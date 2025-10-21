# Game modules

## Game.Achievements (module)

This module implements the game's achievements framework: declarations of achievement IDs, lightweight marker/data components for ECS-driven achievement events, systems that monitor game state and events to report progress/unlock achievements, and platform mapping for external (GDK/Xbox) reporting.

Key pieces:
- Achievements (static): central list of AchievementId constants (MyFirstCity .. Pierfect) with associated thresholds/attributes. Use these IDs to reference achievements across systems and mods.
- AchievementTriggerSystem: main in-game achievement evaluator. Runs each tick, samples game state via many EntityQueries (created objects, parks, service/unique buildings, energy producers, transport queues, policies, tourism/population stats, prefab AchievementFilterData, etc.) to:
  - Compute absolute or incremental progress for many achievements (SixFigures, ShipIt, HowMuchIsTheFish, ALittleBitofTLC, SquasherDowner, ZeroEmission, OneofEverything, FourSeasons, TheInspector, etc.)
  - Consume a NativeQueue<TransportedResource> filled by other systems/jobs to accumulate transported-resource progress (ShipIt).
  - Use ProgressBuffer and UserDataProgressBuffer instances to indicate progress or persist progress to platform user data.
  - Use PlatformManager to indicate progress/unlocks and to persist some progress to platform user-data, logging errors to an ILog.
  - Expose GetTransportedResourceQueue() for other systems/jobs to enqueue transport events and AddWriter(JobHandle) so writers can register dependencies.
  - Serialize/Deserialize progress into saves and SetDefaults for new games.
- EventAchievementTriggerSystem: listens for created event entities carrying EventAchievement marker and prefab EventAchievementData buffers, creates temporary EventAchievementTrackingData entities to wait a configured duration, and unlocks achievements when tracking entries expire. Uses SimulationSystem for frame timing and a ModificationEndBarrier to defer structural changes safely.
- Marker/data components:
  - EventAchievement: 1-byte tag component to mark event entities that can trigger achievements.
  - ObjectAchievement: 1-byte tag for object-based achievement entities.
  - EventAchievementTrackingData: per-tracking-entity component (m_StartFrame, m_ID) serialized with ISerializable for tracking temporary timed event achievements.
  - TransportedResource: lightweight struct with an Entity reference and m_Amount used to report transported resource quantities.
- GdkAchievementsMapping: maps internal achievement enum/ids to external numeric IDs for Microsoft GDK/Xbox reporting (ensure IDs match your GDK configuration).

Notes and behaviors to be aware of:
- Many achievements rely on prefab-level AchievementFilterData to include/exclude prefabs from counting.
- Some ProgressBuffers persist to platform user-data via UserDataProgressBuffer and can throw/log errors if platform APIs fail.
- AchievementTriggerSystem maintains several native counters and caches and must be given writer JobHandles for safe multi-threaded queue use.
- Event achievements are scheduled and unlocked after configured durations; structural changes are deferred to the end barrier to avoid mid-frame modifications.

### Usage example
```csharp
using Unity.Entities;
using Unity.Jobs;
using Game.Achievements;
using Colossal.PSI.MicrosoftGdk; // if interacting with GDK mapper

// Get core systems
var world = World.DefaultGameObjectInjectionWorld;
var achievementSystem = world.GetOrCreateSystemManaged<AchievementTriggerSystem>();
var eventTriggerSystem = world.GetOrCreateSystemManaged<EventAchievementTriggerSystem>();

// 1) Enqueue a transported resource from another system/job:
//    Acquire the transport queue and add writer dependency for any job that writes to it.
var transportQueue = achievementSystem.GetTransportedResourceQueue();

// Example job that writes to the queue (pseudo-code)
JobHandle writerHandle = default; // assume some job scheduled that will enqueue TransportedResource
achievementSystem.AddWriter(writerHandle); // ensure achievement system waits for job completion

// Alternatively, enqueue directly from main thread:
var queue = transportQueue; // NativeQueue<TransportedResource>
if (queue.IsCreated)
{
    queue.Enqueue(new TransportedResource { m_CargoTransport = Entity.Null, m_Amount = 12345 });
}

// 2) Check or unlock an achievement by id (illustrative; use platform API in game):
AchievementId id = Achievements.SixFigures;
// PlatformManager.instance.UnlockAchievement(id); // game/platform API typically used

// 3) Create an event entity that will trigger a timed achievement:
// (Event prefab should contain EventAchievementData mapping to AchievementId)
// Using EntityManager directly (pseudo-code):
var em = world.EntityManager;
var e = em.CreateEntity(
    typeof(Game.Events.Event), typeof(PrefabRef),
    typeof(EventAchievement), typeof(Created)
);
// set PrefabRef appropriately and optionally a Duration component so EventAchievementTriggerSystem
// will schedule the tracking entry. The system will create EventAchievementTrackingData and unlock
// when its startFrame passes.

// 4) Reference achievement ids in mod code:
if (/* your check */ false)
{
    // Example use: pass id to whatever achievement API the game exposes
    // AchievementManager.Unlock(Achievements.MyFirstCity);
}

// 5) If mapping to GDK, ensure GdkAchievementsMapping is present so GDK reporting maps internal ids:
// new GdkAchievementsMapping(); // instantiated by game or plugin registration (preserve attribute ensures presence)
```

---

## Game.Agents (batch 1)

This module contains small ECS data components and an enum used by agent-related systems in Cities: Skylines 2. The items included are:

- HasJobSeeker (struct, IComponentData, IEnableableComponent, ISerializable)  
  Marks an entity as a job seeker and stores:
  - m_Seeker: Entity reference (serialized if save version includes seekerReferences)
  - m_LastJobSeekFrameIndex: uint (serialized if save version includes findJobOptimize)  
  Enableable — can be toggled per-entity. Deserialize gates fields by save-version flags.

- JobSeeker (struct, IComponentData, ISerializable)  
  Lightweight tag + small state:
  - m_Level: byte (serialized)
  - m_Outside: byte (runtime-only, not serialized)

- LeisureType (enum)  
  Leisure/tourism categories (Meals, Entertainment, Commercial, CityIndoors, Travel, CityPark, CityBeach, Attractions, Relaxation, Sightseeing) and a Count sentinel for sizing/iteration.

- MovingAway (struct, IComponentData, ISerializable)  
  Marks an agent moving away from a target:
  - m_Target: Entity (serialized)

- PropertySeeker (struct, IComponentData, IEnableableComponent, ISerializable)  
  Tracks property-searching state:
  - m_TargetProperty, m_BestProperty: Entity
  - m_BestPropertyScore: float
  - m_LastPropertySeekFrame: uint (deserialization handles older formats where this was a byte)

- TaxPayer (struct, IComponentData, ISerializable)  
  Tracks income/tax metrics:
  - m_UntaxedIncome: int (always serialized)
  - m_AverageTaxRate: int (serialized only if save version supports it; defaults to 10 for older saves)

Common usage patterns:
- Use EntityManager / Entities API to AddComponentData, GetComponentData, SetComponentData.
- Many components implement ISerializable; the engine will call Serialize/Deserialize — you normally do not call these directly.
- Several components are enableable so you can toggle participation in systems with SetComponentEnabled<T>.
- Be mindful of save-version/format flags when reasoning about persisted fields (some fields are omitted for backwards compatibility).

### Usage example
```csharp
// Example: create an agent entity, attach several agent components and later query/update them.
var em = World.DefaultGameObjectInjectionWorld.EntityManager;

// Create an agent entity (archetype would normally include required components)
Entity agent = em.CreateEntity();

// Initialize components
em.AddComponentData(agent, new Game.Agents.JobSeeker { m_Level = 2, m_Outside = 0 });
em.AddComponentData(agent, new Game.Agents.HasJobSeeker {
    m_Seeker = agent,
    m_LastJobSeekFrameIndex = 0u
});
em.AddComponentData(agent, new Game.Agents.MovingAway { m_Target = Entity.Null });
em.AddComponentData(agent, new Game.Agents.PropertySeeker {
    m_TargetProperty = Entity.Null,
    m_BestProperty = Entity.Null,
    m_BestPropertyScore = 0f,
    m_LastPropertySeekFrame = 0u
});
em.AddComponentData(agent, new Game.Agents.TaxPayer {
    m_UntaxedIncome = 50000,
    m_AverageTaxRate = 12
});

// Enable/disable job seeking without removing component
em.SetComponentEnabled<Game.Agents.HasJobSeeker>(agent, true);

// Update last-seek frame later in a system
var seekerComp = em.GetComponentData<Game.Agents.HasJobSeeker>(agent);
seekerComp.m_LastJobSeekFrameIndex = (uint)SimulationManager.instance.m_currentFrameIndex;
em.SetComponentData(agent, seekerComp);

// Example Entities query (pseudo-code inside a System)
Entities
    .WithAll<Game.Agents.JobSeeker>()
    .ForEach((ref Game.Agents.JobSeeker js, ref Game.Agents.PropertySeeker ps) => {
        // Use js.m_Level and ps fields to evaluate property choices
        if (ps.m_BestProperty != Entity.Null) {
            // evaluate relocation or scoring logic...
        }
    }).Run();

// Use LeisureType for UI/logic branching
void ShowLeisureIcon(Game.Agents.LeisureType type) {
    switch (type) {
        case Game.Agents.LeisureType.CityPark:
            ShowIcon("icon_park");
            break;
        case Game.Agents.LeisureType.Meals:
            ShowIcon("icon_meals");
            break;
        default:
            ShowIcon("icon_default");
            break;
    }
}
```

---

## Game.Areas

The Game.Areas module provides the ECS components, buffer types, enums, utility helpers and systems used to represent, index, triangulate, raycast, resource-sample and manage polygonal "areas" in Cities: Skylines 2 (lots, districts, map tiles, surface areas, extractors, map features, wood/ore resources, etc.). It is the central toolkit for polygonal area workflows and exposes:

- Core components & value types
  - Area (flags, serializable) — primary area state and flags (Complete, CounterClockwise, NoTriangles, Slave, ...).
  - Geometry — bounds, center position and surface area metadata computed by triangulation.
  - Triangle, Node, LabelVertex, LabelExtents, SubArea, ServiceDistrict, MapFeatureElement, WoodResource, Extractor, DistrictModifier and many small POD buffer elements used by area systems.
  - Tags (empty blittable components) such as Surface, Space, Lot, MapTile, Terrain, Navigation, HangaroundLocation used for filtering.
  - Enums and masks: AreaType, AreaTypeMask, MapFeature, DistrictOption, DistrictModifierType and references to VehicleWorkType.

- Major systems
  - GeometrySystem — triangulates polygon node buffers (ear-clipping), equalizes triangles and computes triangle height ranges relative to Terrain/Water. Runs in Burst jobs; supports incremental and full rebuilds.
  - SearchSystem — builds and exposes a NativeQuadTree of area triangle bounds; provides GetSearchTree / AddSearchTreeReader / AddSearchTreeWriter to coordinate job dependencies for safe concurrent access.
  - AreaConnectionSystem — burst-parallel job to create/update/remove secondary connection lanes (road/pedestrian/border) to match area geometry and connection prefabs, using ModificationBarrier for structural changes.
  - AreaResourceSystem — samples terrain/water/natural resources to compute extractors, map feature resource values and provides helpers like CalculateBuildable for buildability of a cell.
  - SurfaceExpandSystem — computes per-node expansion offsets for surfaces (to grow areas for footprints/connections).
  - MapTileSystem — legacy 23×23 tile generator and manager for map tiles.
  - SurfaceUpdateSystem — propagates Updated state from network node entities into overlapping area entities by querying the SearchSystem quad-tree.
  - UpdateCollectSystem — collects updated 2D bounds for lots/districts/tiles/spaces into persistent NativeLists and coordinates reader/writer dependencies with SearchSystem.
  - ValidationHelpers / ValidationSystem — tools and Burst jobs to validate areas/triangles for geometry errors, overlaps, water/storage/distance rules, reporting ErrorData to queues.
  - RaycastJobs (FindAreaJob, RaycastLabelsJob) — high-performance Burst raycasting against the search tree and label quads with results written to accumulators.

- Utilities & helpers
  - AreaUtils — geometry helpers (triangle/edge tests, label transforms), object placement utilities (TryGetRandomObjectLocation, GetRandomPosition, TryFitInside), pathfinding helpers, node expansion and collision masks.
  - AreaTools — small mapping helpers (e.g., MapFeature → icon name).
  - Serialization/versioning helpers: many area components/buffers implement ISerializable or provide version-aware Deserialize to preserve save compatibility.

- Practical/modder guidance
  - Areas are frequently stored in DynamicBuffer<T> (Node, Triangle, LabelVertex, etc.). Respect InternalBufferCapacity hints and own buffer mutation/Updated signalling patterns.
  - To trigger geometry work, add/mark Updated (or Created) on area entities. GeometrySystem and related systems run heavy Burst jobs — schedule and chain dependencies correctly.
  - For threaded access to the quad-tree, use SearchSystem.GetSearchTree and register any jobs via AddSearchTreeReader/AddSearchTreeWriter so systems can track dependencies.
  - Use ModificationBarrier(s) when scheduling structural changes (entity creation/destruction, adding/removing components) from parallel jobs.
  - When you allocate unmanaged/native memory (native heap blocks used internally), ensure you manage lifetime to avoid leaks.
  - Use AreaResourceSystem.CalculateBuildable (and Terrain/Water systems) to compute buildable fractions when placing items or scoring suitability.
  - Follow version-aware serialization patterns when persisting custom area data to remain compatible with save versions.

### Usage example
```csharp
// Illustrative example: create a simple surface area, add nodes/labels/resources, mark Updated,
// query systems (AreaResourceSystem, SearchSystem, UpdateCollectSystem) and compute buildability.
// Note: some system API calls (GetSurfaceData/GetHeightData) are game-specific and are shown
// as representative calls; adapt to your runtime's exact APIs.

using Unity.Entities;
using Unity.Mathematics;
using Unity.Collections;
using Game.Areas;

public static class AreasUsageExample
{
    public static void RunExample(World world)
    {
        var em = world.EntityManager;

        // 1) Create an area entity with Node/Triangle buffers and tag it as a Surface so systems will process it
        var archetype = em.CreateArchetype(
            typeof(Game.Areas.Surface),           // tag for surface areas
            typeof(Game.Areas.Area),              // primary area component
            typeof(Game.Areas.Geometry)           // geometry produced by triangulation
        );
        var area = em.CreateEntity(archetype);
        var nodes = em.AddBuffer<Game.Areas.Node>(area);
        var triangles = em.AddBuffer<Game.Areas.Triangle>(area);

        // Add a simple quad (clockwise or counter-clockwise depends on your data)
        nodes.Add(new Game.Areas.Node(new float3(0f, 0f, 0f), 0f));
        nodes.Add(new Game.Areas.Node(new float3(10f, 0f, 0f), 0f));
        nodes.Add(new Game.Areas.Node(new float3(10f, 0f, 10f), 0f));
        nodes.Add(new Game.Areas.Node(new float3(0f, 0f, 10f), 0f));

        // Add label extents/vertex
        var extents = em.AddBuffer<Game.Areas.LabelExtents>(area);
        extents.Add(new Game.Areas.LabelExtents(new float2(2f, 2f), new float2(8f, 8f)));

        var labelVerts = em.AddBuffer<Game.Areas.LabelVertex>(area);
        labelVerts.Add(new Game.Areas.LabelVertex {
            m_Position = new float3(5f, 0.1f, 5f),
            m_UV0 = new float2(0f,0f),
            m_UV1 = new float2(0f,0f),
            m_Color = new UnityEngine.Color32(255,255,255,255),
            m_Material = 0
        });

        // Add a wood resource reference (example: treeEntity previously created)
        // Entity treeEntity = ...;
        // var woodBuf = em.AddBuffer<Game.Areas.WoodResource>(area);
        // woodBuf.Add(new Game.Areas.WoodResource(treeEntity));

        // 2) Mark the area Updated so GeometrySystem/SearchSystem will re-triangulate and index it
        em.AddComponentData(area, new Updated()); // use the game's Updated component

        // 3) Use AreaResourceSystem helper to compute buildability for a sample cell
        var areaResSys = world.GetOrCreateSystemManaged<Game.Areas.AreaResourceSystem>();
        var terrainSys = world.GetOrCreateSystemManaged<Game.Areas.TerrainSystem>();
        var waterSys = world.GetOrCreateSystemManaged<Game.Areas.WaterSystem>();

        // Pseudocode: obtain terrain/water sample data as required by AreaResourceSystem.CalculateBuildable
        var waterSurface = waterSys.GetSurfaceData(out var _);   // adapt to real API
        var terrainHeights = terrainSys.GetHeightData();        // adapt to real API

        float3 cellCenter = new float3(2.5f, 0f, 2.5f);
        float2 cellSize = new float2(1f, 1f);

        // AreasConfigurationData typically stores buildable slope, fetch via singleton query
        var areasConfigQuery = em.CreateEntityQuery(typeof(Game.Areas.AreasConfigurationData));
        var config = areasConfigQuery.GetSingleton<Game.Areas.AreasConfigurationData>();
        float buildableSlope = config.m_BuildableLandMaxSlope;

        float buildable = Game.Areas.AreaResourceSystem.CalculateBuildable(
            cellCenter, cellSize, waterSurface, terrainHeights, buildableSlope
        );
        UnityEngine.Debug.Log($"Buildable fraction: {buildable}");

        // 4) Access the SearchSystem quad-tree for read access and register a job reader
        var searchSys = world.GetExistingSystemManaged<Game.Areas.SearchSystem>();
        if (searchSys != null)
        {
            // Acquire tree for read-only; get dependencies for safe job chaining
            var tree = searchSys.GetSearchTree(readOnly: true, out Unity.Jobs.JobHandle deps);

            // If you schedule a job that reads the tree, use 'deps' when scheduling and then register the reader
            // Example: var myReadJob = myJob.Schedule(deps);
            // searchSys.AddSearchTreeReader(myReadJob);

            // If you only read synchronously on main thread, ensure there are no outstanding writers (Complete deps)
            deps.Complete();
            // Now you can safely read the quad-tree on main thread (if API permits)
        }

        // 5) Collect updated lot bounds via UpdateCollectSystem
        var updateCollect = world.GetExistingSystemManaged<Game.Areas.UpdateCollectSystem>();
        if (updateCollect != null)
        {
            Unity.Jobs.JobHandle boundsDeps;
            var lotBounds = updateCollect.GetUpdatedLotBounds(out boundsDeps);

            // Option A: wait and read immediately on main thread
            boundsDeps.Complete();
            for (int i = 0; i < lotBounds.Length; i++)
            {
                var b = lotBounds[i];
                // process updated bounds...
            }

            // Option B: schedule a job that reads lotBounds and register it as a reader:
            // JobHandle myRead = myJob.Schedule(...);
            // updateCollect.AddLotBoundsReader(myRead);
        }

        // 6) To propagate node updates into overlapping areas, mark a network node Updated:
        // em.AddComponentData(nodeEntity, new Updated()); // SurfaceUpdateSystem will find overlapping areas and mark them Updated.
    }
}
```

This summary captures the main types, systems and usage patterns: add/modify ECS components and buffers (Node/Triangle/Area/Geometry), mark Updated to trigger geometry and indexing work, coordinate threaded access to the quad-tree via SearchSystem, use AreaResourceSystem for terrain/water sampling/buildability, and follow ModificationBarrier/JobHandle conventions when performing structural changes or scheduling Burst jobs.

---

## Game.AssetPipeline (AssetImportPipeline & IPrefabFactory)

AssetImportPipeline is the central static pipeline used to import art/content into Cities: Skylines 2. It collects source files, runs configured importers and post-processors (textures, models, specialized Didimo character flow), generates Geometry/Surface/RenderPrefab assets, serializes them into a target ILocalAssetDatabase, and optionally converts materials to the engine's Virtual Texturing (VT) format. The pipeline supports parallel import, progress/cancellation callbacks, per-asset settings (settings.json), JSON schema generation for settings, VT mid-mip cache creation, debug instantiation of prefabs, and various helper utilities for LOD setup, emissive/procedural animation components, and resource disposal.

Key features and surface APIs:
- Static configuration: AssetImportPipeline.targetDatabase (ILocalAssetDatabase), AssetImportPipeline.useParallelImport, and AssetImportPipeline.OnDebugTexture.
- Main entry: ImportPath(...) — collects paths, runs importers/post-processors, performs main-thread serialization, and optionally converts surfaces to VT. Supports progress callbacks and cancellation.
- Fine-grained steps: ImportTextures, ImportModels, CreateGeometriesAndSurfaces, CreateDidimoAssets, CreateRenderPrefab(s), SetupLODs, SetupComponents, and specialized helpers for emissive/procedural animation setup.
- VT workflow: ConvertSurfacesToVT, BuildMidMipsCache, HideVTSourceTextures, and ApplyVTMipBias for rebuilding VT assets with a different mip bias.
- Diagnostics and tooling: GetImportChainFor, CollectDataToImport, GenerateJSONSchema, GetTextureReferenceCount, InstantiateRenderPrefabs for editor/debug preview.
- Utilities: naming normalization, unmanaged-to-native-array helpers, LOD validation/disposal, and progress/main-thread dispatch support.

IPrefabFactory is a small interface used by the pipeline to create typed prefab instances (subclasses of PrefabBase) from a source path and an LOD level:
- Method: T CreatePrefab<T>(string sourcePath, string name, int lodLevel) where T : PrefabBase
- Implementations bridge the pipeline to project/game-specific prefab construction and registration.

Together, AssetImportPipeline + IPrefabFactory let toolchains/importers produce and instantiate prefab assets reliably while supporting large-batch imports, VT conversion, and editor tooling.

### Usage example
```csharp
// Example: simple prefab factory + import call and preview instantiation.
// (Adapt AssetDatabase/game APIs to your environment.)

public class SimplePrefabFactory : IPrefabFactory
{
    public T CreatePrefab<T>(string sourcePath, string name, int lodLevel) where T : PrefabBase
    {
        // Pseudocode: load asset data and initialize a concrete PrefabBase subclass.
        var raw = MyAssetLoader.Load(sourcePath); // replace with real loader
        T prefab = Activator.CreateInstance<T>();
        // Assume PrefabBase exposes an initialization entry for user code:
        // prefab.InitializeFromRaw(raw, name, lodLevel);
        return prefab;
    }
}

public async Task RunImportDemoAsync()
{
    // configure target DB and concurrency
    AssetImportPipeline.targetDatabase = AssetDatabase.game; // or a transient ILocalAssetDatabase
    AssetImportPipeline.useParallelImport = true;

    // optional progress/cancel callback
    AssetImportPipeline.SetReportCallback((title, desc, fraction) =>
    {
        Debug.Log($"{title}: {desc} ({fraction:P0})");
        return false; // return true to request cancellation
    });

    IPrefabFactory factory = new SimplePrefabFactory();

    // Import assets (await because ImportPath is async)
    await AssetImportPipeline.ImportPath(
        projectRootPath: @"C:\MyProjects\MyArtProject",
        relativePaths: new[] { "Props/Bench", "Props/Lamp" },
        importMode: ImportMode.Geometry | ImportMode.Textures,
        convertToVT: true,
        progressCallback: null,
        prefabFactory: factory
    );

    // Optional: preview instantiated render prefabs in editor
    var prefabs = AssetDatabase.game.GetAssets(default(SearchFilter<RenderPrefab>()))
        .Select(p => (prefab: p.Load(), sourcePath: p.name)); // adapt as needed

    AssetImportPipeline.InstantiateRenderPrefabs(prefabs, smartInstantiate: true, ignoreLODs: true);
}
```

---

## Game.Assets (Assets module)

This module contains lightweight asset and metadata types used by Cities: Skylines 2 for representing maps, saves, cinematic camera sequences, and small value types used in save metadata. Key responsibilities:

- Metadata wrappers: MapMetadata and SaveGameMetadata extend Metadata<T> and hook into the metadata lifecycle (OnPostLoad) to populate target objects (MapInfo / SaveInfo) with source metadata (display name, cloud target, readonly flag, linked SaveGameData). They also provide constants for file extensions and helper delegates for user-specific persistent storage locations (kExtension and kPersistentLocation).
- Asset descriptors: CinematicCameraAsset wraps cinematic camera sequences and implements IJsonWritable to emit a compact JSON summary (name, guid, identifier, cloud target, isReadOnly). MapInfo and SaveInfo are the main data containers for maps and save-games respectively: both expose presentation fields (preview/thumbnail, displayName), content prerequisites, and runtime flags (isReadonly, locked, cloudTarget).
- Save/game utilities: SaveGameMetadata exposes a convenience isValidSaveGame property that verifies linked save data and readonly state. SaveInfo supports shallow Copy() with a defensive copy for options and custom Write(IJsonWriter) formatting for save listings.
- Dependencies and validation: IContentPrerequisite is the simple interface for assets that declare content dependencies (string[] contentPrerequisites) so loaders/validators can check required packages/mods.
- Small value types and serialization: SimulationDateTime is a small value-type representation of in-game datetime (year/month/hour/minute) with JSON read/write and equality semantics and AOT support registration.

Common patterns:
- JSON output is produced via IJsonWriter.Write / TypeBegin/TypeEnd implemented on many types (CinematicCameraAsset, MapInfo, SaveInfo, SimulationDateTime).
- Persistent storage helpers use PlatformManager.instance.userSpecificPath to build per-user folders (e.g., "Maps/<userPath>", "Saves/<userPath>", "CinematicCamera/<userPath>").
- OnPostLoad lifecycle methods in Metadata<T> subclasses populate target objects from SourceMeta (ownership, cloud target, display name) when the metadata database finishes loading.

### Usage example
```csharp
using System;
using Game.Assets;

// Example: create a MapInfo, wrap it in MapMetadata (normally provided by the asset DB), and write JSON
var map = new MapInfo {
    id = "island_01",
    displayName = "Sunny Island",
    theme = "Temperate",
    temperatureRange = new Bounds1(-10f, 35f),
    area = 1024f,
    contentPrerequisites = new[] { "core_assets", "beach_pack" }
};

// Example SaveInfo populated from runtime
var save = new SaveInfo {
    id = "save_001",
    displayName = "My City",
    cityName = "My City",
    population = 12000,
    money = 250000,
    simulationDate = new SimulationDateTime(2035, 4, 14, 30),
    contentPrerequisites = new[] { "DLC.RIVER" },
    preview = /* TextureAsset reference */,
    sessionGuid = Guid.NewGuid()
};

// Check prerequisites via IContentPrerequisite consumer (pseudo-API)
bool AreAvailable(IContentPrerequisite asset) {
    var list = asset?.contentPrerequisites;
    if (list == null || list.Length == 0) return true;
    foreach (var id in list) {
        if (!ContentManager.HasContent(id)) return false; // ContentManager is the game's content API
    }
    return true;
}

// Write JSON summaries (IJsonWriter is game-specific; use the engine's implementation)
IJsonWriter writer = /* obtain writer from game API */;
map.Write(writer);   // MapInfo implements IJsonWritable
save.Write(writer);  // SaveInfo implements IJsonWritable

// Use metadata helpers (paths/constants)
string mapsFolder = MapMetadata.kPersistentLocation();            // "Maps/<userPath>"
string savesFolder = SaveGameMetadata.kPersistentLocation();      // "Saves/<userPath>"
string cameraExt = CinematicCameraAsset.kExtension;               // ".CinematicCamera"

// Use SaveInfo.Copy to mutate options safely
var copy = save.Copy();
copy.options = copy.options ?? new System.Collections.Generic.Dictionary<string,bool>();
copy.options["traffic"] = false;
```

---

## Game.Audio (module)

Summary
Audio module for Cities: Skylines 2 manages all game audio responsibilities: low-level playback, ambience grouping, radio, music loops, sfx culling and small-scale weather/water audio. Key components:

- AudioManager — central main-thread audio coordinator. Holds mixer/groups, pooled Unity AudioSources, UI one-shots, ambient camera sources, menu music (AudioLoop), the radio subsystem, and the job-facing SourceUpdateData/NativeQueue API. Modders should use AudioManager.instance for playback, registering SFX, routing mixer groups and for getting SourceUpdateData when writing jobs. Many methods require main-thread calls; job authors must use GetSourceUpdateData + AddSourceUpdateWriter to chain dependencies.

- AudioGroupingSystem — ECS system that groups ambient sounds (far/near) per ambience type and updates EffectInstance entities via a Burst IJob. It reads traffic/zone ambience maps, terrain height, effect flags and climate to compute intensities. It lazily creates EffectInstance entities and exposes no public API — changes come via AudioGroupingSettingsData assets/entities.

- AudioLoop — utility to load/play a menu/ambient AudioAsset with seamless looping and scheduled handoffs. Start(...) is async (loads clips) and Update(deltaTime) must be called to drive scheduling and fades. Use FadeOut/Dispose to stop and clean up.

- Radio (Game.Audio.Radio.Radio) — manages radio networks/channels, queueing programs, on-demand clip population, emergency interrupts, equalizer/spectrum visuals and playback controls. Create with an AudioMixerGroup, call Reload/Enable and call Update(normalizedTime) each frame. Events notify program/clip changes.

- BpmAnalyzer — synchronous utility that estimates BPM of an AudioClip by analyzing a per-frame energy signal and scanning candidate tempos. Good for preprocessing or offline analysis; run off main thread for long clips.

- SFXCullingSystem — ECS system that Burst-compiles jobs to cull and enable/disable prefab audio/effects based on distance, culling groups and configured group limits. It interacts with EffectControlSystem (enabled effects) and AudioManager (source updates). Use or modify the optional CullingAudioSettingsData singleton to control group culling behavior.

- WeatherAudioSystem — low-frequency ECS system that updates a small camera-following water ambient effect. It samples WaterSystem depth texture and TerrainHeightData in a Burst job and updates an EffectInstance when the camera is near water. Configure via the WeatherAudioData singleton.

Modding/Integration tips
- For one-shot/UI audio: use AudioManager.instance.PlayUISound(...) or PlayUISoundIfNotPlaying(...).
- For scheduled job-driven audio updates: obtain SourceUpdateData via AudioManager.GetSourceUpdateData(out JobHandle deps) and call AddSourceUpdateWriter(jobHandle) to merge dependencies.
- Menu music: create an AudioLoop via AudioManager.PlayMenuMusic(tag) or directly use AudioLoop (Start is async and must be awaited).
- Radio: create Game.Audio.Radio.Radio with a mixer group, call Reload/Enable and drive with Update(normalizedTime).
- Change ambience/ambient prefabs or settings by editing/creating AudioGroupingSettingsData or AmbientAudioSettingsData; AudioGroupingSystem reads configuration entities (restarting system may be needed).
- BpmAnalyzer.AnalyzeBpm is CPU-bound and synchronous — run on a background thread for long clips.
- Many APIs are main-thread-only (UnityEngine.Object, AudioSource, AudioMixer). Use ResetAudioOnMainThread when needed.

### Usage example
```csharp
// Example usage snippets (C# / Unity / DOTS mixed):

// 1) Play a UI one-shot (main thread)
Entity uiClipEntity = /* an entity that has AudioEffectData or AudioRandomizeData */;
AudioManager.instance?.PlayUISoundIfNotPlaying(uiClipEntity, 0.8f);

// 2) Start menu music (async)
async Task StartMenuMusic(string tag)
{
    // AudioManager will find a matching AudioAsset and play via AudioLoop
    await AudioManager.instance?.PlayMenuMusic(tag);
}

// 3) Analyze BPM of an AudioClip (run off main thread for long clips)
Task<int> DetectBpmAsync(AudioClip clip) =>
    Task.Run(() => Game.Audio.Radio.BpmAnalyzer.AnalyzeBpm(clip));

// 4) Change water audio settings via ECS (WeatherAudioData singleton)
void SetWaterAudio(World world, float intensity, int nearDistance)
{
    var em = world.EntityManager;
    var q = em.CreateEntityQuery(typeof(WeatherAudioData));
    if (!q.IsEmptyIgnoreFilter)
    {
        var entity = q.GetSingletonEntity();
        var data = em.GetComponentData<WeatherAudioData>(entity);
        data.m_WaterAudioIntensity = intensity;
        data.m_WaterAudioNearDistance = nearDistance;
        em.SetComponentData(entity, data);
    }
}

// 5) Configure culling settings (CullingAudioSettingsData singleton)
void ConfigureCulling(World world)
{
    var em = world.EntityManager;
    // Create or get singleton entity for CullingAudioSettingsData (pattern-specific)
    Entity e = /* obtain or create singleton entity */;
    em.SetComponentData(e, new CullingAudioSettingsData {
        m_PublicTransCullMaxAmount = 8,
        m_PublicTransCullMaxDistance = 500f
    });
}

// 6) Create & enable radio (main thread)
// (Assumes you have an AudioMixerGroup radioGroup)
var radio = new Game.Audio.Radio.Radio(radioGroup);
radio.Reload(enable: false);
radio.RestoreRadioSettings(savedChannel: "MyChannelId", savedAds: false);
radio.Enable(Camera.main.gameObject);
// drive radio each frame with normalized time-of-day
void Update() => radio.Update(normalizedTimeOfDay);
```

---

## Game.Buildings

A consolidated overview of the Game.Buildings module — the Cities: Skylines 2 building-domain ECS layer. It provides the data types, flags, helper utilities and systems used to represent, initialize, serialize and simulate building-related state. Key features:

- Data model
  - Many compact IComponentData and IBufferElementData structs for building state (Building, BuildingCondition, BuildingNotifications, Battery, WaterConsumer, TransportStation, ResourceConsumer, School, Park, etc.).
  - Small marker/tag components (1-byte structs) for classification and queries (e.g., CityEffectProvider, LocalEffectProvider, ResidentialProperty, Condemned). Tag components use StructLayout(Size = 1) or IEmptySerializable for stable serialization.
  - Dynamic buffers for per-building lists: InstalledUpgrade, Occupant/Patient/Renter, Efficiency (buffer entries), BuildingModifier, SpawnLocationElement, Student, Resources.
  - Enums/flags are compact (byte-backed) and often [Flags] for bitwise checks: BuildingFlags, BuildingNotification, ElectricityConsumerFlags, TransportStationFlags, etc.

- Systems & jobs
  - Initialization systems that copy prefab data into newly created buildings and prepare runtime state (ParkInitializeSystem, CargoTransportStationInitializeSystem, BatteryInitializeSystem, ResourcesInitializeSystem, CityServiceWorkplaceInitializeSystem, etc.).
  - Update systems that compute and keep building metrics consistent using Burst IJobChunk: CityServiceEfficiencySystem (writes ServiceBudget efficiency factors), BuildingStateEfficiencySystem (Disabled/Abandoned/Destroyed factors), RoadConnectionSystem (selects best road edge / manages secondary lanes), SchoolUpdatedSystem (student bookkeeping), LocalEffectSystem (maintains NativeQuadTree of local modifiers), ZoneCheckSystem (zone validation), WaterPoweredInitializeSystem, and others.
  - Upgrade & reference management: ServiceUpgradeReferencesSystem (keeps InstalledUpgrade buffers in sync), ServiceUpgradeSystem (installs/removes upgrade-provided components).
  - Systems use performance-friendly patterns: Burst + IJobChunk, ComponentTypeHandle/BufferTypeHandle caches, ComponentLookup/BufferLookup, parallel EntityCommandBuffer via ModificationBarrier variants, IconCommandBuffer for icons, and registration of job handles with system barriers/readers.

- Utilities & helpers
  - BuildingUtils: geometry helpers, lot sampling, height sampling, efficiency math/combinations, checks for options, upgrade placement, shelter capacity, collapse/maintenance calculations.
  - PropertyUtils: rent and apartment-quality scoring, company/property matching jobs.
  - ValidationHelpers: job-friendly validators for building/upgrades.
  - LocalEffectSystem helpers for reading/applying local modifiers (GetReadData/GetSearchTree with JobHandle synchronization).

- Serialization & compatibility
  - Most serialized components implement Colossal.Serialization ISerializable with version-gated Deserialize branches to remain compatible across save formats.
  - Marker components write/read a single byte or use IEmptySerializable to preserve stable footprint.
  - Enums and many fields are packed; when extending, follow the version-guard pattern and preserve byte-backed semantics.

- Patterns & modding tips
  - Use the presence/absence of marker components as behavior switches.
  - Prefer BuildingUtils and provided helpers rather than reimplementing geometry/sampling logic.
  - For structural changes from jobs, always use the appropriate ModificationBarrier's ParallelWriter and register job handles with systems that read/write the same data.
  - When adding serialized fields, append them and add version checks in Deserialize. Do not reorder existing serialized bytes or change enum underlying sizes.
  - If your mod updates singletons used by systems (e.g., BuildingEfficiencyParameterData, ServiceBudgetData), mark the entity Updated to force full recalculation where expected.

### Usage example
```csharp
using Unity.Entities;
using Unity.Mathematics;
using Game.Buildings;

// Example: create a building, attach common building components and buffers,
// check a marker option, read battery hours and register an installed upgrade.

var world = World.DefaultGameObjectInjectionWorld;
var em = world.EntityManager;

// Create a simple building entity (in practice you may use a prefab archetype)
var archetype = em.CreateArchetype(
    typeof(Game.Buildings.Building),
    typeof(Game.Buildings.Battery),
    typeof(Game.Buildings.InstalledUpgrade), // dynamic buffer
    typeof(Game.Buildings.Efficiency),       // dynamic buffer for efficiency factors
    typeof(Game.Common.Created)              // created marker used by initialization systems
);
var building = em.CreateEntity(archetype);

// Set link/position flags for Building
em.SetComponentData(building, new Game.Buildings.Building {
    m_RoadEdge = Entity.Null,
    m_CurvePosition = 0.5f,
    m_OptionMask = 0u,
    m_Flags = Game.Buildings.BuildingFlags.Illuminated
});

// Add a Battery with stored energy (internal units)
em.SetComponentData(building, new Game.Buildings.Battery {
    m_StoredEnergy = 8500L,
    m_Capacity = 10000,
    m_LastFlow = 120
});

// Read battery hours via the provided helper property
var battery = em.GetComponentData<Game.Buildings.Battery>(building);
int storedHours = battery.storedEnergyHours; // uses internal divisor (e.g., storedEnergy / 85)

// Populate an InstalledUpgrade dynamic buffer (ServiceUpgradeReferencesSystem will reconcile upgrades)
var upgrades = em.GetBuffer<Game.Buildings.InstalledUpgrade>(building);
upgrades.Add(new Game.Buildings.InstalledUpgrade { m_Upgrade = Entity.Null, m_OptionMask = 0u });

// Initialize an Efficiency buffer entry (ServiceBudget factor)
var effBuf = em.GetBuffer<Game.Buildings.Efficiency>(building);
effBuf.Clear();
effBuf.Add(new Game.Buildings.Efficiency(Game.Buildings.EfficiencyFactor.ServiceBudget, 1.0f));

// Check an option mask with BuildingUtils
var buildingComp = em.GetComponentData<Game.Buildings.Building>(building);
bool hasPaidParking = Game.Buildings.BuildingUtils.CheckOption(buildingComp, Game.Buildings.BuildingOption.PaidParking);

// If this building provides local effects, tag it and compute local modifiers via LocalEffectSystem:
// (Read access requires synchronizing with that system — example shown for main-thread usage)
if (em.HasComponent<Game.Buildings.LocalEffectProvider>(building))
{
    var localEffectSystem = world.GetExistingSystemManaged<Game.Buildings.LocalEffectSystem>();
    JobHandle deps;
    var readData = localEffectSystem.GetReadData(out deps);
    float value = 1.0f;
    float3 pos = new float3(10f, 0f, 20f);
    readData.ApplyModifier(ref value, pos, Game.Buildings.LocalModifierType.Wellbeing);
    // To schedule jobs that use 'readData', pass 'deps' as dependency and call
    // localEffectSystem.AddLocalEffectReader(yourJobHandle) when scheduling.
}

// Create a ServiceUpgrade entity that targets this building (ServiceUpgradeReferencesSystem will append to InstalledUpgrade)
var upgrade = em.CreateEntity(
    typeof(Game.Buildings.ServiceUpgrade),
    typeof(Game.Buildings.Owner),      // Owner contains m_Owner = building
    typeof(Game.Prefabs.PrefabRef),
    typeof(Game.Common.Created)
);
em.SetComponentData(upgrade, new Game.Buildings.Owner { m_Owner = building });
em.SetComponentData(upgrade, new Game.Prefabs.PrefabRef { m_Prefab = Entity.Null });

// Many building systems (efficiency, initialization, upgrades, road connection, water, resources) run automatically
// on the ECS tick. When changing shared singletons (e.g., ServiceBudgetData), mark them Updated so systems recalc:
// em.SetComponentData(serviceBudgetEntity, new ServiceBudgetData { /* ... */ });

```

---

## CinematicCameraSequence

CinematicCameraSequence is a container for camera animation data used by the game's cinematic/photo mode. It holds five transform curves (PositionX/Y/Z, RotationX (pitch), RotationY (yaw)) plus any number of named modifier curves (CinematicCameraCurveModifier) that drive other photo-mode properties (e.g., exposure). Key features:

- Transforms: transforms[] is a fixed 5-entry array (PositionX/Y/Z, RotationX, RotationY). You can add/remove keys, sample the transform at time t, and apply sampled values to an IGameCameraController.
- Modifiers: A list of named curves (id, AnimationCurve, optional min/max). Used by Refresh to evaluate and set PhotoModeProperty values at runtime.
- Looping: setting loop = true runs EnsureLoop to add keys at time 0 and playbackDuration so curves loop smoothly.
- Rotation handling: PatchRotations adjusts RotationY keys so yaw interpolation is continuous across wrap boundaries (avoids large jumps).
- Editing helpers: AddCameraTransform, AddModifierKey, RemoveModifier/keys, MoveKeyframe; AfterModifications centrally triggers EnsureLoop and PatchRotations when needed.
- Playback duration: playbackDuration controls the end time used for loop endpoint insertion (default 30s).
- Serialization: Implements IJsonWritable/IJsonReadable; CinematicCameraCurveModifier also serializes/deserializes curves and min/max.
- Utility: SampleTransform reads transform keys and composes a sampled position/rotation (uses controller as baseline). Refresh(t, properties, controller) evaluates modifiers and applies transform+modifiers to live controller/properties.

Nested types:
- TransformCurveKey enum: PositionX, PositionY, PositionZ, RotationX, RotationY.
- CinematicCameraCurveModifier struct: id, AnimationCurve curve, float min, float max, AddKey/serialization helpers.

### Usage example
```csharp
// Create and configure a sequence
CinematicCameraSequence seq = new CinematicCameraSequence();
seq.playbackDuration = 10f;

// Add camera transforms (time, position, rotation: pitch(x), yaw(y), roll(z ignored))
seq.AddCameraTransform(0f, new Vector3(0f, 5f, -10f), new Vector3(10f, 0f, 0f));
seq.AddCameraTransform(5f, new Vector3(0f, 10f, -20f), new Vector3(15f, 90f, 0f));

// Add a modifier curve for a photo-mode property named "Exposure"
seq.AddModifierKey("Exposure", 0f, 1f);
seq.AddModifierKey("Exposure", 5f, 2f);

// Enable looping (adds endpoint keys and patches rotations)
seq.loop = true;

// At runtime: evaluate at time t and apply to controller and properties
IGameCameraController controller = GetActiveCameraController(); // game-provided
var properties = new Dictionary<string, PhotoModeProperty>(); // populate with PhotoModeProperty instances keyed by id
float t = 3.2f;

// Apply modifiers and transforms to live controller/properties
seq.Refresh(t, properties, controller);

// Or sample only the transform and set manually
if (seq.SampleTransform(controller, t, out Vector3 sampledPos, out Vector3 sampledRot))
{
    controller.position = sampledPos;
    controller.rotation = sampledRot;
}
```

---

## Game.Citizens (Citizens / Household / Travel module)

This module implements the core ECS data, enums, helpers and initialization/cleanup systems used by Cities: Skylines 2 for citizens, households, pets, meetings, travel and light economy interactions. It is focused on compact, serializable component types and Burst-friendly job systems that initialize and maintain citizen/household state at scale.

Key points
- Components: many tiny IComponentData types (some enableable / tag-like) such as Citizen (compact per-citizen state), Household, HouseholdMember, HouseholdPet, HouseholdNeed, Student, Worker, Teen, TouristHousehold, SchoolSeeker, TravelPurpose, TripNeeded (buffer element), HealthProblem, Meeting/Attendee tags and more. Most entity links are stored as Entity fields and many types implement Colossal.Serialization ISerializable for version-aware save/load.
- Citizen data & enums: Citizen struct contains a compact bitmasked state, wellbeing/health, birthday, pseudo-random seed and helpers (GetAge, GetPseudoRandom, education getters/setters, Serialize/Deserialize). Enums include Purpose, CitizenAge, CitizenEducationLevel, CitizenFlags, Workshift, HealthProblemFlags, MeetingStatus, etc.
- Utilities: CitizenUtils provides many job-friendly helpers (IsDead/IsResident/IsCommuter/IsWorkableCitizen, household helpers like HasMovedIn/HouseholdMoveAway, prefab/sound selection, GetPathfindWeights, deterministic per-citizen pseudo-random access). Prefer the ComponentLookup/BufferLookup overloads when inside jobs.
- Buffer elements: HouseholdCitizen, HouseholdAnimal, TripNeeded, LookingForPartner, PetTrip and others for small inline storage; many with InternalBufferCapacity hints and serializable behavior.
- Systems:
  - CitizenInitializeSystem / CompanyInitializeSystem: initialize newly-created citizens/companies in parallel IJobChunk (assign pseudo-random seed, health/wellbeing, gender, birthday, prefab selection, household membership).
  - HouseholdInitializeSystem: spawn household members/pets/cars, set seekers and city statistics; uses ModificationBarrier + parallel jobs + ECB.
  - HouseholdPetInitializeSystem / HouseholdPetRemoveSystem and HouseholdAndCitizenRemoveSystem: keep buffers in sync and clean up on Deleted markers.
  - MeetingInitializeSystem: assigns AttendingMeeting and prunes buffers.
  - StorageInitializeSystem: seeds company random and brand for storage companies (parallel).
- Serialization & safety: Many components implement ISerializable and perform version checks — preserve field semantics when modding. Several components are IEnableableComponent to allow toggling without changing archetypes. Structural changes are deferred via ModificationBarrierN + EntityCommandBuffer; systems are Burst-friendly and job-chunk oriented.
- Modder notes: Use provided bitfield helpers rather than manual m_State bit ops; inside jobs use ComponentLookup / BufferLookup overloads from utilities; be careful with Entity.Null checks and with version-aware Deserialize; there is a noted potential Equals/GetHashCode inconsistency in CitizenSelectedSoundData (Equals can ignore happiness in some cases while GetHashCode includes it).

### Usage example
```csharp
using Unity.Entities;
using Unity.Collections;
using Unity.Mathematics;
using Game.Citizens;
using Game.Economy; // for Resource helpers if needed

// Minimal examples showing common patterns: create household + citizen + trip and let init systems run.

public static class CitizensExample
{
    public static void CreateHouseholdWithCitizen(World world, Entity householdPrefab, Entity citizenPrefab, Entity building)
    {
        var em = world.EntityManager;

        // Create a household entity with components expected by HouseholdInitializeSystem
        Entity household = em.CreateEntity();
        em.AddComponentData(household, new PrefabRef { m_Prefab = householdPrefab });
        em.AddComponentData(household, new Household());
        em.AddComponentData(household, new CurrentBuilding { m_CurrentBuilding = building });
        em.AddBuffer<HouseholdCitizen>(household);
        em.AddBuffer<Game.Economy.Resources>(household);

        // Create a raw citizen entity that CitizenInitializeSystem will initialize
        Entity citizen = em.CreateEntity(
            typeof(Citizen),
            typeof(HouseholdMember),
            typeof(Game.Common.Created) // initializer systems query Created
        );
        em.SetComponentData(citizen, new HouseholdMember { m_Household = household });

        // Add a Worker component and a travel purpose + planned trip
        em.AddComponentData(citizen, new Worker {
            m_Workplace = Entity.Null,
            m_LastCommuteTime = 0u,
            m_Level = 2,
            m_Shift = Workshift.Day
        });

        em.AddComponentData(citizen, new TravelPurpose {
            m_Purpose = Purpose.GoingToWork,
            m_Data = 0,
            m_Resource = Resource.None
        });

        var trips = em.AddBuffer<TripNeeded>(citizen);
        trips.Add(new TripNeeded {
            m_TargetAgent = Entity.Null,
            m_Purpose = Purpose.GoingToWork,
            m_Data = 0,
            m_Resource = Resource.None
        });

        // Optionally tag as teen / student
        em.AddComponent<Teen>(citizen);
        em.AddComponentData(citizen, new Student { m_School = Entity.Null, m_LastCommuteTime = 0u, m_Level = 1 });

        // Mark the household instance Created so HouseholdInitializeSystem can spawn linked entities/car selection/etc.
        em.AddComponentData(household, new Game.Common.Created());
    }

    // Using CitizenUtils on main thread to pick a sound or deterministic random
    public static Entity PickCitizenSound(EntityManager em, Entity citizen, Entity citizenPrefab)
    {
        if (!em.HasComponent<Citizen>(citizen)) return Entity.Null;
        var c = em.GetComponentData<Citizen>(citizen);
        return CitizenUtils.GetCitizenSelectedSound(em, citizen, c, citizenPrefab);
    }

    // Example: mark household moving away via ECB (call from main thread or job using an ECB)
    public static void MarkHouseholdMovingAway(EntityCommandBuffer ecb, Entity household)
    {
        CitizenUtils.HouseholdMoveAway(ecb, household);
    }
}
```

Notes:
- To trigger initialization systems, create entities with the module-expected components (e.g., Created tag, PrefabRef on instances) — the parallel IJobChunk-based systems will fill remaining fields.
- Inside jobs prefer the supplied ComponentLookup/BufferLookup overloads and CitizenUtils helpers to avoid extra allocations and to remain Burst-compatible.
- When adding/removing membership or pets, use the provided removal systems or follow their patterns (use Deleted tags) to keep buffers consistent.

---

## Game.City (City module)

This module provides compact, ECS-friendly types, enums, buffers and a few systems for city-wide state, options, modifiers, services, economy, statistics, taxation, tourism and XP in Cities: Skylines 2. It’s focused on serializable game state for use with Unity DOTS/EntityManager and Colossal.Serialization (IWriter/IReader), with attention to version-aware Deserialize logic for backward compatibility.

Key contents
- City metadata & options
  - City component: bitmask of CityOption flags (e.g., ImportOutsideServices, LeftHandTraffic, etc.).
  - CityUtils: helpers to check/interpret option bitmasks and to apply CityModifier buffers to values.
  - CityConfigurationSystem: stores/serializes city config (name, theme, camera, toggles, required prefabs) and controls overrides at preload/load.
- Modifiers, statistics and telemetry
  - CityModifier buffer element: delta and percent modifiers with a CityModifierType index.
  - CityStatistic buffer element + StatisticType/StatisticCollectionType/StatisticUnitType enums and StatisticsEvent for telemetry and sampling.
  - StatisticParameter: small IComponentData wrapper for integer statistic parameters.
- Services, fees & economy
  - Enums: CityService, ExpenseSource, IncomeSource, PassengerType, PlayerResource, TaxRate.
  - ServiceFee and ServiceImportBudget buffer elements for per-resource fees/budgets.
  - PlayerMoney struct: clamped integer money value with an m_Unlimited flag and helper methods.
  - ServiceFeeCollector / CityServiceUpkeep: compact ECS types for upkeep/accounting.
- Taxation
  - TaxRates buffer element (TaxRate enum indices) for dynamic per-entity tax tables.
- Tourism & XP
  - Tourism component: tracks current/average tourists, attractiveness, lodging; supports defaults and serialization.
  - XP component and XPRewardFlags: XP totals, historical maxima and reward flags; versioned serialization.
- Dev tree / progression
  - DevTreePoints, DevTreeSystem and MilestoneLevel/MilestoneReachedEvent: manage dev tree points, milestone state and purchases/unlocks (system resolves node prefabs/entities internally).
- Utility and compatibility patterns
  - Buffer element types implement IBufferElementData and (where needed) ISerializable/IDefaultSerializable, with Deserialize honoring reader.context.version for compatibility.
  - Many enums include Count/Invalid sentinels for safe sizing/iteration.
  - CityUtils includes a helper to compute maximum workplace workers for a city service from prefab data + installed upgrades.
- Systems
  - CityConfigurationSystem: central city config, name/camera restore, option overrides before preload.
  - DevTreeSystem: manage points, milestone events and purchases.

Overall: lightweight, serializable ECS building blocks and a couple of manager systems to represent and mutate city-wide settings, modifiers, economy/taxes, tourism and XP while keeping save/load compatibility.

### Usage example
```csharp
using Unity.Entities;
using Unity.Mathematics;
using Game.City;

// Get world singletons / systems
var world = World.DefaultGameObjectInjectionWorld;
var em = world.EntityManager;
var cityConfig = world.GetOrCreateSystemManaged<Game.City.CityConfigurationSystem>();
var devTree = world.GetOrCreateSystemManaged<Game.City.DevTreeSystem>();

// --- Create a city entity with options ---
var cityEntity = em.CreateEntity();
var cityComp = new Game.City.City { m_OptionMask = 0u };
// Turn on ImportOutsideServices option
cityComp.m_OptionMask |= (1u << (int)Game.City.CityOption.ImportOutsideServices);
em.AddComponentData(cityEntity, cityComp);

// Check an option
var readCity = em.GetComponentData<Game.City.City>(cityEntity);
bool importAllowed = Game.City.CityUtils.CheckOption(readCity, Game.City.CityOption.ImportOutsideServices);

// --- Apply city modifiers ---
var modifiers = em.AddBuffer<Game.City.CityModifier>(cityEntity);
modifiers.Add(new Game.City.CityModifier { m_Delta = new float2(10f, 0.10f) }); // +10 then +10%
float price = 100f;
Game.City.CityUtils.ApplyModifier(ref price, modifiers, Game.City.CityModifierType.Attractiveness);

// --- Player money and fees ---
var pm = new Game.PlayerMoney(10000);
pm.Add(5000);
pm.m_Unlimited = false;
int balance = pm.money; // clamps and respects unlimited flag

var feesEntity = em.CreateEntity();
var feeBuf = em.AddBuffer<Game.City.ServiceFee>(feesEntity);
feeBuf.Add(new Game.City.ServiceFee {
    m_Resource = Game.City.PlayerResource.Water,
    m_Fee = 0.1f
});

// --- Tax rates buffer ---
var taxEntity = em.CreateEntity();
var taxBuf = em.AddBuffer<Game.City.TaxRates>(taxEntity);
taxBuf.Add(new Game.City.TaxRates { m_TaxRate = 100 }); // interpretation by game logic

// --- Tourism & XP ---
var statsEntity = em.CreateEntity();
var tourism = new Game.City.Tourism();
tourism.SetDefaults(default); // real code provides Context
tourism.m_CurrentTourists = 250;
tourism.m_AverageTourists = 200;
tourism.m_Attractiveness = 80;
tourism.m_Lodging = new int2(120, 95);
em.AddComponentData(statsEntity, tourism);

var xp = new Game.City.XP {
    m_XP = 420,
    m_MaximumPopulation = 5000,
    m_MaximumIncome = 60000,
    m_XPRewardRecord = Game.City.XPRewardFlags.ElectricityGridBuilt
};
em.AddComponentData(statsEntity, xp);

// --- Dev tree usage ---
devTree.points = 5;
// devTree.Purchase(nodePrefab) or devTree.Purchase(nodeEntity) when available

// --- City configuration overrides (before preload) ---
cityConfig.overrideCityName = "MyModCity";
cityConfig.overrideLeftHandTraffic = true;
cityConfig.overrideLoadedOptions = false; // allow loaded options to apply

// Note: serialization and interactions with Prefab/Camera systems require actual game context.
// When serializing types in this module, use the game's IWriter/IReader and respect reader.context.version for compatibility.
```

---

## Game.Common

A lightweight utility module of small ECS components, helper types, and coordinating systems used across the game's DOTS pipeline. Game.Common provides building blocks for deterministic randomness, simple serializable data, many 1-byte tag/marker components, named barrier systems for safe command-buffer ordering, a Prepare/CleanUp handoff pattern for device-native lists and job handles, a high-performance raycast subsystem, quad-tree / bounds helpers, localization index utilities, and a few convenience utilities (CommonUtils, ExclusiveGroundCollision, enum/inspector helpers, etc.).

Key features (concise):
- Marker/tag components: many 1-byte tags (Created, Deleted, Applied, BatchesUpdated, EffectsUpdated, Event, PathfindUpdated, Overridden, Native, Terrain, Updated, etc.) intended for presence/absence queries and structural filtering. StructLayout(Size = 1) used to avoid zero-sized semantics.
- Small data components: Owner (Entity ref), PointOfInterest (position + validity), Target (serializable Entity ref), Destroyed (event/cleared), BufferedEntity, TimeData (time-of-day metadata), etc. Several support Colossal serialization and Preserve attributes for IL2CPP/AOT.
- Barrier systems: named SafeCommandBufferSystem-derived barriers (ModificationBarrier1..5, 2B/3/4B/4, ModificationEndBarrier, AudioEndBarrier, EndFrameBarrier) used as deterministic sync/playback points for command buffers and job handles.
- Phase coordination systems: ModificationSystem drives the modification-phase sequence; NativeSystem toggles Native tags per-load context; AllowAudioEndBarrier ensures AudioEndBarrier usage; EndFrameBarrier coordinates end-of-frame dependencies.
- Prepare/CleanUp pattern: PrepareCleanUpSystem builds NativeList<Entity> with Allocator.TempJob and a producer JobHandle, forwards them + handle to CleanUpSystem which completes handles, destroys entities, and removes markers (ownership/disposal semantics expected).
- Randomness: RandomSeed (32-bit) providing per-index Random substreams; PseudoRandomSeed (16-bit) with reason constants to derive many small deterministic RNGs per-entity.
- Localization helpers: RandomLocalizationIndex buffer element and a RandomLocalizationInitializeSystem to seed per-entity localization indices using RandomSeed.
- Spatial helpers: QuadTreeBoundsXZ (XZ AABB with masks and LOD), DebugIterator for gizmo drawing, bounds utilities.
- Raycasting subsystem: RaycastInput (Line3.Segment + offsets, masks, flags), RaycastHit/RaycastResult with deterministic merging rules, RaycastSystem that batches/submits many inputs and returns results (AddInput, GetResult/CompleteRaycast).
- Utilities: CommonUtils (GetRandomEntity from archetype chunks with overloads that fill component data, Swap/SwapBits, GetBoundsMask, ExclusiveGroundCollision), EnumValueAttribute for editor display, and small helpers for safe random selection and job-friendly operations.
- Patterns/notes: Many methods/ctors decorated with [Preserve]; NoInlining used where stable boundaries matter. Jobs/Burst are used widely — systems provide JobHandles or complete them; callers must honor Allocator/ownership rules for NativeList<>

Overall: Game.Common supplies tiny, heavily reused primitives that coordinate entity lifecycle, deterministic randomness, spatial queries, and ordered command-buffer playback across systems in a predictable, job- and Burst-friendly manner.

### Usage example
```csharp
using Unity.Burst;
using Unity.Collections;
using Unity.Entities;
using Unity.Mathematics;
using UnityEngine;
using Game.Common;

public partial class ExampleModSystem : SystemBase
{
    protected override void OnUpdate()
    {
        var em = EntityManager;
        // 1) Create a simple POI entity tagged as "Created" with an Owner and PointOfInterest
        var archetype = em.CreateArchetype(typeof(Created), typeof(Owner), typeof(PointOfInterest));
        Entity e = em.CreateEntity(archetype);
        em.SetComponentData(e, new Owner(Entity.Null));
        em.SetComponentData(e, new PointOfInterest { m_Position = new float3(10f, 0f, 20f), m_IsValid = true });

        // 2) Query POIs and pick one randomly using CommonUtils.GetRandomEntity
        var query = GetEntityQuery(ComponentType.ReadOnly<PointOfInterest>());
        var chunks = query.CreateArchetypeChunkArray(Allocator.TempJob);
        if (chunks.Length > 0)
        {
            // create RNG (seed with UnityEngine.Random for demo; prefer deterministic RandomSeed in production)
            var rng = new Unity.Mathematics.Random((uint)UnityEngine.Random.Range(1, int.MaxValue));
            var entityType = GetEntityTypeHandle();
            var poiHandle = GetComponentTypeHandle<PointOfInterest>(isReadOnly: true);

            // Overload fills out the component data for the chosen entity
            PointOfInterest chosenPoi;
            Entity randomEntity = CommonUtils.GetRandomEntity(ref rng, chunks, entityType, poiHandle, out chosenPoi);

            if (randomEntity != Entity.Null && chosenPoi.m_IsValid)
            {
                Debug.Log($"Selected POI at {chosenPoi.m_Position}");
            }
        }
        chunks.Dispose();

        // 3) Use RandomSeed / PseudoRandomSeed for deterministic randomness
        var seed = RandomSeed.Next();
        var rng0 = seed.GetRandom(0);              // per-index substream
        var pseudo = new PseudoRandomSeed(12345);  // small per-entity seed
        var colorRand = pseudo.GetRandom(PseudoRandomSeed.kColorVariation);
        float hue = colorRand.NextFloat();

        // 4) Submit a raycast input to the RaycastSystem and read results later
        var raycastSystem = World.GetExistingSystemManaged<RaycastSystem>();
        if (raycastSystem != null)
        {
            var input = new RaycastInput
            {
                m_Line = new Colossal.Mathematics.Line3.Segment(new float3(0, 50, 0), new float3(0, -50, 0)),
                m_Offset = float3.zero,
                m_TypeMask = TypeMask.Terrain | TypeMask.StaticObjects,
                m_Flags = RaycastFlags.None
            };

            // context can be any object key you use to retrieve results
            object context = this; 
            raycastSystem.AddInput(context, input);

            // after the RaycastSystem has run (or call CompleteRaycast/ensure completion), obtain results:
            var results = raycastSystem.GetResult(context);
            for (int i = 0; i < results.Length; i++)
            {
                var res = results[i];
                if (res.m_Owner != Entity.Null)
                {
                    Debug.Log($"Ray hit owner {res.m_Owner} at {res.m_Hit.m_HitPosition}, dist={res.m_Hit.m_NormalizedDistance}");
                }
            }
        }

        // 5) Typical next steps (illustrative): schedule work that writes to NativeList<Entity> and forward the list +
        //    JobHandle to the PrepareCleanUpSystem / CleanUpSystem pair so entity destruction and marker removal happen safely.
        //    Also, systems requiring deterministic ordering should use the named ModificationBarrierX systems for command buffering.
    }
}
```

---

## Game.Companies

A collection of small, performance-oriented ECS types used by Cities: Skylines 2 to model company behavior, resources and workplace logistics. The module provides:

- Marker/tag components (empty structs with StructLayout(Size = 1)) to classify entities: CommercialCompany, IndustrialCompany, ExtractorCompany, ProcessingCompany, TransportCompany, OutsideTrader, ResourceSeller. These are used as WithAll/WithNone filters in ECS queries and are serialized via the game's empty-component support (IEmptySerializable / IEmptySerializable-like conventions).
- Data components (IComponentData + ISerializable) carrying per-entity state: CompanyData (per-company Random + brand entity), BuyingCompany / StorageCompany (last trade partner), Profitability, LodgingProvider, TransportCompanyData, ServiceCompanyData, ServiceAvailable, WorkProvider, StorageLimitData, FreeWorkplaces, Workplaces, TransportCompanyData, etc.
- Buffer element types (IBufferElementData + ISerializable) for lists/variable-length data attached to entities: Employee, TradeCost, StorageTransferRequest. These are used for employees, per-resource trade costs, and queued transfer requests.
- Resource/transfer primitives: ResourceBuyer, ResourceExporter, StorageTransfer and StorageTransferFlags, StorageTransferRequest. Resources are serialized compactly by mapping to sbyte indices via EconomyUtils.GetResourceIndex/GetResource.
- Utility behaviors: FreeWorkplaces (byte-per-education-level free slots with refresh/best-fit helpers), Workplaces (int-per-education-level counts and accumulation), StorageLimitData (limit multiplier + combine), TradeCost (per-resource buy/sell costs + last request time).
- Serialization/versioning patterns: most types implement Colossal.Serialization.Entities.ISerializable-like methods (Serialize/Deserialize) and often check reader.context.version or reader.context.format flags to preserve compatibility across save versions. Entity fields rely on the engine’s reader/writer to remap entity handles during load. Many resource enums are compacted to sbyte indices (watch index ranges).

Design/usage notes:
- Components are blittable, minimal, and intended for use inside ECS systems and jobs. Prefer modifying whole struct instances via EntityManager/ComponentData APIs or within SystemBase jobs to avoid copies/race conditions.
- Marker components are intentionally empty but sized to 1 byte to ensure stable native layout and integration with the custom serializer.
- When adding new fields or changing serialization order, respect version checks or append-only serialization to preserve save compatibility.
- EconomyUtils is the canonical helper for converting Resource enum ↔ compact indices; Ensure custom additions remain within sbyte range if you rely on these serialized forms.

### Usage example
```csharp
// Minimal example: create a company entity, tag it as a transport company,
// set company data, add employees buffer and a storage transfer request.

using Unity.Entities;
using Unity.Mathematics;
using Game.Companies;
using Game.Economy;

public class CompanyExample
{
    public void CreateCompany(World world, EntityManager em)
    {
        // Create entity archetype with a few components
        var archetype = em.CreateArchetype(
            typeof(TransportCompany),            // tag
            typeof(CompanyData),                 // per-company RNG + brand
            typeof(TransportCompanyData),        // max transports
            typeof(WorkProvider)                 // worker slots + notifications
        );

        var company = em.CreateEntity(archetype);

        // Initialize CompanyData
        var cd = new CompanyData {
            m_RandomSeed = new Unity.Mathematics.Random(12345u),
            m_Brand = Entity.Null
        };
        em.SetComponentData(company, cd);

        // Set transport limits
        em.SetComponentData(company, new TransportCompanyData { m_MaxTransports = 8 });

        // Add WorkProvider and set worker capacity
        em.SetComponentData(company, new WorkProvider {
            m_MaxWorkers = 24,
            m_UneducatedCooldown = 0,
            m_EducatedCooldown = 0,
            m_UneducatedNotificationEntity = Entity.Null,
            m_EducatedNotificationEntity = Entity.Null,
            m_EfficiencyCooldown = 0
        });

        // Add employee buffer
        var empBuffer = em.AddBuffer<Employee>(company);
        // Add an employee entry
        empBuffer.Add(new Employee { m_Worker = Entity.Null, m_Level = 2 });

        // Add a storage transfer request buffer and push a request
        var reqBuffer = em.AddBuffer<StorageTransferRequest>(company);
        var req = new StorageTransferRequest {
            m_Flags = StorageTransferFlags.Car,
            m_Resource = EconomyUtils.GetResource((sbyte)0), // map index to Resource
            m_Amount = 200,
            m_Target = Entity.Null
        };
        reqBuffer.Add(req);

        // Example: set a FreeWorkplaces value on some building/company entity (if used)
        var free = new FreeWorkplaces(new Workplaces {
            m_Uneducated = 3,
            m_PoorlyEducated = 2,
            m_Educated = 4,
            m_WellEducated = 1,
            m_HighlyEducated = 0
        });
        // free.Refresh(...) would be called from a system when employee buffers / capacity change
    }
}
```

This overview should help you locate the relevant struct for your modding task (tag vs. data vs. buffer), understand common serialization patterns and version guards, and show typical ECS usage (add/set component data, add buffers, use EconomyUtils for resource encoding).

---

## Game.Creatures

This module (including the "Creatures" batch) contains the core ECS components, buffer elements, flags, utilities and systems that implement creature behaviour in Cities: Skylines 2 — humans, animals and pets. It is designed for DOTS/Burst usage: most types are small, blittable value types (IComponentData / IBufferElementData / IQueryTypeParameter), many implement Colossal/engine serialization interfaces and contain version-aware Deserialize paths so save compatibility is preserved.

Main responsibilities and contents:
- Marker components: tiny tags such as AmbienceEmitter and CreatureSpawner used only to mark entities for systems.
- Per-entity state: components like Creature, Human, Animal, Domesticated, CurrentVehicle and Divert hold compact flags, timers, and entity references describing an entity's current state and relationships. Corresponding [Flags] enums (HumanFlags, AnimalFlags, CreatureVehicleFlags, etc.) provide efficient bitfield state.
- Navigation and lane data: HumanNavigation, AnimalNavigation, HumanCurrentLane, AnimalCurrentLane store navigation targets, directions, transform/animation state, lane/curve positions and queue area information. These components are optimized for jobs and include serialization guarded by save-version checks.
- Grouping: GroupCreature buffer elements and GroupMember components represent group membership. GroupSystem assembles groups, chooses leaders, updates buffers and clears path state when needed.
- High-level systems:
  - InitializeSystem: initializes newly created/updated creatures (positions, navigation, lane state, spawn selection and per-creature flags).
  - ReferencesSystem: keeps entity-level references in sync (owned creature buffers, current transport, vehicle passengers, lane object buffers, moving search tree) and handles cleanup on deletion.
  - TripResetSystem: processes ResetTrip components to reroute or reset trips, clears path flags, updates PathOwner/Divert/Target and re-queues TripSource when appropriate.
- Utilities: CreatureUtils provides many helpers used by systems/jobs — lane/curve math (Bezier), triangle/area targeting, braking and navigation size calculations, queue-area merging, path-start/enter fixes, activity/location selection (including vehicle door/activity locations), and other AI/pathfinding helpers.
- Serialization & versioning: many components implement ISerializable/IEmptySerializable and use reader.context.version checks to maintain backwards compatibility when fields changed.
- DOTS considerations: systems are Burst-compiled and use ComponentLookup/BufferLookup/TypeHandles; structural changes are deferred via ModificationBarrier/EntityCommandBuffer. Jobs must avoid managed objects.

Design guidance for modders:
- Prefer bitwise checks for flags: (flags & Flag.Value) != 0.
- Use ComponentLookup/BufferLookup in jobs and schedule structural changes through ECB/ModificationBarrier.
- Interact with CreatureUtils and the provided components; the engine systems will perform the heavy lifting (initialization, reference maintenance and trip resets).
- When adding/removing creature components, be aware the provided systems may run on Created/Updated/Deleted queries and respond automatically.

### Usage example
```csharp
using Unity.Entities;
using Unity.Mathematics;
using Game.Creatures;
using Colossal.Mathematics; // for Sphere3 if needed

public static class CreatureExample
{
    public static void SetupExampleEntities()
    {
        var em = World.DefaultGameObjectInjectionWorld.EntityManager;

        // Create a spawner entity (marker)
        var spawnerArchetype = em.CreateArchetype(
            typeof(CreatureSpawner),
            typeof(Unity.Transforms.LocalToWorld)
        );
        Entity spawner = em.CreateEntity(spawnerArchetype);
        em.AddComponentData(spawner, new AmbienceEmitter()); // optional marker

        // Create a human creature with navigation and lane state
        var humanArchetype = em.CreateArchetype(
            typeof(Human),
            typeof(HumanNavigation),
            typeof(HumanCurrentLane),
            typeof(Creature) // core creature marker/state
        );
        Entity human = em.CreateEntity(humanArchetype);

        // Set compact human flags
        em.SetComponentData(human, new Human(HumanFlags.Waiting | HumanFlags.Happy));

        // Initialize HumanNavigation toward a world target
        var nav = new HumanNavigation
        {
            m_TargetPosition = new float3(100f, 0f, 200f),
            m_TargetDirection = new float2(0f, 0f),
            m_MaxSpeed = 2.0f,
            m_TransformState = TransformState.Default,
            m_LastActivity = 0,
            m_TargetActivity = 0
        };
        em.SetComponentData(human, nav);

        // Initialize current lane with a queue spherical area
        var queueArea = new Sphere3 { position = new float3(10f, 0f, 5f), radius = 2.5f };
        var currentLane = new HumanCurrentLane(CreatureLaneFlags.None)
        {
            m_QueueArea = queueArea,
            m_QueueEntity = Entity.Null
        };
        em.SetComponentData(human, currentLane);

        // Create a household owner and a pet, associate them and set pet flags
        Entity household = em.CreateEntity(); // owner entity
        Entity pet = em.CreateEntity(typeof(Pet), typeof(Creature));
        em.SetComponentData(pet, new Pet(household));

        // Ensure household has OwnedCreature buffer and add pet reference
        var owned = em.HasComponent<OwnedCreature>(household) ? em.GetBuffer<OwnedCreature>(household) : em.AddBuffer<OwnedCreature>(household);
        owned.Add(new OwnedCreature(pet));

        // Set pet behavior flag
        var petComp = em.GetComponentData<Pet>(pet);
        petComp.m_Flags |= PetFlags.Hangaround;
        em.SetComponentData(pet, petComp);

        // Mark that human should have its trip reset (TripResetSystem will process this)
        var reset = new ResetTrip
        {
            m_Creature = human,
            m_Source = Entity.Null,
            m_Target = Entity.Null,
            m_DivertTarget = Entity.Null,
            m_NextTarget = Entity.Null,
            m_Arrived = Entity.Null,
            m_TravelResource = default,
            m_DivertResource = default,
            m_NextResource = default,
            m_ResidentFlags = default,
            m_TravelData = 0,
            m_DivertData = 0,
            m_NextData = 0,
            m_Delay = 0u,
            m_TravelPurpose = default,
            m_DivertPurpose = default,
            m_NextPurpose = default,
            m_HasDivertPath = false
        };
        em.AddComponentData(human, reset);

        // Optionally add a Stumbling tag to make the pet stumble (IEmptySerializable)
        em.AddComponent<Stumbling>(pet);

        // Systems InitializeSystem, ReferencesSystem and TripResetSystem will run automatically
        // and will use the component data and CreatureUtils helpers to manage state.
    }
}
```

---

## Game.Debug

A comprehensive in-engine debug module used by Cities: Skylines 2 that provides:
- Base infrastructure for reflection-discovered debug UI and togglable debug systems:
  - BaseDebugSystem for registering Option toggles and integrating job dependencies.
  - DebugContainerAttribute / DebugTabAttribute / DebugWatchDepsAttribute and DebugWatchValue/DebugWatchOnly attributes for auto-discovery and preservation.
  - EndFrameBarrier for safe end-of-frame structural changes.
- A large suite of job-friendly visualization systems that sample simulation data and emit batched gizmo draws:
  - AreaDebugSystem, NetDebugSystem, NavigationDebugSystem, PathDebugSystem, PathfindDebugSystem, PollutionDebugSystem, LandValueDebugSystem, LaneDebugSystem, TerrainDebugSystem, WaterDebugSystem, GroundWaterDebugSystem, BuildableAreaDebugSystem, AvailabilityDebugSystem, CoverageDebugSystem, and many more.
  - Most visualize maps/grids, edge/cell/route geometry, lane reservations, search-tree/quadtree contents, pollution/noise/ground-water maps, and per-entity or per-cell metrics.
  - Jobs are Burst-compiled (IJobChunk / IJobParallelFor / IJob), use ComponentTypeHandle/BufferTypeHandle/ComponentLookup, obtain a GizmosSystem.GizmoBatcher and register readers/writers to ensure thread-safe drawing.
- Debug-watch and sampling utilities:
  - DebugWatchSystem for collecting annotated member history and distributions, exporting watches to JSON, and driving the watch UI.
  - DebugWatchDistribution: a NativeQueue-backed distribution sampler that supports writer JobHandle registration, scheduled clears, and safe main-thread reads.
- Debug UI providers and helpers:
  - Attribute-discovered debug tabs such as AudioDebugUI, CameraDebugUI, LocalizationDebugUI, LogsDebugUI, TestsDebugUI, ThumbnailsDebugUI, WatchersDebugUI, ProfilerMetricsDebugUI, and more. These build widgets (Values, Foldouts, Buttons, Fields) for runtime control.
  - Small widgets/helpers like IntInputField and extensions for ObservableList<T>.
- Utilities for development:
  - ComponentDebugUtils for inspecting archetypes/chunks, ConsoleWindow / WinConsole helpers to allocate native consoles and redirect output, and testing helpers (e.g., test scenario helpers or forced exception throwers).
- Common patterns & cautions:
  - Systems are typically disabled by default — enable explicitly (system.Enabled = true) to schedule visualizations.
  - All drawing from worker threads uses GizmosSystem.GetGizmosBatcher plus AddGizmosBatcherWriter and proper JobHandle wiring.
  - Always Complete JobHandles before reading native collections on the main thread. Dispose persistent native containers when finished.
  - Intended for development/debug builds — many visualizations are expensive, access internal engine data, and may rely on unsafe APIs. Use with care in mods/releases.

### Usage example
```csharp
// C# (Unity ECS) example: enable debug systems, toggle an option, use a DebugWatchDistribution and open a console.
using Unity.Entities;
using Unity.Jobs;
using Unity.Collections;
using Game.Debug;

public static class DebugExample
{
    public static void Run()
    {
        var world = World.DefaultGameObjectInjectionWorld;
        if (world == null) return;

        // 1) Enable several visualization systems (they are disabled by default).
        var areaSys = world.GetOrCreateSystemManaged<Game.Debug.AreaDebugSystem>();
        var buildableSys = world.GetOrCreateSystemManaged<Game.Debug.BuildableAreaDebugSystem>();
        var netSys = world.GetOrCreateSystemManaged<Game.Debug.NetDebugSystem>();
        if (areaSys != null) areaSys.Enabled = true;
        if (buildableSys != null) buildableSys.Enabled = true;
        if (netSys != null) netSys.Enabled = true;

        // 2) Toggle a specific Option on an availability/area system (options are exposed via BaseDebugSystem.options).
        var availSys = world.GetExistingSystemManaged<Game.Debug.AvailabilityDebugSystem>();
        if (availSys != null)
        {
            var opt = availSys.options?.Find(o => o.name != null && o.name.Contains("Water"));
            if (opt != null) opt.enabled = true;
            availSys.Enabled = true;
        }

        // 3) Use DebugWatchDistribution to collect samples written by jobs.
        var dist = new DebugWatchDistribution(persistent: true, relative: false);
        dist.Enable();

        // Suppose some producer job wrote samples and produced a JobHandle called producerHandle.
        JobHandle producerHandle = default; // replace with real producer job handle
        dist.AddWriter(producerHandle);

        // Request the queue and ask for it to be cleared after read; get back a dependency handle.
        JobHandle deps;
        var queue = dist.GetQueue(clear: true, out deps);
        // Must complete deps (which includes producers + clear) before accessing the queue on main thread.
        deps.Complete();

        while (queue.TryDequeue(out int sample))
        {
            UnityEngine.Debug.Log($"DebugWatch sample: {sample}");
        }

        dist.Dispose(); // completes outstanding deps and disposes resources

        // 4) Allocate a debug console (Windows helper). Use the module's console helper you have available.
#if UNITY_STANDALONE_WIN
        var console = new Game.Debug.ConsoleWindow("Mod Debug Console", attachConsole: true);
        try
        {
            Game.Debug.ConsoleWindow.SetColor(Game.Debug.ConsoleWindow.FOREGROUND_GREEN | Game.Debug.ConsoleWindow.FOREGROUND_INTENSITY);
            System.Console.WriteLine("Debug console ready.");
        }
        finally
        {
            console.Dispose();
        }
#endif

        // 5) Read a metric exposed on a system after it has updated (e.g., after a frame):
        if (buildableSys != null)
        {
            // buildableArea is updated by the system when enabled; read with caution (timing dependent).
            float avg = buildableSys.buildableArea;
            UnityEngine.Debug.Log($"Average buildable fraction: {avg:F2}");
        }
    }
}
```

---

## Game.Dlc (DLC identifiers and platform mapping helpers)

Summary
This module provides the game's known DLC identifiers and small platform mapping helpers:

- Dlc (static class): a central static holder of DlcId fields for known DLCs (e.g., LandmarkBuildings, SanFranciscoSet, CS1TreasureHunt, BridgesAndPorts) and a numeric constant BridgesAndPortsId = 5. The readonly DlcId fields are populated by the engine at runtime (may be null before registration) and are the preferred references when APIs accept a DlcId. The Dlc fields are annotated with attributes used by the engine's DLC registration system.

- GdkDlcsMapping: maps in-game DLC enum entries to Microsoft GDK/Xbox product IDs. The constructor registers mappings (LandmarkBuildings -> "9PM19MNT8GXH", SanFranciscoSet -> "9NLWRT4D535J", BridgesAndPorts -> "9NFGBRJQFNB3") via the base GdkDlcMapper. Marked with [Preserve] to avoid stripping.

- PdxSdkDlcsMapping: registers a list of legacy content IDs for the CS1 Treasure Hunt DLC with the PDX SDK mapper (IDs like "BusCO01", "TramCarCO01", "FountainPlaza01"). Also preserved to survive IL2CPP/code stripping. Both mapping classes simply call the inherited Map method in their constructors.

Notes for modders:
- Guard against null DlcId fields until the engine has registered DLCs (check at safe initialization points).
- Use the DlcId fields with APIs that accept DlcId; use the BridgesAndPortsId constant only when an int is required.
- Instantiate the mapping classes (or ensure their constructors run) to register platform-specific mappings so platform services can resolve store/product IDs or PDX content IDs.

### Usage example
```csharp
using UnityEngine;
using UnityEngine.Scripting;
using Colossal.PSI.Common;
using Colossal.PSI.MicrosoftGdk;
using Colossal.PSI.PdxSdk;
using Game.Dlc;

public class DlcExample : MonoBehaviour
{
    void Start()
    {
        // 1) Check numeric ID and DlcId availability
        int bridgesRaw = Dlc.BridgesAndPortsId;
        Debug.Log("Bridges & Ports raw ID: " + bridgesRaw);

        DlcId bridges = Dlc.BridgesAndPorts;
        if (bridges != null)
        {
            Debug.Log("Bridges & Ports DlcId available.");
            // Example: if (bridges.IsInstalled) { ... } // depending on DlcId API
        }
        else
        {
            Debug.Log("Bridges & Ports DlcId not yet registered.");
        }

        // 2) Register platform mappings so external services can resolve DLC -> product/content IDs
        // Creating instances calls the base Map method in their constructors.
        var gdkMapping = new GdkDlcsMapping();       // registers Microsoft/Xbox product IDs
        var pdxMapping = new PdxSdkDlcsMapping();    // registers CS1 Treasure Hunt content IDs

        // After registration, platform integration code can resolve product/content IDs for DLCs.
    }
}
```

---

## Game.Economy (Economy module)

Summary
- This module contains the core economy types and helper utilities used by Cities: Skylines 2. It centers on a bitmask-style Resource enum (ulong-backed) and a large static helper class EconomyUtils that provides conversion helpers, price/weight lookups, transport cost and production/profit calculations, and buffer/serialization helpers for DOTS (DynamicBuffer, ComponentLookup, EntityManager, etc.).
- Key types:
  - Resource (enum): power-of-two values for every resource (Money, Grain, Oil, Metals, Services, Garbage, Last, All). Intended to be used as bit flags.
  - EconomyUtils (static utility): resource index mapping, trade/transport cost builders, resource name/color/price/weight accessors, storage buffer helpers (Resources buffer type), company/household income & production/profit estimators, workforce/wage helpers, and masks/test helpers (IsIndustrialResource, IsCommercialResource, etc.). Important constants: kCompanyUpdatesPerDay = 256 and ResourceCount.
  - Resources (IBufferElementData + ISerializable): one resource/amount pair intended for DynamicBuffer; provides compact sbyte index + int serialization and compatibility clamps for older save versions (non-money resources clamped).
  - ResourceInfo (IComponentData + ISerializable): a component carrying Resource, price and trade distance; serialized as sbyte index + floats.
  - ResourceIterator: small value-type iterator for stepping single-bit Resource flags up to Resource.Last.
  - ResourceArrayAttribute: marker attribute for resource-array members.
  - ResourceInEditor (enum): editor-facing index enum (serializable) with Count sentinel.
- Usage notes and caveats:
  - Resources are used as bitmasks—use EconomyUtils.GetResource(index) or explicit single-value Resource constants rather than raw ints. EconomyUtils.GetResourceIndex returns an sbyte index for serialization; invalid or multi-bit values yield -1.
  - Many helpers expect DOTS types (DynamicBuffer<>, ComponentLookup<>, BufferLookup<>, EntityManager, NativeCollections). Call them from a system/world context or adapt to non-DOTS code.
  - Name/FixedString variants: GetNameFixed returns FixedString32Bytes for allocation-free job usage.
  - Serialization: Resources and ResourceInfo write resource as sbyte index. Older saves may clamp negative/excess amounts for non-money resources.
  - Resource.All sets all bits of ulong — be careful when using it.
- Typical responsibilities covered:
  - Mapping editor indices to runtime Resource flags.
  - Reading resource metadata (price, weight, color) via ResourcePrefabs / ResourceData.
  - Computing transport costs and trade costs for processes.
  - Estimating production per day and company profit (both static estimates and instance-based using employees).
  - Managing DynamicBuffer<Resources> entries (get/add/set).
  - Iterating resource flags via ResourceIterator.

### Usage example
```csharp
// Example usage snippets that illustrate common tasks.
// Requires appropriate DOTS/system context for EntityManager / ComponentLookup usage.

using Game.Economy;
using UnityEngine;
using Unity.Entities;

// 1) Iterate defined single-bit resources up to Resource.Last
var it = ResourceIterator.GetIterator();
while (it.Next())
{
    Resource r = it.resource;
    Debug.Log($"Resource flag: {r} name={EconomyUtils.GetName(r)}");
}

// 2) Read a resource's market price & color (EntityManager version)
Resource res = Resource.Grain;
float marketPrice = EconomyUtils.GetMarketPrice(res, resourcePrefabs, entityManager);
Color resColor = EconomyUtils.GetResourceColor(res);
Debug.Log($"Market price for {EconomyUtils.GetName(res)} = {marketPrice}, color={resColor}");

// 3) Compute transport cost for moving 120 units of Oil over 3000 units distance
float weight = EconomyUtils.GetWeight(entityManager, Resource.Oil, resourcePrefabs);
int transportCost = EconomyUtils.GetTransportCost(distance: 3000f, resource: Resource.Oil, amount: 120, weight: weight);
Debug.Log($"Transport cost for oil shipment = {transportCost}");

// 4) Estimate company production & profit per day (static estimate)
int estimatedProduction = EconomyUtils.GetCompanyProductionPerDay(
    buildingEfficiency: 0.9f,
    workerAmount: 40,
    level: 2,
    isIndustrial: true,
    workplaceData: workplaceData,      // from prefab/component in your context
    processData: processData,          // the IndustrialProcessData for the building process
    resourceData: resourceData,        // ResourceData for the produced resource
    economyParameters: economyParams
);
int estimatedProfit = EconomyUtils.GetCompanyProfitPerDay(
    buildingEfficiency: 0.9f,
    isIndustrial: true,
    employees: employeeBuffer,        // DynamicBuffer<Employee> for the instance (or pass workerAmount variant)
    processData: processData,
    resourcePrefabs: resourcePrefabs,
    resourceDatas: ref resourceDataLookup,
    citizens: ref citizenLookup,
    economyParameters: ref economyParams
);
Debug.Log($"Est. production/day = {estimatedProduction}, est. profit/day = {estimatedProfit}");

// 5) Manage a DynamicBuffer<Resources> (add/get amount)
EconomyUtils.AddResources(Resource.Wood, 500, refBuffer); // adds or creates entry
int woodAmount = EconomyUtils.GetResources(Resource.Wood, refBuffer);
EconomyUtils.SetResources(Resource.Wood, refBuffer, 750);
```

This module is the primary entry point for resource metadata, transport/trade calculations and company/household economic estimations—use EconomyUtils for conversions and DOTS-aware helpers and treat Resource as a bitmask when building masks or iterating.

---

## Game.Effects (Effects module)

A compact overview of the Game.Effects module — the core effect/VFX/audio/light-source pipeline used by Cities: Skylines 2. This module implements discovery, enable/disable decisioning, indexing, culling, and rendering of effect sources in a DOTS-friendly, jobified fashion. Key responsibilities and components:

- Central controller
  - EffectControlSystem: scans owners, evaluates enablement (LOD/culling/prefab validity/flags), builds a contiguous NativeList<EnabledEffectData> of active effects, and coordinates many Burst jobs (chunk scanning, quadtree culling, enabled-action processing and resizing). Consumers obtain enabled data through GetEnabledData and must register readers/writers (AddEnabledDataReader / AddEnabledDataWriter) and manage JobHandles.

- Condition & caching helpers
  - EffectControlData: caches ComponentLookup/BufferLookup and implements deterministic logic used to decide whether a prefab effect should be active for a given owner (GetRandom, ShouldBeEnabled, GetRealOwner). Handles editor-container rules, selection, light vs non-light behavior, probability flags.

- Flag sampling
  - EffectFlagSystem: low-frequency sampler for TimeSystem/ClimateSystem that exposes EffectFlagData and IsEnabled(random, data, frame) to reproduce time/climate-dependent randomized enable windows.

- Spatial indexing / discovery
  - SearchSystem: keeps a NativeQuadTree of active sources, updates it via a Burst IJobChunk (UpdateSearchTreeJob), and exposes GetSearchTree/AddSearchTreeReader/AddSearchTreeWriter for safe multi-threaded access.

- Enabled-instance bookkeeping
  - EnabledEffect (buffer element) and EnabledEffectData (global list entry): plain-data types representing per-owner entries and the contiguous enabled-effects list. EnabledEffectFlags is a bitflag enum marking IsEnabled, IsVFX, IsLight, Deleted, OwnerUpdated, EnabledUpdated, WrongPrefab, etc.

- Finalization / cleanup
  - CompleteEnabledSystem: Burst job that finalizes per-frame enabled-data changes, removes disabled entries (RemoveAtSwapBack semantics), fixes swapped indices in owner DynamicBuffers, and enqueues VFX MoveIndex updates to keep mappings consistent.

- VFX runtime / GPU upload
  - VFXSystem: manages per-prefab VisualEffect instances and instance-data textures, maps enabled-index ↔ instance slot, consumes NativeQueue<VFXUpdateInfo> producers (GetSourceUpdateData), and schedules VFXTextureUpdateJob to write instance transforms/intensity into a float texture (3 rows: position+intensity, rotation, scale). Main-thread Texture2D.Apply is done after job completion.

- Light handling
  - LightCullingSystem: builds per-prefab light culling parameters, culls enabled punctual lights against the camera frustum using Burst, sorts/prioritizes visible lights, and writes compact HDRP punctual-light buffers for the renderer.

- Source update helpers
  - SourceUpdateData/SourceUpdateInfo/SourceUpdateType and VFXUpdateInfo/VFXUpdateType: small blittable structs used to enqueue thread-safe add/remove/move/wrong-prefab/snap events consumed by VFXSystem, LightCullingSystem, etc.

Concurrency & integration patterns (important for modders)
- Heavy use of Native containers and Burst jobs (NativeList, NativeQueue, NativeParallelHashMap, NativeQuadTree).
- Systems expose Get...Data(readOnly, out JobHandle) and Add...Reader/Add...Writer APIs. Always capture the returned JobHandle, Complete() it before main-thread access or chain it into your job dependencies. Register your writer/reader JobHandles with the system so the consumer waits appropriately.
- Enabled-effect indices may change because of RemoveAtSwapBack; consume VFX MoveIndex updates to keep mappings correct.
- PreDeserialize/PostDeserialize hooks and lazy reinitialization are used across loads.
- Types used inside jobs must be Burst-compatible and blittable; UnityEngine.Object usage (e.g., Transform) is limited to main-thread-only or via snapshot data.

When to use what
- Use EffectControlData.ShouldBeEnabled to apply the game's enable rules for a prefab and owner.
- Read enabled instances via EffectControlSystem.GetEnabledData(readOnly: true), and register readers via AddEnabledDataReader when scheduling jobs that consume the list.
- Produce VFX updates by writing to the queue returned by VFXSystem.GetSourceUpdateData() and register the JobHandle that wrote to it with VFXSystem.AddSourceUpdateWriter so VFXSystem waits and consumes the queue safely.

### Usage example
Example showing (1) using EffectControlData.ShouldBeEnabled inside a SystemBase, (2) safely reading enabled data on the main thread, and (3) producing VFX updates on the main thread and registering a completed writer.

```csharp
using Unity.Entities;
using Unity.Collections;
using Unity.Mathematics;
using Game.Effects;

// 1) Use EffectControlData.ShouldBeEnabled in a SystemBase
public partial class MyEffectCheckerSystem : SystemBase
{
    private EffectControlData m_EffectControl;

    protected override void OnCreate()
    {
        base.OnCreate();
        m_EffectControl = new EffectControlData(this); // caches lookups
    }

    protected override void OnUpdate()
    {
        // refresh lookups and runtime state each frame
        var flags = World.GetExistingSystemManaged<EffectFlagSystem>()?.GetData() ?? default;
        uint simFrame = (uint)Time.ElapsedFrames;
        Entity selected = Entity.Null; // set to actual selection if needed
        m_EffectControl.Update(this, flags, simFrame, selected);

        Entity owner = /* some owner entity */;
        Entity effectPrefab = /* effect prefab entity */;
        bool checkEnabled = true;
        bool isEditorContainer = false;

        if (m_EffectControl.ShouldBeEnabled(owner, effectPrefab, checkEnabled, isEditorContainer))
        {
            // The game's rules say this effect should be active for this owner.
        }
    }
}

// 2) Read enabled effects safely on main thread
void ReadEnabledEffectsOnMainThread(World world)
{
    var ecs = world.GetExistingSystemManaged<EffectControlSystem>();
    if (ecs == null) return;

    JobHandle deps;
    var enabledData = ecs.GetEnabledData(readOnly: true, out deps);

    // Ensure jobs producing enabledData have finished before reading
    deps.Complete();

    for (int i = 0; i < enabledData.Length; i++)
    {
        var ed = enabledData[i];
        // use ed.m_Owner, ed.m_Prefab, ed.m_Position, ed.m_Intensity, ...
    }
}

// 3) Enqueue a VFX update on the main thread and register a completed writer
void EnqueueVFXMainThread(World world, int ownerIndex, int effectIndex)
{
    var vfx = world.GetExistingSystemManaged<VFXSystem>();
    if (vfx == null) return;

    var queue = vfx.GetSourceUpdateData(); // returns NativeQueue<VFXUpdateInfo> (Allocator.TempJob)
    var info = new VFXUpdateInfo {
        m_Type = VFXUpdateType.Add,
        m_EnabledIndex = new int2(ownerIndex, effectIndex)
    };
    queue.Enqueue(info);

    // We wrote on main thread, so tell VFXSystem the writer is effectively completed
    vfx.AddSourceUpdateWriter(JobHandle.Completed);
    // VFXSystem will consume and dispose the queue on its next update
}
```

---

## Game.Events

A consolidated summary of the Game.Events ECS module used by Cities: Skylines 2 for creating, routing, aggregating and persisting in-game events (fires, floods, accidents, weather phenomena, crimes, meetings, health incidents, spectator sites, etc.).

Summary
- Purpose: provides the component types, buffer elements and systems that drive the game's event/incident pipeline and the event journal (runtime view + serialized journal entries). Producers create transient "event" entities with request components; module systems (Burst/jobs + EntityCommandBuffer/ModificationBarrier) aggregate/merge requests, convert them into persistent state on target entities, update per-event target buffers, create journal entries, and persist state via Colossal.Serialization-aware types.
- Common patterns:
  - Producers create an Event-tagged entity, add one or more request components (AddAccidentSite, AddCriminal, AddHealthProblem, Ignite, FaceWeather, Submerge, Spectate, Impact, WeatherPhenomenon, AddEventJournalData, etc.) and optionally a TargetElement buffer listing intended targets.
  - Dedicated systems run Burst jobs that aggregate requests per-target (merge flags, keep max severity/depth, dedupe), then use an EntityCommandBuffer (ModificationBarrierN) to perform structural edits (add/update persistent components and buffers) on the main thread safely.
  - Many payload structs/components implement ISerializable / IEmptySerializable for save/load compatibility and include version-aware Deserialize implementations.
- Key components and buffers (non-exhaustive):
  - Tag/marker components: Event, CalendarEvent, Crime, Fire, Flood, HealthEvent, SpectatorEvent, FindingEventParticipants, etc.
  - Persistent markers/state: AccidentSite (+AccidentSiteFlags), Criminal (+flags), HealthProblem (+flags), InDanger (+flags, expires), FacingWeather, Flooded, OnFire, InvolvedInAccident, SpectatorSite.
  - Request components: AddAccidentSite, AddCriminal, AddHealthProblem, Ignite, Impact, FaceWeather, Submerge, Spectate, AddEventJournalData, AddMeeting (via producer queue).
  - Support types: Duration, DangerLevel, DangerFlags, Endanger, TargetElement (DynamicBuffer used by many systems to record targets), EventJournalPending, EventJournalData (and EventJournalCityEffect), EventJournalEntry.
- Major systems and responsibilities:
  - InitializeSystem: expands Event prefabs into sub-events (ignite, damage, meetings, criminal/health requests, etc.), selects targets (RandomEventTargetJob), enforces concurrent limits, and emits trigger actions.
  - AddX Systems: AddAccidentSiteSystem, AddCriminalSystem, AddHealthProblemSystem, AddMeetingSystem — aggregate requests and create/merge persistent components and update event target/journal buffers.
  - EndangerSystem: consolidates Endanger requests into persistent InDanger states, sets flags that drive evacuation/behavior.
  - IgniteSystem / FaceWeatherSystem / ImpactSystem / SubmergeSystem / SpectateSystem: handle fire, weather-facing, impacts/vehicle reactions, flooding, and spectator site creation respectively. They aggregate per-target and create/update target state and journal entries.
  - EventJournalInitializeSystem & EventJournalSystem (IEventJournalSystem): create and manage JournalEvent entities, maintain a runtime eventJournal list, provide notifications (eventEntryAdded, eventEventDataChanged), and provide utilities to read tracked values.
  - Meeting subsystem: uses a NativeQueue producer/consumer pattern; AddMeetingSystem consumes queued requests and creates coordinated meeting events.
- Journal and city-effect tracking:
  - EventJournalData and EventJournalCityEffect buffers record tracked metrics (damages, casualties, attendants, crime/happiness/income changes, etc.). EventJournalUtils has helpers (IsValid, GetValue) to read those buffers.
  - Systems append AddEventJournalData entries as events affect buildings/targets; the journal system consolidates and exposes data to UI subscribers.
- Serialization and versioning:
  - Many components are serialized; some fields exist only for newer save versions (example: secured-frame in AccidentSite). Deserialize implementations check version to preserve compatibility.
- Modding notes / best practices:
  - Create events by making an Event-tagged entity and attach request components and TargetElement buffers. Systems will do the rest.
  - When producing events or modifying world state from jobs use an EntityCommandBuffer (ModificationBarrier produced by the barrier system). If you write into producer queues (AddMeetingSystem), call AddWriter with your job handle so consumer waits correctly.
  - Use ComponentLookup/BufferLookup inside jobs for reading; structural edits must go through the ECB.
  - Use EventJournalSystem (IEventJournalSystem) to read journal entries, subscribe to eventEntryAdded/eventEventDataChanged and prefer EventJournalUtils to extract tracked metrics.
  - Respect flags enums (AccidentSiteFlags, DangerFlags, CriminalFlags, HealthProblemFlags) and the semantics behind them.
  - If extending the target-selection or TypeHandles used by RandomEventTargetJob or other jobs, keep their TypeHandle/query composition consistent with existing code.
  - Be aware of deterministic randomness usage in InitializeSystem (seed derived from eventEntity.Index) and serialization versioning semantics.
- Typical flow:
  1. Produce an Event entity, add request components (e.g., Ignite, AddAccidentSite, AddCriminal), optionally populate TargetElement buffer.
  2. Module systems aggregate requests per-target in Burst jobs, dedupe/merge flags, pick max severity/depth, enqueue modifications via ECB.
  3. Persistent components/buffers are added/updated on targets (OnFire, AccidentSite, Criminal, Flooded, FacingWeather, InDanger, etc.), and journal entries/buffers are updated/created to record metrics.
  4. EventJournalSystem exposes runtime journal list and notifies subscribers; serialized components persist state across saves.

### Usage example
```csharp
// Simple example: create a transient Event entity, request an accident site and a criminal marker,
// and add a journal data entry. Systems in Game.Events will process these requests and convert
// them into persistent components on the target prefab (via the module's Add*Systems).

using Unity.Entities;
using Game.Events;

public static class EventProducerExample
{
    public static void SpawnAccidentWithJournal(EntityManager em, Entity targetPrefab)
    {
        // Create the event token and tag it
        Entity eventEnt = em.CreateEntity();
        em.AddComponent<Game.Common.Event>(eventEnt); // or em.AddComponent<Game.Events.Event>(eventEnt) depending on assembly alias

        // Make sure we have a TargetElement buffer (optional, many systems append into it)
        if (!em.HasComponent<TargetElement>(eventEnt))
            em.AddBuffer<TargetElement>(eventEnt);

        // Request an accident site for the target
        var addAccident = new AddAccidentSite {
            m_Event = eventEnt,
            m_Target = targetPrefab,
            m_Flags = AccidentSiteFlags.StageAccident | AccidentSiteFlags.RequirePolice
        };
        em.AddComponentData(eventEnt, addAccident);

        // Request a criminal marker associated with the same event
        var addCriminal = new AddCriminal {
            m_Event = eventEnt,
            m_Target = targetPrefab,
            m_Flags = 0 // set appropriate CriminalFlags if needed
        };
        em.AddComponentData(eventEnt, addCriminal);

        // Add a small journal entry request: track 1 casualty (EventDataTrackingType.Casualties)
        var journalReq = new AddEventJournalData(eventEnt, EventDataTrackingType.Casualties, 1);
        em.AddComponentData(eventEnt, journalReq);

        // Module systems (AddAccidentSiteSystem, AddCriminalSystem, EventJournalSystem) will
        // aggregate these requests on the next simulation update and produce persistent state.
    }
}
```

---

## Game.Input (input module)

A unified input layer that wraps Unity's Input System into game-aware, mod-friendly primitives. It exposes:
- Low-level building blocks: enums (ActionComponent/ActionType/AxisComponent, BindingGamepad/Keyboard/Mouse, BuiltInUsages), ControlPath parsing/display helpers, CompositeUtility for reading composite parts and mapping components↔types, DisplayNameOverride, and DeviceListener for simple device-activation detection.
- Reusable composites and processors: built composite types (ButtonWithModifiersComposite, AxisWithModifiersComposite, AxisSeparatedWithModifiersComposite, CameraVector2WithModifiersComposite, Vector2WithModifiersComposite, Vector2SeparatedWithModifiersComposite) and camera-related processors (CameraMoveProcessor, CameraRotateProcessor, CameraZoomProcessor), smoothing/scroll processors (SmoothFloat/Vector2Processor, ScrollSensitivityProcessor) and mask/modifier processors.
- Composite serialization/registration: ICustomComposite, CompositeInstance and CompositeData helpers to register composites with Unity Input System and the game's InputManager and to serialize composite definitions for bindings and the options UI.
- High-level runtime model and UI glue:
  - InputManager singleton: loads InputAction assets, creates ProxyActionMap/ProxyAction wrappers, tracks control-scheme/device state, resolves binding conflicts, provides binding APIs (GetBindings/SetBinding/ResetAllBindings), and creates InputBarrier/InputActivator objects for temporary blocking/allowing.
  - ProxyActionMap / ProxyAction / ProxyBinding / ProxyComposite: serializable/proxy wrappers that expose flattened bindings, per-device composite data, conflict info, rebind metadata and runtime state (read/value queries, WasPressedThisFrame, ReadRawValue, etc.). ProxyBinding and ProxyModifier support JSON write/read and conflict tracking.
  - InputBarrier and InputActivator: scoped objects to block or force-enable maps/actions for device masks; register/unregister with proxies and must be disposed to avoid stale registrations.
  - Conflict resolution: InputConflictResolution periodically categorizes actions (system/UI/mod) and enforces priorities (system > UI > mod) using InputManager.HasConflicts and applies masking/enabling accordingly.
  - Editor/UI assets: UIBaseInputAction and derivatives (UIInputAction, UIInputCombinedAction, UIInputOverrideAction, UIInputActionPart, UIInputActionCollection) provide ScriptableObject-driven mappings that produce IProxyAction runtime states usable by UI code.
  - Usages, option-group overrides and presentation helpers for localized/human-readable binding labels (ControlPath, DisplayNameOverride).
- Conventions and usage notes:
  - Register custom composites/processors with InputSystem.RegisterBindingComposite / RegisterProcessor and use CompositeUtility.GetCompositeData() when integrating with the game InputManager/UI.
  - Use CompositeUtility.ReadValue / ReadValueAsButton inside custom composites to respect modifiers/comparers.
  - Processors like CameraMove/Rotate/Zoom consult SharedSettings.instance.input for device sensitivities; ensure SharedSettings exists when used.
  - Most APIs are main-thread only; batch mutating operations via InputManager.DeferUpdating() or ProxyAction.DeferStateUpdating() to avoid repeated expensive updates.
  - Dispose barriers/activators to avoid stale registrations.

In short: this module provides composable binding primitives, processors, serialization and runtime proxies so mods and UI can read, present, remap and temporarily control input with consistent behavior and conflict handling.

### Usage example
```csharp
using UnityEngine;
using UnityEngine.InputSystem;
using Game.Input;

public class ExampleMod : MonoBehaviour
{
    private ProxyAction _zoomAction;
    private InputBarrier _barrier;
    private InputActivator _activator;
    private DeviceListener _deviceListener;

    void Start()
    {
        // 1) Register composites/processors so Unity InputSystem and game UI know them
        InputSystem.RegisterBindingComposite<AxisSeparatedWithModifiersComposite>();
        InputSystem.RegisterBindingComposite<AxisWithModifiersComposite>();
        InputSystem.RegisterBindingComposite<ButtonWithModifiersComposite>();
        InputSystem.RegisterBindingComposite<CameraVector2WithModifiersComposite>();
        InputSystem.RegisterProcessor<ScrollSensitivityProcessor>();

        // 2) Ensure the game InputManager exists and get instance
        InputManager.CreateInstance();
        var input = InputManager.instance;

        // 3) Find a proxy action (map "Camera", action "Zoom") and subscribe to interaction events
        _zoomAction = input.FindAction("Camera", "Zoom");
        if (_zoomAction != null)
        {
            _zoomAction.onInteraction += (proxy, phase) =>
            {
                if (phase == UnityEngine.InputSystem.InputActionPhase.Performed &&
                    proxy.valueType == typeof(float))
                {
                    float v = proxy.ReadValue<float>();
                    Debug.Log($"Zoom performed: {v}");
                }
            };

            // 4) Temporarily block gamepad for this action
            _barrier = _zoomAction.CreateBarrier("BlockGamepadZoom", InputManager.DeviceType.Gamepad);
            _barrier.blocked = true;

            // 5) Ensure action is enabled regardless of other mask state
            _activator = _zoomAction.CreateActivator("EnsureEnabled", InputManager.DeviceType.All);
            _activator.enabled = true;
        }

        // 6) Use ControlPath helper and CompositeUtility for small runtime queries
        var cp = ControlPath.Get("<Keyboard>/a");
        Debug.Log($"control name={cp.name}, display={cp.displayName}, device={cp.device}");

        // Example CompositeUtility mapping
        var comp = ActionComponent.Press;
        var aType = comp.GetActionType(); // ActionType.Button/Axis/Vector2

        // 7) DeviceListener: detect when a device is activated (any button pressed)
        var gp = Gamepad.current;
        if (gp != null)
        {
            _deviceListener = new DeviceListener(gp, requiredDelta: 0.1f);
            _deviceListener.EventDeviceActivated.AddListener(OnDeviceActivated);
            _deviceListener.StartListening();
            // call _deviceListener.Tick() from Update() to flush activations if needed
        }

        // 8) Example: create a ProxyBinding, check conflicts and write to JSON
        var compositeInstance = CompositeUtility.GetDefaultCompositeInstance(ActionType.Axis);
        var proxyBinding = new ProxyBinding("Gameplay", "Move", ActionComponent.Primary, "horizontal", compositeInstance)
            .WithPath("<Keyboard>/a")
            .WithModifiers(new[] { new ProxyModifier { m_Name = "Shift", m_Path = "<Keyboard>/shift" } });

        if (proxyBinding.isSet && proxyBinding.hasConflicts != ProxyBinding.ConflictType.None)
        {
            Debug.Log($"Binding conflicts: {proxyBinding.conflicts.Count}");
        }

        using (var writer = JSON.CreateWriter())
        {
            proxyBinding.Write(writer);
            Debug.Log(writer.ToString());
        }
    }

    private void OnDeviceActivated(InputDevice device)
    {
        Debug.Log($"Device activated: {device.displayName}");
    }

    void Update()
    {
        // If using DeviceListener, tick it on main thread
        _deviceListener?.Tick();
    }

    void OnDestroy()
    {
        _activator?.Dispose();
        _barrier?.Dispose();
        _deviceListener?.StopListening();
    }
}
```

---

## Game.Modding (modding & toolchain)

Summary

- Purpose: Provides runtime infrastructure for loading, running and configuring game mods (IMod lifecycle, ModManager, ModInfo, ModSetting and UI registration) and a toolchain dependency framework used by mod tooling (BaseDependency family, combined/IDE helpers, concrete dependencies and a toolchain manager/deployer).
- Runtime mod lifecycle:
  - IMod: simple lifecycle interface with OnLoad(UpdateSystem) and OnDispose(). Mods must initialize runtime state in OnLoad and perform heavy I/O off the main thread.
  - ModManager: discovers mod assets, loads mod assemblies, allocates IMod instances without running constructors (FormatterServices.GetUninitializedObject), calls OnLoad, registers UIModules, reports progress/errors via NotificationSystem, and marks restartRequired when enabled mods change. Initialization, iteration and disposal are timed and logged.
  - ModInfo: per-mod wrapper validating flags and dependencies, loading assemblies (calling a static AfterLoadAssembly to register types and mark SerializerSystem dirty), creating IMod instances, calling lifecycle methods, and exposing loadError/state for diagnostics. Missing deps and assembly errors map to explicit states and notifications.
- Settings & input binding:
  - ModSetting: base class for mod settings and input bindings. Auto-discovers ProxyBinding properties through reflection and creates ProxyAction/ProxyComposite/ProxyBinding objects. Integrates with InputManager, supports mimicking built-in bindings, exposes localization key helpers, and requires RegisterKeyBindings (when InputManager exists) and RegisterInOptionsUI to appear in Options.
- Toolchain dependency framework:
  - BaseDependency: core abstract class with state/progress reporting and default async methods (IsInstalled/Download/Install/Uninstall/Refresh). Includes a unified Download helper using UnityWebRequest with progress/cancellation support and standardized error wrapping.
  - BaseIDEDependency: probes and caches external tool versions and compares against minimum requirements. Async probe methods are preferred; synchronous getters may block.
  - CombinedDependency: composes multiple child dependencies and aggregates checks/operations with combine strategies (OR, AND, ALL). Supports parallel or sequential execution and aggregates results/errors. Note shipped source contains an Uninstall delegating to Download (likely a bug).
  - Concrete dependencies: DotNetDependency, NodeJSDependency, NpxModProjectDependency, ProjectTemplateDependency, IDEDependency (combines VS/Rider/VSCode detectors), MainDependency (read-only proxy). Many are Windows-focused (msi/exe installers) and use CliWrap to run installers/uninstallers and refresh PATH/env.
- Toolchain toolset and manager:
  - IToolchainDependency and helpers: disk-space structs, states, env var constants, registry helpers, download-size utilities, refresh/sorting helpers.
  - Concrete tool detectors: Unity, UnityLicense, UnityModProject, Rider (RiderPathLocator), VSCode, VisualStudio (vswhere), plus POCOs for parsing vswhere output.
  - ToolchainDependencyManager: registers dependencies, computes aggregate DeploymentState, orders install/uninstall according to dependsOnInstallation/Uninstallation, checks disk-space by drive, persists environment variables to user registry and broadcasts WM_SETTINGCHANGE, posts UI notifications and progress updates.
  - ToolchainDeployment: public entry points (Run/RunWithUI) that schedule operations on the game's TaskManager. Manager supports filtering, ordering and cancellation. Many operations throw ToolchainException on error.
- Error model:
  - ToolchainException: exception type carrying a ToolchainError enum and the IToolchainDependency source for diagnostics. Used to surface dependency-specific failures (missing executables, bad versions, process failures).
- Best practices and gotchas:
  - Mods should do heavy I/O off the main thread, do initialization in OnLoad, and cleanup in OnDispose. Mod objects may be instantiated without running their constructors—initialization must therefore happen in OnLoad.
  - Call ModSetting.RegisterKeyBindings only after InputManager is ready. Use SettingsUI* attributes on ProxyBinding properties to control UI defaults or to mimic built-in bindings.
  - Prefer async APIs (GetVersion/IsInstalled/Install/Download) and CancellationToken-aware calls to avoid blocking the game thread. Many installers target Windows; CLI wrappers (CliWrap) are used to run external installers.
  - CombinedDependency short-circuits and cancels other children as appropriate; be aware of the combine strategy semantics.
  - Inspect ModInfo.loadError and ToolchainException.error/source for diagnostics. Notifications and logs are published via NotificationSystem and toolchain logging.

### Usage example
```csharp
// Minimal mod using IMod + ModSetting and an example of invoking the toolchain installer.
// (Illustrative; depends on game engine types like UpdateSystem and ToolchainDeployment.)

public class MyModSettings : ModSetting
{
    // Example ProxyBinding property; ModSetting base will discover and create bindings.
    [SettingsUILabel("MyMod.Bind.ToggleLabel")]
    public ProxyBinding ToggleAction { get; private set; } = new ProxyBinding();

    public MyModSettings(IMod modSource) : base(modSource)
    {
        // ModSetting ctor performs reflection discovery of ProxyBindings.
    }
}

public class MyFeatureMod : IMod
{
    private UpdateSystem _updateSystem;
    private MyModSettings _settings;

    public void OnLoad(UpdateSystem updateSystem)
    {
        _updateSystem = updateSystem;

        // Create settings object (auto-discovers bindings)
        _settings = new MyModSettings(this);

        // Register settings UI (shows in Options) and key bindings (call when InputManager is ready)
        _settings.RegisterInOptionsUI();
        _settings.RegisterKeyBindings();

        // Example: register a per-frame callback (short, non-blocking)
        // _updateSystem.Register(UpdateCallback);
    }

    public void OnDispose()
    {
        // Cleanup: unregister UI/bindings and any update callbacks
        _settings?.UnregisterInOptionsUI();
        // _updateSystem?.Unregister(UpdateCallback);
        _settings = null;
        _updateSystem = null;
    }
}

// Example: trigger a programmatic toolchain install (from a background task/context)
public static class ToolchainExample
{
    public static async System.Threading.Tasks.Task InstallToolchainAsync()
    {
        using var cts = new System.Threading.CancellationTokenSource();

        try
        {
            // Runs downloads/installs for the registered default dependency set.
            await Game.Modding.Toolchain.ToolchainDeployment.Run(Game.Modding.Toolchain.DeploymentAction.Install, cts.Token);
            Console.WriteLine("Toolchain install completed or components already up-to-date.");
        }
        catch (OperationCanceledException)
        {
            Console.WriteLine("Toolchain install cancelled.");
        }
        catch (Game.Modding.Toolchain.ToolchainException tex)
        {
            Console.WriteLine($"Toolchain error: {tex.error} (src: {tex.source?.Name}) - {tex.Message}");
        }
        catch (System.Exception ex)
        {
            Console.WriteLine($"Unexpected error: {ex}");
        }
    }
}
```

---

## Game.Net (Net module)

Summary
This module is the Cities: Skylines 2 DOTS/ECS networking ("net") subsystem: the data types, buffer elements, flags and systems that implement roads, lanes, tracks, pipes, airway lanes, lane objects, labels, connectivity and related runtime logic. It is optimized for Burst/jobs and the game's Colossal.Serialization pipeline and follows common ECS patterns (IComponentData, IBufferElementData, ComponentLookup/BufferLookup, ComponentTypeHandle, Native containers, JobHandles, etc.).

Key pieces
- Data & primitives
  - Geometry/curve: Curve, Bezier segments, EdgeGeometry, EdgeLane, Segment, LabelPosition/LabelExtents and compact geometry encodings.
  - Topology & graph: Edge, Node, ConnectedEdge/ConnectedNode buffers, Composition, Aggregate/Aggregated/AggregateElement, EdgeMapping and iterators (EdgeIterator).
  - Lanes & flows: Lane, CarLane, TrackLane, LaneFlow, LaneGeometry, LaneConnection, SubLane, SlaveLane; many have compact serialization and version-aware deserialization.
  - Lane objects & overlaps: LaneObject, LaneObjectAction, LaneObjectCommandBuffer, LaneOverlap, LaneReservation, ParkingLane, LaneSignal types.
  - Utilities & services: ResourceAvailability, ServiceCoverage, WaterPipeConnection, Road/RoadFlags, Roundabout, various small enums/flags like CarLaneFlags, ConnectionLaneFlags, GeometryFlags.
  - Airway: AirwayData / AirwayMap grid-backed NativeArray<Entity> maps and helpers for helicopter/airplane lanes.

- Core systems (job/Burst-driven)
  - GeometrySystem / InitializeSystem / FlipTrafficHandednessSystem: compute and maintain node/edge/lane geometry, bezier curves, heights and bounds.
  - LaneSystem / SecondaryLaneSystem / SecondaryLaneReferencesSystem: create/update/delete primary and decorative lanes, maintain SubLane buffers and master/slave grouping.
  - LaneOverlapSystem / LaneReferencesSystem / LaneHiddenSystem: compute overlaps, propagate flags (merge/split/forbid), and keep hidden/visibility states consistent.
  - LaneObjectUpdater & LaneObjectCommandBuffer: queue and apply add/remove/update actions for per-lane objects (trees, markers, signals) via parallel jobs and quadtree updates.
  - EdgeMappingSystem / ReferencesSystem / CompositionSelectSystem / AggregateSystem: maintain edge-to-node mappings, connected-edge/node buffers, compositions and aggregated edge groups.
  - SearchSystem: maintains NativeQuadTree net and lane search trees and exposes reader/writer registration and JobHandle dependencies for safe multithreaded queries.
  - RaycastJobs: raycast helpers (edges, lanes, labels) used by selection/hit-testing with a NativeAccumulator writer pattern.
  - ConnectionWarningSystem, CostSystem, FixLaneObjectsSystem, UpdateCollectSystem, TrafficLightInitializationSystem and other specialized systems handling warnings/icons, costs, repairs, updated bounds, and signal grouping.
  - AirwaySystem: creates airway lane entities, provides serialization/deserialization and exposes AirwayData maps (must be disposed when created manually).

Common implementation patterns & modder guidance
- Most heavy work runs inside Burst-compiled jobs (IJobChunk, IJobParallelForDefer, IJob) and uses NativeList/Queue/HashMap/ParallelHashSet. Acquire ComponentLookup/BufferLookup/TypeHandles from your SystemState and mark read-only where appropriate.
- Structural changes from jobs use ModificationBarrier(s) and EntityCommandBuffer.ParallelWriter; do not perform concurrent structural changes outside the same barrier/streams. Use UpdateBefore/UpdateAfter to order custom systems relative to built-in net systems.
- SearchSystem quadtrees require readers/writers registration; call provided GetNetSearchTree/GetLaneSearchTree and respect the returned JobHandle dependencies.
- Many components implement Colossal.Serialization IWriter/IReader and include version checks in Deserialize. Preserve field order and version logic when serializing or adding new persisted fields.
- Flags enums are bitflags and used heavily in hot loops — use bitwise checks instead of Enum.HasFlag in performance-sensitive code.
- Native arrays/maps (e.g., AirwayMap.NativeArray<Entity>) must be explicitly disposed or kept in lifetime-managed containers (AirwayData).
- Use IconCommandSystem to add/remove UI icons instead of modifying ConnectionWarningSystem internals.

When to extend vs. modify
- Prefer adding systems that run After or Before existing Game.Net systems to extend behavior (for example, UpdateAfter(Game.Net.EdgeMappingSystem)). Avoid modifying internal burst jobs; instead supply prefab/Composition data or trigger Updated tags to change behaviour declaratively.

### Usage example
```csharp
// Example: create an aggregate container, add an edge into it, query the AirwaySystem,
// and record a lane object action with the LaneObjectUpdater.
// (Illustrative; actual calls to ComponentLookup/BufferLookup and SystemState must happen inside a System.)

using Unity.Entities;
using Unity.Collections;
using Unity.Mathematics;
using Game.Net;

public class NetModuleExample
{
    public void Run()
    {
        var world = World.DefaultGameObjectInjectionWorld;
        var em = world.EntityManager;

        // Create a simple aggregate container entity with a DynamicBuffer<AggregateElement>
        Entity aggregateEntity = em.CreateEntity();
        em.AddBuffer<AggregateElement>(aggregateEntity);
        em.AddComponentData(aggregateEntity, new Aggregate()); // tag as aggregate container

        // Create an edge entity and mark it as aggregated -> point it at the aggregate
        Entity edgeEntity = em.CreateEntity(
            typeof(Game.Net.Edge),
            typeof(Game.Net.Curve),
            typeof(Game.Net.EdgeGeometry),
            typeof(Game.Net.Aggregated)
        );
        em.SetComponentData(edgeEntity, new Game.Net.Aggregated { m_Aggregate = aggregateEntity });

        // Add the edge into the aggregate's buffer (so AggregateSystem can validate/merge it)
        var aggBuf = em.GetBuffer<AggregateElement>(aggregateEntity);
        aggBuf.Add(new AggregateElement(edgeEntity));

        // Query the AirwaySystem for airway data (read-only usage). AirwaySystem owns lifetime of maps.
        var airwaySystem = world.GetExistingSystemManaged<AirwaySystem>();
        if (airwaySystem != null)
        {
            var airwayData = airwaySystem.GetAirwayData(); // returns owned AirwayData
            var helicopterMap = airwayData.helicopterMap; // NativeArray-backed map
            // To find the closest lane you'd sample Curve components via a ComponentLookup<Curve>
            // and use helpers on AirwayMap. (Actual sampling must be inside a System with proper lookups.)
        }

        // Record lane object actions using LaneObjectUpdater inside a System context.
        // Here we illustrate the pattern (real code must be inside a SystemBase and use its JobHandles):
        var updater = new LaneObjectUpdater(/* SystemBase or SystemState instance required */ null);
        // Begin returns a command recorder that writes into native queues managed by the updater.
        // var cmd = updater.Begin(Allocator.TempJob);
        // cmd.Add(laneEntity, prefabToAdd, new float2(0.25f, 0f));
        // cmd.Remove(laneEntity, existingObjToRemove);
        // // Schedule apply and respect/chain returned JobHandle
        // JobHandle deps = default;
        // JobHandle handle = updater.Apply(/* systemState */, deps);
        // handle.Complete(); // optionally wait

        // Note: The above LaneObjectUpdater usage must be done inside a System (to provide lookups and allow
        // the updater to schedule Burst jobs). Do not dispose internal updater queues yourself — the updater does it.
    }
}
```

If you want a focused summary of a single subsystem (AirwaySystem, LaneOverlapSystem, GeometrySystem, SearchSystem, or any specific component type like LaneFlow / Aggregate), tell me which and I will expand that section with fields, key algorithms and common pitfalls.

---

## Game.Notifications (Notifications module)

A collection of lightweight ECS components, enums, systems and helper jobs that implement the Cities: Skylines 2 notification / icon pipeline: producing icon commands, creating and maintaining icon entities, animating icons, clustering icons spatially for rendering/LOD, raycasting icons for interaction, and utilities for persistence and visibility. The module is designed to run mostly in Jobs/Burst with DOTS-friendly types (ComponentData, BufferElement, ComponentLookup, Native containers) and coordinates structural changes via command buffers / modification barriers.

Key pieces:
- Data components and enums
  - Animation (struct): per-entity animation state (m_Timer, m_Duration, AnimationType). Serializable for saves.
  - AnimationType (enum): Fade/appear/resolve/transaction phases (byte-backed).
  - Icon (struct): world icon data (float3 m_Location, priority, cluster layer, flags, runtime m_ClusterIndex). Serializable with version checks for clustering fields.
  - IconElement (IBufferElement): dynamic buffer element referencing an icon Entity (InternalBufferCapacity(4)).
  - IconFlags, IconPriority, IconClusterLayer, IconLayerMask: bitmask/enum types controlling behavior, priority and clustering layer.
  - DisallowCluster (tag struct): marker to prevent clustering for an entity.

- Command pipeline
  - IconCommandBuffer (struct): a parallel-safe producer wrapper around NativeQueue<Command>.ParallelWriter used to enqueue Add / Remove / Update commands from main thread or jobs.
  - IconCommandBuffer.Command: command record (owner, prefab, optional location, flags, priority, delay, bufferIndex) with stable ordering via CompareTo.
  - IconCommandSystem (system): drains per-producer queues, flattens and sorts commands, and schedules IconCommandPlaybackJob (Burst) to create/remove/update icon entities using a ModificationEndBarrier's EntityCommandBuffer. The playback job resolves icon locations, matches existing icon instances, assigns animations, handles temp/hidden/disallow clustering flags, and uses ComponentLookups for transform/route/geometry lookups.

- Deletion/update helpers
  - IconDeletedSystem: detects Deleted/Updated entities and enqueues commands to remove/update icons via IconCommandSystem (runs as a JobChunk that writes to IconCommandBuffer).
  - MarkerCreateSystem: data-driven job that converts infomode/tool and prefab marker definitions into icon commands for stops, buildings, vehicles and arbitrary marker prefabs. Uses mask bitsets and a Burst IJobChunk to issue Add/Remove commands.

- Clustering & spatial data
  - IconClusterSystem: builds and maintains a quadtree and contiguous icon allocations (NativeHeapAllocator, NativeList<IconCluster>, NativeList<ClusterIcon>) for grouping icons spatially. Exposes ClusterData (a read-only view) and functions to request dependencies (GetIconClusterData, AddIconClusterReader/Writer). Supports full rebuilds on load and incremental updates using Burst jobs.
  - NotificationsUtils: small helpers (ICON_VISIBLE_THROUGH_DISTANCE constant and GetIconLayerMask).

- Animation, rendering and picking
  - IconAnimationSystem: schedules a Burst IJobChunk to advance Animation.m_Timer and apply transitions (remove Animation, add Updated or Deleted markers) using a ModificationBarrier.
  - RaycastJobs.RaycastIconsJob: Burst parallel job that raycasts over clusters and raw icon chunks, validates hits (owner resolution, placeholders, static/moving filters), and accumulates RaycastResult entries into a NativeAccumulator for UI/selection.

- Design notes
  - Systems use ModificationBarrier/ModificationEndBarrier to safely record structural changes from jobs.
  - Heavy work is Burst-compiled and uses ComponentLookups and NativeCollections; consumers must honor JobHandles returned by GetIconClusterData or AddCommandBufferWriter to avoid races.
  - Serialization-aware code paths exist (ISerializable / IEmptySerializable) and version checks guard cluster fields when deserializing older saves.

### Usage example
```csharp
// Example: produce an icon add command from a managed system and read cluster data safely.
using Unity.Entities;
using Unity.Mathematics;
using Game.Notifications;
using Unity.Collections;
using Unity.Jobs;

public void ExampleUsage(World world)
{
    var em = world.EntityManager;

    // 1) Create a simple icon entity with Icon + Animation (optional direct creation)
    Entity iconEntity = em.CreateEntity();
    em.AddComponentData(iconEntity, new Icon {
        m_Location = new float3(100f, 0f, 200f),
        m_Priority = IconPriority.Info,
        m_ClusterLayer = IconClusterLayer.Default,
        m_Flags = IconFlags.None,
        m_ClusterIndex = -1
    });
    em.AddComponentData(iconEntity, new Animation(AnimationType.MarkerAppear, 0f, 1.0f));

    // 2) Use IconCommandSystem to create a command buffer and enqueue an Add command (main thread)
    var iconCmdSystem = world.GetOrCreateSystemManaged<IconCommandSystem>();
    var cmdBuffer = iconCmdSystem.CreateCommandBuffer(); // returns IconCommandBuffer
    // Assume ownerEntity and prefabEntity exist:
    Entity ownerEntity = iconEntity; // for example
    Entity prefabEntity = Entity.Null;
    cmdBuffer.Add(ownerEntity, prefabEntity, IconPriority.Warning, IconClusterLayer.Marker, IconFlags.TargetLocation);

    // If you scheduled jobs that wrote to command buffers, register the job handle:
    // iconCmdSystem.AddCommandBufferWriter(jobHandle);

    // 3) Read cluster data safely (read-only) from IconClusterSystem
    var clusterSystem = world.GetOrCreateSystemManaged<IconClusterSystem>();
    JobHandle deps;
    var clusterData = clusterSystem.GetIconClusterData(readOnly: true, out deps);

    // To read immediately on main thread:
    deps.Complete();

    // Iterate root clusters (example)
    int rootIndex = 0;
    IconCluster cluster;
    while (clusterData.GetRoot(ref rootIndex, out cluster))
    {
        UnityEngine.Vector3 center = new UnityEngine.Vector3(cluster.center.x, cluster.center.y, cluster.center.z);
        // inspect cluster, icon count, bounds, etc.
        int first, count;
        var alloc = cluster.GetIcons(out first, out count);
        for (int i = 0; i < count; i++)
        {
            var ci = alloc.GetIcons(clusterData)[i]; // ClusterIcon fields: icon/prefab/priority/flags
            // handle icon entry...
        }
    }

    // Note: the systems (IconCommandSystem/IconClusterSystem) will process commands and cluster updates
    // during their normal OnUpdate scheduling; this example shows how to enqueue a command and consume cluster data.
}
```

---

## Game.Objects

Game.Objects is the Cities: Skylines 2 ECS module that provides the data components, tag markers, buffers and systems used to create, place, attach, align, update and manage lifecycle/interaction for placeable world objects (props, sub‑objects, stamps, attachments, buildings, net attachments, cranes, streetlights, trees, etc.). It is a DOTS-first, jobified set of small, mostly-blittable components (many 1‑byte marker/tags or versioned ISerializable structs), high-performance Burst jobs (raycasts, search quadtrees, batch updates), and several command-buffer driven systems that defer structural changes safely using the engine’s ModificationBarrier/ECB patterns.

Key points
- Purpose: position, attach and align subobjects; create/replace/duplicate subobjects; manage spawn/placeholder logic; compute and serialize geometry/transform state; handle damage/destroy events; compute lane blocking and override/collision relationships; perform validation for placement; and expose many placement/math helpers.
- Component types:
  - Marker/tag components: ActivityLocation, Object, Pillar, Placeholder, OutsideConnection, UtilityObject, WaterPipeOutsideConnection, Secondary, Static, Unspawned, UniqueObject, etc. (empty structs sized to 1 for serialization).
  - Small data components (blittable and versioned): Transform, Relative, Moving, MovedLocation, Elevation, Color, Quantity, Plant, NetObject (flags), SpawnLocation, Stack, StreetLight, Damage/Damaged/Destroy, BlockedLane (buffer element), SubObject (buffer element), SubObjectsUpdated, SubObjectHidden, etc.
  - Enums/Flags for placement and state: PlacementFlags, RotationSymmetry, SpawnLocationFlags, TransformFlags, TreeState, TrafficLightState, ObjectState.
- Buffers and search structures:
  - SubObject buffer holds child entities; BlockedLane buffer reports lane blockage ranges.
  - SearchSystem maintains NativeQuadTree(s) for static and moving object spatial queries; many systems register readers/writers and producer JobHandles with it.
- Major systems (representative):
  - SubObjectSystem / SubObjectReferencesSystem / SubObjectHiddenSystem: create/duplicate/remove subobjects, keep owner buffers in sync, hide originals when temps exist, and handle nested placement rules.
  - AlignSystem / AttachSystem / AttachPositionSystem: snap subobjects to owners (nodes/edges/lanes), compute world transforms, match height/water/rotation snapping and propagate transforms to children.
  - DestroySystem / DamageSystem: process Damage/Destroy events, mark Damaged/Destroyed, spawn collapse effects and remove building-specific parts.
  - LaneBlockSystem: find nearby net lanes, compute blocked ranges and maintain lane-object mappings.
  - SecondaryObjectSystem / SecondaryObjectReferencesSystem: spawn and maintain secondary objects (streetlights, anchors, signs) deterministically via pseudo-random seeds and barriers.
  - ObjectEmergeSystem / PlaceholderSystem / OutsideConnectionInitializeSystem / NetObjectInitializeSystem: handle specialized initialization and spawn/emergence behaviors (residents, animals, outside connections).
  - QuantityUpdateSystem, RelativeBoneSystem, ResetOverriddenSystem, SpawnLocationConnectionSystem: per-domain update jobs (fill levels, bone-resolution, override resets, spawn-location lane detection).
  - SearchSystem & RaycastJobs: high-performance spatial queries and mesh/skin raycasts used across placement and validation.
  - UpdateCollectSystem: collects per-frame bounds for changed objects for downstream users and UI.
  - ValidationHelpers: central placement/validation helpers (ValidateObject/ValidateNetObject/ValidateOutsideConnection/ValidateWorldBounds etc.) intended to run on worker threads and produce ErrorData.
- Utilities:
  - ObjectUtils: broad helper library for bounds, local/world transforms, terrain/water sampling, placement adjustments, cost/refund math, animation root-motion and other geometry/placement math.
- Serialization & save compatibility:
  - Many small components implement Colossal.Serialization patterns (ISerializable / IEmptySerializable) and are version-aware; tag components are sized to 1 to appear in saves. Changing persisted layouts or enum backing sizes must be done carefully to preserve backward compatibility.
- Concurrency & safety:
  - Systems are jobified and Burst-compiled. Use ComponentTypeHandle / ComponentLookup / BufferLookup and native containers. Structural changes must be deferred via the provided ModificationBarrier/ECB fences; do not mutate archetypes or entity layouts inside parallel jobs.
  - When using shared quadtrees/search structures, register job dependencies with SearchSystem (AddStaticSearchTreeWriter/Reader, etc.) and respect returned JobHandles.
- Modding tips:
  - Use provided small tag components to mark behavior cheaply and have your queries pick them up.
  - When adding persisted fields, follow the existing version-guarded serialization patterns.
  - To extend placement/attachment behavior, prefer changing ECS data (components/buffers/tags) or scheduling jobs that use the lookups rather than calling internal job logic directly.
  - For any custom jobs reading/writing the same data, use the system fences and search-tree reader/writer registration to avoid race conditions.

### Usage example
```csharp
// Example: create a placeable object, tag/attach it and enqueue a Damage event.
// Requires Unity.Entities, Unity.Mathematics and the game's namespaces to compile.

using Unity.Entities;
using Unity.Mathematics;
using Game.Objects;

public static class GameObjectsExample
{
    public static void CreateAttachAndDamage(EntityManager em, Entity prefab, Entity parentNode)
    {
        // Create an archetype using common Game.Objects components
        var archetype = em.CreateArchetype(
            typeof(Game.Objects.Transform),
            typeof(Game.Prefabs.PrefabRef),
            typeof(Game.Objects.Attached),
            typeof(Game.Objects.Color),
            typeof(Unity.Entities.DynamicBuffer<Game.Objects.SubObject>) // optional buffer
        );

        // Create the object entity and set minimal data
        Entity obj = em.CreateEntity(archetype);
        em.SetComponentData(obj, new Game.Objects.Transform {
            m_Position = new float3(0f, 0f, 0f),
            m_Rotation = quaternion.identity
        });
        em.SetComponentData(obj, new Game.Prefabs.PrefabRef { m_Prefab = prefab });

        // Attach to a parent (curve position 0.5 means mid-curve)
        em.SetComponentData(obj, new Game.Objects.Attached(parentNode, Entity.Null, 0.5f));

        // Tag the object as an activity location that other systems may query
        em.AddComponentData(obj, new Game.Objects.ActivityLocation());

        // Set a color slot (example struct with index/value/subColor)
        em.SetComponentData(obj, new Game.Objects.Color(index: 2, value: 10, subColor: false));

        // Create a Damage event entity; DamageSystem/Damage jobs will process it
        Entity damageEvent = em.CreateEntity(typeof(Game.Event), typeof(Game.Objects.Damage));
        em.SetComponentData(damageEvent, new Game.Objects.Damage(obj, new float3(0f, 25f, 0f)));

        // Signal Updated so SubObject/Attach/Align systems will consider this entity
        em.AddComponentData(obj, new Updated());
    }

    // Example SystemBase that queries ActivityLocation-tagged objects
    public partial class MyActivitySystem : SystemBase
    {
        protected override void OnUpdate()
        {
            Entities
                .WithAll<Game.Objects.ActivityLocation>()
                .ForEach((Entity e, ref Game.Objects.Transform t, in Game.Prefabs.PrefabRef prefabRef) =>
                {
                    // Custom per-activity-location logic
                    // Keep accesses small and job-friendly (use ComponentLookup/BufferLookup for heavy reads)
                })
                .ScheduleParallel();
        }
    }
}
```

---

## Game.PSI (PSI module)

A concise overview of the Game.PSI helpers used by Cities: Skylines 2 for platform integration, telemetry, mod UI, notifications and a few small utilities. The PSI module provides:

- ExcludeGeneratedModTagAttribute — a simple marker attribute to opt types/members out of automatic mod-tag generation.
- Internal.Helpers — small conversion and telemetry helpers (language ISO mapping, DisplayMode/GameMode -> telemetry enums, ScreenResolution -> "WxH", bool -> int).
- ModTags — generates and trims mod tags for assets/prefabs (type-derived tags, component/modTags), exposes GetEnumFlagTags (contains a noted implementation bug: yields the whole value repeatedly) and IsProp logic for static prefabs.
- NotificationSystem — static bridge to a NotificationUISystem: bind/unbind UI, Push/Pop notifications, and check Exist; safe no-ops if no UI is bound.
- PdxSdk.Launcher & LauncherSettings — save/delete "continue" metadata (continue_game.json) and load/save launcher UI settings (launcher-settings.json) mapping JSON <-> SharedSettings and LocalizationManager; handles resolution strings, refresh rate, display mode and language.
- PdxModsUI — integration for Paradox Mods UI: view adapter (Cohtml wrapper), input-mode mapping, localized locale string, logger adapter and lifecycle handling (show/destroy, respond to input and locale changes). The view adapter raises ReadyForBindings and requires disposal.
- PlatformSupport — factory delegates for platform integrations (DiscordRichPresence / GDK) with hard-coded IDs that can be replaced if needed.
- RichPresenceUpdateSystem — ECS system that periodically composes and updates Discord rich presence from game state (population, money, happiness, milestone, weather, action/state cycle) with throttling and registered rich-presence keys.
- Telemetry — central static telemetry sender: payload types and helpers for hardware, language, graphics, gameplay events (achievements, milestones, building placements, policies, panels, city stats), mods/DLC listing and session open/close. It uses Telemetry.gameplayData (must be initialized) and an internal Session tracker.
- VirtualKeyboard — TextInputHandler that opens/closes platform on-screen keyboard for gamepad-driven text input, maps "vk-type"/"vk-title"/"vk-description" attributes, and honors platform pass-through/backspace emulation.

Important notes & caveats:
- ModTags trims to kMaxTags (10) and prefers to keep type-derived tags; excessive tags are logged. GetEnumFlagTags has an implementation error (yields value.ToString() in the loop).
- PdxModsUI.uiViewAdapter returns a new adapter each call; calls that bind must wait for ReadyForBindings; adapters must be disposed to avoid leaks.
- LauncherSettings.TryGetLauncherSettings will fail if the JSON is missing/malformed; SaveSettings merges current SharedSettings and writes back. Resolution strings are expected as "WIDTHxHEIGHT".
- Telemetry requires Telemetry.gameplayData to be initialized with a valid World instance to emit many gameplay-related events; Telemetry.OpenSession initializes session state and sends mods/DLC info.
- NotificationSystem calls are safe when UI is not bound (null-conditional forwarding).
- VirtualKeyboard toggles GameManager.UIInputSystem.emulateBackspaceOnTextEvent according to platform pass-through behavior and subscribes to PlatformManager.onInputDismissed.

### Usage example
```csharp
using System;
using System.Collections.Generic;
using Game.PSI;
using Game.PSI.PdxSdk;
using Game.Settings;

// Example snippet showing several common PSI operations.
// Assumes game context types (NotificationUISystem, AssetData, SaveInfo, World, etc.) are available.

void ExampleUsage(World world, NotificationUISystem uiSys, AssetData asset, SaveInfo saveInfo, LocalizationManager loc, SharedSettings settings)
{
    // --- Notifications ---
    NotificationSystem.BindUI(uiSys);
    NotificationSystem.Push(
        identifier: "mod.update_available",
        titleId: "MOD_UPDATE_TITLE",
        textId: "MOD_UPDATE_TEXT",
        thumbnail: "Textures/Icons/update",
        progressState: ProgressState.None,
        onClicked: () => { /* open mod page */ }
    );

    // --- Mod tag generation ---
    var tags = new HashSet<string>(StringComparer.OrdinalIgnoreCase);
    var typeTags = new HashSet<string>(StringComparer.OrdinalIgnoreCase);
    var validTags = new HashSet<string>(StringComparer.OrdinalIgnoreCase) { "Residential", "Commercial", "Park", "Road" };
    ModTags.GetTags(asset, tags, typeTags, validTags);
    // 'tags' now contains generated tags (trimmed to ModTags.kMaxTags)

    // --- Launcher metadata / settings ---
    PdxSdk.Launcher.SaveLastSaveMetadata(saveInfo);
    LauncherSettings.LoadSettings(loc, settings);
    LauncherSettings.SaveSettings(settings);

    // --- PDX Mods UI ---
    var modsUI = new PdxModsUI();
    modsUI.Show();
    // create an adapter and bind when ready
    using (var adapter = modsUI.uiViewAdapter)
    {
        adapter.ReadyForBindings += () =>
        {
            adapter.BindCall("onJSAction", new Action(() => UnityEngine.Debug.Log("JS invoked")));
            adapter.AddHostLocation("ModsUI", new List<string> { "Assets/ModsUI" });
        };
        adapter.Enable();
        // ...
        adapter.Disable();
    }
    modsUI.Destroy();
    modsUI.Dispose();

    // --- Telemetry session (requires a valid World-backed GameplayData) ---
    Telemetry.gameplayData = new Telemetry.GameplayData(world);
    Telemetry.OpenSession(Guid.NewGuid());
    Telemetry.FireSessionStartEvents(); // hardware/language/graphics
    // send a building placement (example)
    // Telemetry.PlaceBuilding(entity, prefab, new float3(10f, 0f, 20f));
    Telemetry.CloseSession();

    // --- Cleanup notifications UI binding when UI is destroyed ---
    NotificationSystem.UnbindUI();
}
```

---

## Game.Pathfind

This module is the game's consolidated, high-performance pathfinding subsystem. It provides the native containers, small POD value types, job wrappers and ECS-facing systems used to build, update and answer path queries (pathfind, availability, coverage) and to maintain the path graph (edges/nodes/lane/parking data). It is designed for Burst/Jobs/ECS use and exposes both low-level primitives (UnsafePathfindData, NativePathfindData, UnsafeLinearAllocator, UnsafeLists/Queues/Heaps) and higher-level orchestration (PathfindQueueSystem, PathfindResultSystem, various Systems that produce modify actions).

Key responsibilities and components
- Action wrappers and action data: Many request and modification operations are expressed as IDisposable native-backed action wrappers (PathfindAction, AvailabilityAction, CoverageAction, CreateAction, UpdateAction, DeleteAction, DensityAction, FlowAction). Their inner ActionData structs hold UnsafeLists/Queues for inputs/results and must be explicitly disposed to avoid leaks. ActionData types carry PathfindActionState/parameters and result containers for worker jobs.
- Native graph storage and modification jobs: UnsafePathfindData / NativePathfindData store the graph (edges, connections, owner→edge maps) in contiguous unmanaged memory for speed. ModificationJobs (CreateEdgesJob, UpdateEdgesJob, DeleteEdgesJob, Time/Density/Flow jobs) apply queued modifications to the native graph; these jobs require the native container to be supplied and must obey job safety/lifecycle rules.
- Executors, jobs and search algorithms: Executors implement Dijkstra/A*-style traversals with min-heaps, deduplication tables, multi-source merging and heuristics. PathfindJobs, AvailabilityJobs and CoverageJobs contain Burst-friendly IJob/IJobParallelFor implementations that run the searches; ProcessResultsJob reduces raw worker results into ECS buffers (AvailabilityElement, CoverageElement, PathElement).
- Orchestration and queuing: PathfindQueueSystem is the central scheduler and batcher: it maintains per-worker NativePathfindData instances, pools allocators, sequences graph modifications across workers, prioritizes requests and dispatches worker jobs (PathfindWorkerJob). PathfindResultSystem collects completed items and schedules ProcessResultsJobs to write results back to ECS buffers and emit end-of-frame update events.
- ECS systems that feed the queue: LaneDataSystem, RoutesModifiedSystem, RouteDataSystem, ParkingLaneDataSystem and related systems produce create/update/delete/time/density actions by scanning/processing ECS data (IJobChunk) and enqueue those action buffers into PathfindQueueSystem.
- Utilities and helpers: PathUtils and PathfindTargetSeekerData offer helpers to build PathSpecification objects for different vehicle/pedestrian types, compute costs/speeds, and sample lane/prefab geometry safely in systems/jobs. Compact packings (PathNode, PathOwner, PathfindWeights, PathfindParameters, PathfindResult) are used to minimize memory and copy cost.
- Results and ECS buffers: Results are compact POD structs (PathfindResult, AvailabilityResult, CoverageResult). Per-owner aggregation is written into IBufferElementData implementations (PathElement, AvailabilityElement, CoverageElement) by ProcessResultsJob.
- Safety & performance notes: Almost all heavy types are blittable and intended for Burst; native containers must be created with an appropriate Allocator (Temp/TempJob for job-lifetime, Persistent for long-lived) and explicitly disposed. Many structs wrap native handles — copying them can cause shared ownership and double-dispose/invalid-access bugs. When scheduling jobs, ensure all job handles complete before disposing memory and follow Unity's native container job-safety rules.

Typical workflows
- Graph update: Systems detect lane/route changes, build Create/Update/Delete action buffers, enqueue them to PathfindQueueSystem. The queue applies modifications across worker NativePathfindData instances via ModificationJobs.
- Single/synchronous search (testing or utility): Construct a PathfindAction (or PathfindActionData) with start/end PathTarget entries and PathfindParameters, run PathfindJobs.PathfindJob.Execute() or schedule the job using JobHandle, read the action data results, then Dispose the action.
- Queued/parallel search: Build an action and Enqueue it into PathfindQueueSystem (optionally with a SystemBase as owner, dependencies and priority). The queue batches and schedules worker jobs; completed results are collected by PathfindResultSystem which writes results into ECS buffers and may emit PathUpdated/CoverageUpdated events. Always Dispose the action when no longer needed.

When to use high-level vs low-level APIs
- High level: Use PathfindQueueSystem and Setup/Enqueue APIs from a SystemBase when integrating with simulation — it handles worker graphs, ordering of modification actions and result dispatch.
- Low level: Use NativePathfindData / UnsafePathfindData and PathfindJobs directly for testing tools, synchronous calculations or advanced custom systems where you manage lifetimes and synchronization.

### Usage example
The example below shows a conceptual synchronous Pathfind request and reading the result, then an example of enqueuing an action into PathfindQueueSystem. Types and field names follow the module's conventions — adapt field initialization to your game's concrete lane/curve data.

```csharp
using Unity.Collections;
using Unity.Entities;
using Game.Pathfind;
using Unity.Jobs;

// Example: Build and run a synchronous pathfind, then enqueue a similar action to the PathfindQueueSystem.
void ExamplePathfindUsage(World world, NativePathfindData nativePathfindData)
{
    // 1) Synchronous direct job execution (useful for unit tests or immediate reads)
    Allocator alloc = Allocator.TempJob;
    try
    {
        // Build deterministic parameters
        var parameters = default(PathfindParameters);
        parameters.m_PathfindFlags = PathfindFlags.Stable;
        parameters.m_MaxSpeed = new Unity.Mathematics.float2(10f, 10f);

        // Create action with one start and one end target (native-backed; will allocate UnsafeLists)
        var action = new PathfindAction(startCount: 1, endCount: 1, alloc, parameters, originType: 0, destinationType: 0);
        try
        {
            ref var data = ref action.data;
            // Fill start/end targets (PathTarget fields must be set according to your context)
            data.m_StartTargets[0] = new PathTarget { /* m_Entity = originEntity, m_Owner = owner, ... */ };
            data.m_EndTargets[0]   = new PathTarget { /* m_Entity = destEntity, m_Owner = owner, ... */ };

            // Prepare the Pathfind job and set the native container if required by job
            var job = new PathfindJobs.PathfindJob
            {
                m_PathfindData = nativePathfindData, // if job accepts a NativePathfindData directly
                m_Action = action
            };

            // Execute synchronously (or Schedule() and Complete() for async)
            job.Execute();

            // Inspect action.data.m_Results (UnsafeList<PathfindResult>) for results
            var results = data.m_Results;
            for (int i = 0; i < results.Length; i++)
            {
                var res = results[i];
                if (res.m_ErrorCode == 0)
                {
                    UnityEngine.Debug.Log($"Path found: cost={res.m_TotalCost}, distance={res.m_Distance}");
                }
                else
                {
                    UnityEngine.Debug.Log($"Path failed: error={res.m_ErrorCode}");
                }
            }
        }
        finally
        {
            // Always dispose action and its inner native lists
            action.Dispose();
        }
    }
    finally
    {
        // If you used TempJob allocator, this completes the lifetime for that allocation block
    }

    // 2) Enqueueing to the PathfindQueueSystem (preferred for in-sim async processing)
    {
        var allocator = Allocator.TempJob;
        var action = new PathfindAction(startCount: 1, endCount: 1, allocator, default(PathfindParameters), 0, 0);
        try
        {
            ref var data = ref action.data;
            data.m_StartTargets[0] = new PathTarget { /* ... */ };
            data.m_EndTargets[0]   = new PathTarget { /* ... */ };

            // Get the queue system from the world (call from a SystemBase context in real code)
            var queueSystem = world.GetExistingSystemManaged<Game.Pathfind.PathfindQueueSystem>();
            if (queueSystem != null)
            {
                // Enqueue the action; the queue will schedule worker jobs and eventually produce results
                // Owner/resultFrame/dependencies arguments are optional/illustrative
                queueSystem.Enqueue(action, owner: Entity.Null, dependencies: default(JobHandle), resultFrame: 0u, system: null);
            }

            // NOTE: when enqueuing, do not Dispose() the action until the queue/workers have finished with it.
            // The queue or PathfindResultSystem will observe and you should Dispose after results are read.
        }
        finally
        {
            // If you did not enqueue (or after you confirmed results processed), always Dispose the action.
            // action.Dispose();
        }
    }
}
```

Notes
- The example is conceptual: constructing real PathTarget/PathSpecification objects requires concrete lane/curve/owner data from the game's components.
- If scheduling jobs (Schedule/Complete), chain JobHandles properly and Complete them before disposing any native data used by those jobs.
- Use Allocator.TempJob for short-lived job-lifetime allocations, Allocator.Persistent for long-lived graph containers (NativePathfindData/UnsafePathfindData) and always call Dispose when the container is no longer needed.

---

## Game.Policies module

Summary
- The Game.Policies module implements the policy system used by the game's ECS: data types, initialization of default policies, applying policy modifications, and computing option masks and numeric modifiers for buildings, districts, routes and the city.
- Key data types:
  - Policy (IBufferElementData): buffer element storing a policy entity, PolicyFlags, and a float adjustment. Serializable.
  - Modify (IComponentData): event payload describing a change (target entity, policy prefab, flags, adjustment).
  - PolicyFlags (byte [Flags] enum): currently defines Active.
- Initialization systems (run for Created entities or during deserialization):
  - DefaultPoliciesSystem: copies DefaultPolicyData from prefabs or the city configuration into instance or city Policy buffers (uses PolicySliderData defaults when present). Implements IPostDeserialize to populate city defaults on new-game/load conversions.
  - BuildingModifierInitializeSystem, DistrictModifierInitializeSystem, RouteModifierInitializeSystem: for newly created buildings/districts/routes, compute option masks and populate per-type modifier buffers (BuildingModifier, DistrictModifier, RouteModifier) based on active policies and any policy sliders. They use helper refresh-data structs and schedule parallel IJobChunk jobs to populate buffers efficiently.
- Runtime modification and refresh:
  - ModifiedSystem: primary system to process policy change events. It watches for Event+Modify entities, applies or removes Policy buffer entries (or toggles extension flags for certain extension-driven options), refreshes option masks and modifier buffers (district/building/route/city), issues triggers (e.g., FreePublicTransport) and records telemetry events. Work is done inside a Burst IJobChunk (ModifyPolicyJob), using ComponentLookup/BufferLookup and a command buffer for structural changes. Telemetry events (PolicyEventInfo) are emitted after the job completes.
- Modifier semantics:
  - Modifier entries (policy-side data) provide ranges and a mode (Relative, Absolute, InverseRelative). When applying policies, slider values (PolicySliderData) are mapped into numeric deltas (lerp over modifier range) and folded into per-type modifier buffers with accumulation rules depending on mode.
- Typical usage patterns:
  - Default policies are applied automatically when prefabs or city config contain DefaultPolicyData.
  - Systems only run for newly created entities (Created tag) when initializing options/modifiers.
  - To change policies at runtime, create an Event entity with a Modify component; ModifiedSystem will apply it and refresh affected entities.
  - You can inspect current policies via DynamicBuffer<Policy> on the target entity (or the city entity).

### Usage example
```csharp
// Example: Activate a policy on an entity (e.g., a district or building).
var em = World.DefaultGameObjectInjectionWorld.EntityManager;

// targetEntity: the entity you want to modify (district, building, route or city entity)
Entity targetEntity = /* obtain target entity */;
Entity policyPrefab = /* obtain the policy prefab/entity reference */;

// Create an event entity that carries a Modify command. ModifiedSystem will process it on update.
Entity evt = em.CreateEntity(typeof(Event), typeof(Game.Policies.Modify));
em.SetComponentData(evt, new Game.Policies.Modify(
    entity: targetEntity,
    policy: policyPrefab,
    active: true,        // set/unset policy activation
    adjustment: 0.75f    // slider/adjustment value if the policy uses a slider
));

// After the system runs, read the target's Policy buffer:
if (em.HasComponent<DynamicBuffer<Game.Policies.Policy>>(targetEntity))
{
    var policies = em.GetBuffer<Game.Policies.Policy>(targetEntity);
    for (int i = 0; i < policies.Length; i++)
    {
        var p = policies[i];
        bool isActive = ((byte)p.m_Flags & (byte)Game.Policies.PolicyFlags.Active) != 0;
        UnityEngine.Debug.Log($"Policy {p.m_Policy} active={isActive} adj={p.m_Adjustment}");
    }
}

// Example: Inspect city policies (DefaultPoliciesSystem.PostDeserialize populates these for new games)
var world = World.DefaultGameObjectInjectionWorld;
var citySystem = world.GetExistingSystemManaged<Game.CitySystem>(); // or access your CitySystem reference
Entity cityEntity = citySystem.City;
if (em.HasComponent<DynamicBuffer<Game.Policies.Policy>>(cityEntity))
{
    var cityPolicies = em.GetBuffer<Game.Policies.Policy>(cityEntity);
    // iterate as above...
}
```

---

## Game.Prefabs (module)

A concise summary

Game.Prefabs is the prefab → ECS bridge used throughout Cities: Skylines 2. It provides the authoring-side ScriptableObject/ComponentBase/PrefabBase types used in the editor and a large collection of small, high-performance runtime types (IComponentData, IBufferElementData, tag components, enums and helper structs) consumed by DOTS systems. Its responsibilities and recurring patterns are:

- Authoring classes and conversion lifecycle
  - ComponentBase / PrefabBase derivatives expose inspector fields and participate in conversion by overriding:
    - GetDependencies(List<PrefabBase>) — declare prefab asset dependencies,
    - GetPrefabComponents(HashSet<ComponentType>) — components that must exist on the prefab entity,
    - GetArchetypeComponents(HashSet<ComponentType>) — components required on runtime archetypes,
    - Initialize / LateInitialize — copy/convert inspector data into IComponentData/IBufferElementData and resolve PrefabBase → Entity via PrefabSystem.
  - LateInitialize is commonly used for buffers and for resolving referenced prefabs to Entities.

- Runtime data types
  - Many small, blittable IComponentData and IBufferElementData structs (ActivityLocationData, WaterPipeConnectionData, BuildingData, VehicleData, RouteData, ZoneData, etc.) store compact configuration for high-performance queries and jobs.
  - Tag components are thin 1‑byte structs (StructLayout Size=1) used for efficient archetype filtering.
  - Buffer element types represent variable-length lists (effects, audio variants, piece lists, affiliated brands, modifiers, initial resources, etc.) and often have InternalBufferCapacity annotations.

- Serialization & combination
  - Where needed types implement Colossal.Serialization ISerializable for save/load and ICombineData or ICombineBuffer-style semantics to aggregate multiple contributions (upgrades, combined capacity, etc.). Serialization ordering/version checks are important for compatibility.

- Common conversion idioms
  - Declare component types via GetPrefabComponents/GetArchetypeComponents.
  - Populate DynamicBuffer<T> in LateInitialize and set component instances via EntityManager.SetComponentData in Initialize.
  - Resolve PrefabBase references using PrefabSystem.GetEntity(prefab) in LateInitialize.
  - Convert editor units (km/h → m/s, degrees → radians) and pack enums/flags into compact fields before writing.

- Systems & helpers
  - PrefabSystem manages registration and PrefabBase → Entity mapping.
  - PrefabInitializeSystem and many subsystem-specific initializer systems (AnimatedPrefabSystem, NetInitializeSystem, MeshSystem, AreaInitializeSystem, ObjectInitializeSystem, ZonePrefabInitializeSystem, etc.) populate buffers, compute derived data and create archetypes.
  - Selection helpers (DeliveryTruckSelectData, GarbageTruckSelectData, TransportVehicleSelectData, etc.) use an async PreUpdate/PostUpdate pattern: collect archetype chunks async, then select/create prefabs, and finally dispose the temporary lists. Respect returned JobHandle.
  - ReplacePrefabSystem, NetCompositionMeshSystem, NetCompositionMeshRefSystem, TriggerPrefabSystem, ZoneBuiltRequirementSystem and other systems perform jobified processing, mesh deduplication, safe prefab replacement, trigger indexing, and unlock evaluation.
  - UpgradeUtils and Combine helpers merge base prefab data with installed upgrades.

- Performance & job patterns
  - Most runtime types are blittable and job‑safe (IQueryTypeParameter used where helpful).
  - Many initializer and mode-prefab operations schedule Burst IJobChunk jobs for parallel processing. Use JobHandle chaining and the provided AddReader/AddWriter semantics where relevant.
  - DynamicBuffer usage and InternalBufferCapacity are used to optimize memory/layout.

- Mode prefabs and game-mode tuning
  - Mode prefabs (LocalModePrefab / EntityQueryModePrefab) apply tuning to singletons or to specific prefabs (ApplyModeData / RestoreDefaultData / RecordChanges). They may run jobs to apply multipliers across entities or modify per-prefab components via PrefabSystem.

- Practical modding notes
  - Follow the standard prefab pattern: declare components in GetPrefabComponents/GetArchetypeComponents, write values in Initialize/LateInitialize, and use PrefabSystem to resolve cross-prefab entity references.
  - When implementing ISerializable or changing component layouts, preserve field order and version checks to avoid save/load breakage.
  - For selection helpers, always call PreUpdate(...) and PostUpdate(...) to manage async chunk lists and job handles.
  - Use bitwise operations on flags/enums in hot paths to avoid enum boxing.
  - Many systems and archetypes are created for you by the game pipeline; for manual work use PrefabSystem.GetEntity(prefab) to find the prefab entity and then read/write its components.

### Usage example

A small illustrative example that shows the common prefab pattern (declare prefab-provided components, LateInitialize to write Entity references and buffers) and a System reading the data. Replace types with real in-game types when integrating.

```csharp
using System.Collections.Generic;
using Unity.Entities;
using Unity.Mathematics;
using Game.Prefabs;

// Example prefab-style authoring component (editor ScriptableObject would normally provide this).
public class MyExamplePrefab : ComponentBase
{
    public PrefabBase referencedPrefab;     // inspector set reference to another PrefabBase
    public int exampleValue = 42;
    public float3[] spawnPositions;

    // Ensure the prefab entity has the components we will write
    public override void GetPrefabComponents(HashSet<ComponentType> components)
    {
        base.GetPrefabComponents(components);
        components.Add(ComponentType.ReadWrite<ExampleData>());           // IComponentData
        components.Add(ComponentType.ReadWrite<ExampleSpawnElement>());   // IBufferElementData
    }

    // LateInitialize: resolve prefabs to Entities and populate a DynamicBuffer
    public override void LateInitialize(EntityManager em, Entity entity)
    {
        base.LateInitialize(em, entity);

        // Resolve referenced prefab -> entity via PrefabSystem
        var prefabSystem = em.World.GetExistingSystemManaged<PrefabSystem>();
        Entity refEntity = prefabSystem != null ? prefabSystem.GetEntity(referencedPrefab) : Entity.Null;

        // Set simple component data
        em.SetComponentData(entity, new ExampleData { m_Value = exampleValue, m_Ref = refEntity });

        // Populate spawn positions into a buffer on the prefab entity
        var buf = em.GetBuffer<ExampleSpawnElement>(entity);
        buf.Clear();
        if (spawnPositions != null)
        {
            foreach (var p in spawnPositions)
                buf.Add(new ExampleSpawnElement { m_Position = p });
        }
    }
}

// Example runtime data types (normally provided by Game.Prefabs)
public struct ExampleData : IComponentData
{
    public int m_Value;
    public Entity m_Ref; // resolved Prefab entity
}

public struct ExampleSpawnElement : IBufferElementData
{
    public float3 m_Position;
}

// Example SystemBase that queries the prefab entity and reads buffers/components.
public partial class ExampleConsumeSystem : SystemBase
{
    protected override void OnUpdate()
    {
        Entities
            .WithAll<ExampleData>()
            .ForEach((Entity e, in ExampleData data, in DynamicBuffer<ExampleSpawnElement> spawns) =>
            {
                UnityEngine.Debug.Log($"Prefab entity {e} value={data.m_Value}, ref={data.m_Ref}");
                for (int i = 0; i < spawns.Length; i++)
                {
                    var pos = spawns[i].m_Position;
                    // Use pos for preview, validation, or spawn planning
                }
            })
            .WithoutBurst() // remove for high-performance production code if all types are job-safe
            .Run();
    }
}
```

This example illustrates the canonical prefab → ECS flow used across Game.Prefabs: declare components, resolve prefab references with PrefabSystem in LateInitialize, populate DynamicBuffers and set IComponentData, and finally read those compact runtime representations in systems.

---

## Reflection (batch 1)

This module provides a small reflection-based accessor system (Game.Reflection) plus a utility attribute for enum-backed arrays. Key pieces:

- EnumArrayAttribute
  - Marks a method/property/field as representing an array whose indices correspond to an enum type (stores the enum Type). Useful for editors/serializers to validate length or map indices to enum names.

- IValueAccessor (used throughout)
  - The common accessor abstraction (GetValue/SetValue and valueType). Concrete implementations implement access to fields, properties, methods and array elements.

- FieldAccessor
  - Reads/writes a FieldInfo on an object obtained from a parent IValueAccessor.
  - When the parent is a value type (struct), SetValue updates the boxed struct and writes it back to the parent so field changes persist.
  - Implements equality based on parent accessor and FieldInfo.

- PropertyAccessor
  - Invokes getter/setter MethodInfo on the parent-provided object.
  - If no setter is present, SetValue is a no-op.
  - Equality based on parent accessor and getter.

- GetterWithDepsAccessor
  - Read-only accessor that invokes a MethodInfo on the parent object and returns its result.
  - Supports passing an arguments array and an index pointing to a Unity.Jobs.JobHandle in that array; the JobHandle is Completed after the getter is invoked.
  - Throws on SetValue (readonly). Equality based on parent and MethodInfo.

- ValueAccessorUtils
  - Factory helpers to create accessors from reflected members:
    - CreateMemberAccessor(parent, MemberInfo): returns FieldAccessor, PropertyAccessor, or GetterWithDepsAccessor depending on member type and signature.
      - Special-cases NativePerThreadSumInt fields by exposing their internal Count as a PropertyAccessor.
      - For methods, supports an optional "readOnly" bool parameter and a single out/ref JobHandle parameter (logs warnings and returns null for unsupported signatures).
    - CreateNativeArrayItemAccessor(accessor, index): returns an accessor for a NativeArray<T> element for a set of supported element types (int, int2/3, uint, uint2/3, float, float2/3).
  - Returns null & logs warnings for unsupported shapes.

Notes and gotchas:
- Reflection invocation uses MethodInfo.Invoke and may throw TargetInvocationException; callers should handle exceptions.
- GetterWithDepsAccessor intentionally invokes the getter before completing the JobHandle (important for usage semantics).
- FieldAccessor handles boxed struct writeback automatically; use when nesting into value types.
- ValueAccessorUtils returns null if it cannot create an accessor for the given member/signature.

### Usage example
```csharp
using System;
using System.Reflection;
using Game.Reflection;
using Unity.Jobs;
using Unity.Collections;
using Unity.Mathematics;

// Example enum + attribute usage
public enum ZoneType { Residential, Commercial, Industrial, Park }

public class ExampleComponent
{
    // Mark that this array maps to ZoneType indices
    [EnumArrayAttribute(typeof(ZoneType))]
    public int[] zoneCapacities = new int[Enum.GetValues(typeof(ZoneType)).Length];

    private int m_counter = 10;
    public int Number { get; set; } = 42;

    // Example method that takes a JobHandle out parameter (pattern supported by ValueAccessorUtils)
    public string GetResult(bool readOnly, out JobHandle handle)
    {
        handle = default; // in real use this might be a scheduled handle
        return readOnly ? "ro" : "rw";
    }
}

// Minimal IValueAccessor for a root object instance
class ObjectAccessor : IValueAccessor
{
    private object _value;
    public ObjectAccessor(object value) => _value = value;
    public Type valueType => _value?.GetType() ?? typeof(object);
    public object GetValue() => _value;
    public void SetValue(object value) => _value = value;
}

// Using the utilities and accessors
void ExampleUsage()
{
    var instance = new ExampleComponent();
    IValueAccessor root = new ObjectAccessor(instance);

    // Create a FieldAccessor for private field 'm_counter'
    FieldInfo fieldInfo = typeof(ExampleComponent).GetField("m_counter", BindingFlags.Instance | BindingFlags.NonPublic);
    IValueAccessor fieldAccessor = ValueAccessorUtils.CreateMemberAccessor(root, fieldInfo);

    Console.WriteLine(fieldAccessor.GetValue()); // 10
    fieldAccessor.SetValue(99);
    Console.WriteLine(fieldAccessor.GetValue()); // 99

    // Create a PropertyAccessor for 'Number'
    PropertyInfo prop = typeof(ExampleComponent).GetProperty("Number", BindingFlags.Instance | BindingFlags.Public);
    IValueAccessor propAccessor = ValueAccessorUtils.CreateMemberAccessor(root, prop);
    Console.WriteLine(propAccessor.GetValue()); // 42
    propAccessor.SetValue(123);
    Console.WriteLine(propAccessor.GetValue()); // 123

    // Create a GetterWithDepsAccessor for GetResult (ValueAccessorUtils handles 'readOnly' + out JobHandle)
    MethodInfo method = typeof(ExampleComponent).GetMethod("GetResult", BindingFlags.Instance | BindingFlags.Public);
    IValueAccessor methodAccessor = ValueAccessorUtils.CreateMemberAccessor(root, method);

    // If creation succeeded, GetValue will invoke the method and, if applicable, complete the JobHandle placed in parameters
    if (methodAccessor != null)
    {
        object result = methodAccessor.GetValue(); // "ro" (ValueAccessorUtils supplies readOnly=true by convention)
        Console.WriteLine(result);
    }

    // Example: access an element of a NativeArray<float3> returned by some accessor
    // (assumes nativeArrayAccessor.ValueType == typeof(NativeArray<float3>))
    // IValueAccessor nativeArrayAccessor = ...
    // IValueAccessor elementAccessor = ValueAccessorUtils.CreateNativeArrayItemAccessor(nativeArrayAccessor, 5);
    // object elem = elementAccessor.GetValue();
}
```

This summary covers the main types and usage patterns in the batch: decorating enum-backed arrays, creating reflection-backed accessors for fields/properties/methods (including job-handle-aware getters), handling value-type parent writeback, and helper factories for native array elements.

---

## Game.Rendering

A consolidated summary of the game's Rendering module: a DOTS/Burst/Built-for-GPU rendering pipeline and helpers used to produce overlays, batched instance rendering, procedural uploads (bones/emissives), animation blending, post-processing/photo-mode, vegetation/wind, terrain/water, and many small value types and utilities for shader/instance mapping.

Core responsibilities and major subsystems
- Aggregation & overlays
  - AggregateMeshSystem / AggregateRenderSystem: collect and GPU-package aggregated labels and arrow overlays (meshes + materials), expose getters to safely obtain Mesh/Material pairs and draw during render callbacks.
  - OverlayRenderSystem / OverlayInfomodeSystem: collect vector overlay geometry and infomode textures (heatmaps), schedule jobs to fill native lists / raw texture buffers, upload to GPU and render via instanced/indirect draws or Texture2D.Apply. Use GetBuffer/AddBufferWriter/GetTextMesh and ApplyOverlay.

- Area & batch rendering
  - AreaBufferSystem / AreaBatchSystem / AreaRenderSystem / AreaBorderRenderSystem / AreaColorSystem: build per-area triangle buffers, pack allocations, manage GPU triangle/color ComputeBuffers, perform batched indirect draws and border overlay emissions. Use GetAreaBuffer/GetAreaBatch/GetColorData/AddColorWriter.

- Managed batching & mesh pipeline
  - BatchMeshSystem, BatchManagerSystem, BatchDataSystem, BatchInstanceSystem, BatchRendererSystem, BatchUploadSystem: mesh lifecycle (async generation, caching, VT binding), batch/group/instance containers, per-instance property updates, culling & LOD, and parallel GPU buffer uploads (BeginParallelUpload/EndParallelUpload). Respect Get*/Add*Writer APIs for JobHandle synchronization.

- Procedural uploads and skeletons/emissives
  - ProceduralSkeletonSystem / ProceduralEmissiveSystem / ProceduralUploadSystem: heap allocators for sparse procedural uploads (float4x4 bones, emissive arrays), threaded assembly of upload data and sparse GPU commits. Use GetHeapAllocator/BeginUpload/AddUploadWriter/CompleteUpload and remember index 0 is reserved.

- Animation & deformables
  - AnimatedSystem + Animated* structs: allocate native animation buffers and ComputeBuffers, blend via a compute shader, accept producer writers for allocation/animation frames (GetAnimationData/GetAllocationData/Add*Writer).

- Culling / pre-culling / rendering flow
  - PreCullingSystem / CompleteCullingSystem / PreRenderSystem / RenderingSystem: compute per-entity pre-culling state, produce compact PreCullingData lists for consumers, finalize culling and prepare per-frame rendering globals (frame index/time/LOD). Use GetCullingData/AddCullingDataReader/Writer and call RenderingSystem.PrepareRendering() before render-dependent work.

- Interpolation, transforms & helpers
  - ObjectInterpolateSystem / RelativeObjectSystem / EventInterpolateSystem: interpolation helpers, transform frame math, bone history management, and animation helpers (CalculateTransform, CalculateUpdateFrames) usable from jobs or mod code.

- Terrain / water / vegetation / outlines / photo mode
  - TerrainRenderSystem: manage per-world terrain materials, cascades, splatmaps and overlays (overrideOverlaymap/overlayExtramap).
  - WaterRenderSystem: per-surface water material setup and shader bindings.
  - VegetationRenderSystem / WindControl / WindTextureSystem: VFX instantiation, wind constant-buffer updates and async wind texture generation.
  - OutlinesWorldUIPass / PhotoModeRenderSystem: custom HDRP pass for outlines and a managed HDRP Volume for photo-mode properties and presets.

- Utility types & small PODs
  - Packed shader/instance structs (AreaTriangleData, BatchData, BlendColors, BlendWeights, Bone, BoneHistory, CullingData, etc.), bitflag enums, MaterialPropertyAttribute mapping helpers, FrustumPlanes (SOA packets), HeapAllocator and other low-level helpers used widely across jobs and systems.

Integration patterns, important rules and modder tips
- Respect job dependencies: whenever you call a Get* method that returns a JobHandle, combine/return your producer JobHandle using the corresponding Add*Writer/Add*Reader method so the system can synchronize correctly.
- Do not destroy Mesh or Material instances created by systems — they are owned and managed by those systems. Use Get*Mesh/Get*Material getters to obtain references (they will complete dependencies as needed).
- Use public system APIs rather than touching native containers directly. Most heavy work is done in Burst jobs and systems expose small, safe surfaces (GetAreaBuffer, GetNameMesh, GetAnimationData, GetCullingData, BeginUpload…).
- For CPU-to-GPU uploads that originate in jobs, always return the job handle via Add*Writer methods (AnimatedSystem.AddAnimationWriter, AreaBatchSystem.AddColorWriter, Procedural* AddUploadWriter, etc.).
- For overlay textures, call OverlayInfomodeSystem.ApplyOverlay() (or ensure the system’s Apply completes) so Texture2D.Apply runs after jobs finish.
- Procedural heaps reserve index 0 (identity) — uploaded indices start from 1.
- Use RenderingSystem.PrepareRendering() to update frame globals before custom rendering code runs.
- When dealing with materials and VT bindings, use ManagedBatchSystem to complete VT requests and create materials on the main thread (CompleteVTRequests / ResetVT).
- Many helpers exist to avoid unsafe code (VFXUtils.SetChecked*, MaterialProperty utilities, FrustumPlanes helpers), but some high-performance APIs (FrustumPackets) require unsafe pointers.

Overall: this module is the rendering backbone—mix of managed systems, Burst jobs and GPU-backed buffers. Interaction is mostly through World.GetExistingSystemManaged/GetOrCreateSystemManaged, queries for prepared GPU resources, and disciplined JobHandle synchronization.

### Usage example
```csharp
using UnityEngine;
using Unity.Entities;
using Unity.Collections;
using Unity.Jobs;
using Game.Rendering;

public class RenderingModExample
{
    public void Example()
    {
        var world = World.DefaultGameObjectInjectionWorld;
        if (world == null) return;

        // 1) Obtain commonly used systems
        var aggregate = world.GetExistingSystemManaged<Game.Rendering.AggregateMeshSystem>();
        var areaBuffer = world.GetExistingSystemManaged<Game.Rendering.AreaBufferSystem>();
        var areaBatch = world.GetExistingSystemManaged<Game.Rendering.AreaBatchSystem>();
        var animated = world.GetOrCreateSystemManaged<Game.Rendering.AnimatedSystem>();
        var rendering = world.GetExistingSystemManaged<Game.Rendering.RenderingSystem>();
        var preCulling = world.GetExistingSystemManaged<Game.Rendering.PreCullingSystem>();
        var climate = world.GetOrCreateSystemManaged<Game.Rendering.ClimateRenderSystem>();
        var managedBatch = world.GetOrCreateSystemManaged<Game.Rendering.ManagedBatchSystem>();
        var terrain = world.GetExistingSystemManaged<Game.Rendering.TerrainRenderSystem>();

        // 2) Read an aggregated name mesh + materials (safe: getter completes deps as needed)
        int nameMatCount = aggregate.GetNameMaterialCount();
        if (nameMatCount > 0 && aggregate.GetNameMesh(0, out Mesh nameMesh, out int subMeshCount))
        {
            for (int s = 0; s < subMeshCount; s++)
            {
                if (aggregate.GetNameMaterial(0, s, out Material mat))
                {
                    // e.g. Graphics.DrawMesh(nameMesh, Matrix4x4.identity, mat, 0);
                }
            }
        }

        // 3) Access an area ComputeBuffer and draw procedurally
        if (areaBuffer.GetAreaBuffer(Game.Rendering.AreaType.Lot, out ComputeBuffer areaBuf, out Material areaMat, out Bounds bounds))
        {
            areaMat.SetBuffer("colossal_AreaTriangleBuffer", areaBuf);
            Graphics.DrawProcedural(areaMat, bounds, MeshTopology.Triangles, areaBuf.count * 3);
        }

        // 4) Enqueue animation frames from a job-friendly writer:
        JobHandle animDeps;
        var animWriter = animated.GetAnimationData(out animDeps);
        // schedule your burst job(s) that write frames and obtain producerJobHandle...
        JobHandle producer = default; // replace with your scheduled job handle
        animated.AddAnimationWriter(producer); // tell AnimatedSystem to wait for producer

        // 5) Read pre-culling results (complete returned handle before reading)
        JobHandle cullDeps;
        var cullList = preCulling.GetCullingData(readOnly: true, out cullDeps);
        cullDeps.Complete();
        for (int i = 0; i < cullList.Length; ++i) {
            var entry = cullList[i];
            // inspect entry.m_Entity, entry.m_Flags etc.
        }
        cullList.Dispose();

        // 6) Trigger an immediate lightning strike (main thread API)
        climate.LightningStrike(new Unity.Mathematics.float3(200f, 0f, 300f), new Unity.Mathematics.float3(210f, 0f, 310f));

        // 7) Ensure VT requests created by jobs are completed/applied on main thread
        managedBatch.CompleteVTRequests();

        // 8) Tweak terrain overlay texture on the main thread
        // (assign a Texture2D from Resources or your mod bundle)
        Texture2D myOverlay = Resources.Load<Texture2D>("MyMod/Textures/overlay");
        if (terrain != null) terrain.overrideOverlaymap = myOverlay;

        // 9) Ensure per-frame rendering globals are set before custom render work
        rendering.PrepareRendering();
        uint frameIdx = rendering.frameIndex;
        float tod = rendering.timeOfDay;
    }
}
```

---

## Game.Routes

A compact, practical summary of the Game.Routes module used by Cities: Skylines 2 for routing and public-transport ECS features.

Summary
- Purpose: low-level, Burst/job-friendly DOTS/ECS building blocks for routes, stops, segments, lanes, vehicles and route geometry. It provides blittable, serializable components and buffer elements, spatial query support (quad-tree), raycast jobs, route/waypoint connection and validation systems, and utilities for route behaviour and path-handling.
- Data model: small components and dynamic buffers represent routes and their pieces (Route, RouteInfo, RouteFlags, RouteNumber, RouteWaypoint, RouteSegment, RouteLane, RouteVehicle, CurveElement, CurveSource, WaypointDefinition, Position, AccessLane, etc.). Many marker/tag components identify special entities (BusStop, TrainStop, HiddenRoute, LivePath, WorkStop, etc.).
- Ownership and links: Connected/ConnectedRoute buffers and Owner components keep bidirectional links between route containers and elements; ReferencesSystem maintains these relationships. SubRoute/ConnectedRoute buffers let routes reference subroutes and connected route entities.
- Geometry and spatial queries: CurveElement/CurveSource store Bezier curve geometry. A NativeQuadTree (SearchSystem) is used for broadphase spatial queries. RaycastJobs implement a two-stage pipeline: FindRoutesFromTreeJob (quad-tree broadphase) and RaycastRoutesJob (parallel narrowphase) to find nearest waypoints/segments.
- Systems:
  - SegmentCurveSystem: rebuilds per-segment CurveElement buffers (Burst jobs, curve splitting).
  - RoutePathSystem / RoutePathReadySystem: detect lane/segment changes, queue pathfind work, populate PathTargets and notify icons.
  - InitializeSystem: assigns route numbers and selects vehicle prefabs for new routes.
  - ReferencesSystem / ElementSystem: maintain Owner links and mark route elements Deleted when a route is removed.
  - WaypointConnectionSystem: heavy-duty Burst-parallel pipeline that finds nearest lanes/access, updates PathTargets/WaypointDefinitions and emits PathTargetMoved events.
  - SearchSystem: maintains the quad-tree used by many systems and exposes safe reader/writer access patterns.
  - BoardingVehicleSystem: validates and clears stale boarding vehicle references.
- Utilities: RouteUtils contains route constants, boarding/exit helpers, departure scheduling, path method selection and modifier application. ValidationHelpers provide route/stop checks that enqueue ErrorData for diagnostics.
- Serialization & versioning: Many types implement ISerializable/IEmptySerializable and use version-aware read/write logic for backward compatibility with saved games.
- Design & performance: Types are designed to be safe for Burst and multithreaded jobs (blittable layouts, small marker components). Systems use IJobChunk, IJobParallelForDefer, ComponentLookup/BufferLookup, EntityCommandBuffer patterns and parallel accumulators for performant large-scale updates.

Typical usage pattern
- Create route-related entities and attach lightweight components or buffers.
- Let systems (InitializeSystem, SegmentCurveSystem, WaypointConnectionSystem, SearchSystem, etc.) operate automatically; mark entities with Updated/Deleted tags to trigger re-evaluation.
- For spatial queries, obtain the SearchSystem tree (respecting returned JobHandle dependencies), then use the RaycastJobs pipeline to perform broadphase + narrowphase tests in parallel.
- Use RouteUtils and ValidationHelpers inside systems/jobs where ECS lookups are available.

### Usage example
```csharp
using Unity.Entities;
using Unity.Mathematics;
using Unity.Collections;
using UnityEngine;
using Game.Routes;

public static class RoutesExample
{
    public static void CreateSimpleRoute()
    {
        var world = World.DefaultGameObjectInjectionWorld;
        var em = world.EntityManager;

        // 1) Create a stop (marker + position)
        Entity busStop = em.CreateEntity();
        em.AddComponentData(busStop, new BusStop()); // marker/tag (1-byte)
        em.AddComponentData(busStop, new Position(new float3(12f, 0f, 34f)));

        // 2) Create a route entity with metadata
        Entity route = em.CreateEntity();
        em.AddComponentData(route, new Route { m_Flags = 0, m_OptionMask = 0u });
        em.AddComponentData(route, new RouteNumber { m_Number = 7 });
        em.AddComponentData(route, new Color(new Color32(200, 60, 60, 255)));
        em.AddComponentData(route, new RouteInfo { m_Duration = 90f, m_Distance = 5.4f });

        // 3) Add waypoint/segment buffers and a simple waypoint definition
        var waypoints = em.AddBuffer<WaypointDefinition>(route);
        waypoints.Add(new WaypointDefinition(new float3(10f, 0f, 5f))); // logical waypoint

        var segments = em.AddBuffer<RouteSegment>(route);
        // segments.Add(new RouteSegment(someSegmentEntity)); // in real code reference segment entities

        // 4) Link a vehicle to the route (CurrentRoute component on a vehicle entity)
        Entity vehicle = em.CreateEntity();
        em.AddComponentData(vehicle, new CurrentRoute(route));

        // 5) Mark route as Updated so WaypointConnectionSystem will evaluate it next tick
        em.AddComponentData(route, new Updated());

        // 6) Example: adjust fare locally using modifiers buffer (used inside systems/jobs)
        var modifiers = em.AddBuffer<RouteModifier>(route);
        modifiers.Add(new RouteModifier { m_Delta = new float2(2.0f, 1.1f) }); // add + multiply example
        float baseFare = 10f;
        RouteUtils.ApplyModifier(ref baseFare, modifiers, RouteModifierType.TicketPrice);
        Debug.Log($"Adjusted fare: {baseFare}");

        // 7) Query the spatial search tree (safely obtain read access via SearchSystem)
        var searchSys = world.GetExistingSystemManaged<SearchSystem>();
        if (searchSys != null)
        {
            JobHandle deps;
            var tree = searchSys.GetSearchTree(readOnly: true, out deps);
            // If we need the tree immediately on main thread:
            deps.Complete();

            // Use tree.Query/nearest APIs here (pseudo-API provided by SearchSystem)
            // Example: var items = tree.Query(someBounds);
        }

        // Note: For raycasts use the FindRoutesFromTreeJob + RaycastRoutesJob pipeline shown
        // in Game.Routes.RaycastJobs. That pipeline requires building inputs (RaycastInput),
        // passing the quad-tree items and scheduling jobs with appropriate Component/Buffer lookups.
    }
}
```

---

## Game.SceneFlow (SceneFlow module)

A compact summary of the scene‑flow subsystem used by Cities: Skylines 2. Game.SceneFlow implements fullscreen overlay screens and startup/loading/sign‑in flows, helpers for scoping input and overlay state, and high‑level lifecycle orchestration via GameManager.

Core pieces
- GameManager: the central bootstrap/runtime manager. Initializes platform, UI and ECS world, loads prefabs/thumbnails, runs save/load workflows, registers mods, drives per‑frame updates and shutdown. Exposes helpers/events such as WaitForReadyState, RunOnMainThread, RegisterUpdater, Load/Save APIs and SetScreenActive<T>.
- IScreenState / FullScreenOverlay: abstraction for modal/fullscreen flows. IScreenState defines Execute(GameManager, CancellationToken) and supplies static helpers (WaitForInput, WaitForDevice, WaitForUser) that await input or platform events. FullScreenOverlay is a base class for overlays that centralizes action registration, m_Done/m_CompletedEvent handling and common activation/teardown plumbing.
- Concrete overlay screens: many small screen implementations (EngagementScreen, SplashScreenSequence, LoadingScreen, ControllerDisconnectedScreen, ControllerPairingScreen, LoggedOutScreen, CorruptSaveDataScreen, SwitchUserScreen, ValidationScreen, WaitScreen, etc.). Pattern: enable temporary input actions (EnabledActionScoped), create an input overlay barrier to block normal input, activate an OverlayScreen via OverlayBindings and await user action or platform tasks.
- Input scoping / RAII helpers:
  - EnabledActionScoped: temporarily enables an input ProxyAction and optionally sets display name/priority. Restores state on Dispose and can be implicitly used as an InputAction.
  - Overlay input barriers (InputManager.instance.CreateOverlayBarrier) prevent gameplay/UI input while overlays are active. These are used with disposables to auto‑cleanup.
- OverlayBindings and OverlayScreen enum: OverlayBindings manages which fullscreen overlay is active (ScopedScreen helper), per‑layer progress values (OverlayProgressType: Outer/Middle/Inner), hints/corrupt messages and emits onScreenActivated events. OverlayScreen enumerates available overlay states.
- Asset, save, and persistence helpers:
  - AssetLibrary groups AssetCollection references and can register prefabs with a PrefabSystem with cancellation and progress reporting.
  - SaveHelpers centralizes platform‑aware save paths and deletion semantics.
- Async utilities and UI readiness:
  - AsyncHelpers.AwaitWithTimeout lets you check if a Task completes within a TimeSpan without propagating its result.
  - UserInterface (cohtml view host) sets up CompositeBindings (localization, overlays, input hints, app state), handles view events (cursor/caret/focus/navigation) and exposes WaitForBindings so startup can await UI readiness.

Common patterns and usage notes
- RAII/scoped usage is pervasive: EnabledActionScoped, OverlayBindings.ScopedScreen, ActivateScreenScoped and overlay barrier disposables are used in using blocks so registration and UI state are automatically cleaned up even on exceptions.
- Async + cooperative cancellation: Execute methods accept CancellationToken. IScreenState helpers use TaskCompletionSource and carefully subscribe/unsubscribe to events.
- Separation of concerns: FullScreenOverlay handles input/action wiring while concrete screens implement flow‑specific logic (sign‑in, device pairing, waiting for platform tasks, etc.).
- Most screens use IScreenState helper methods (WaitForInput/WaitForDevice/WaitForUser) and may show a WaitScreen while awaiting asynchronous platform/sign‑in calls.

### Usage example
```csharp
using System;
using System.Threading;
using System.Threading.Tasks;
using Game.SceneFlow;

public class SceneFlowDemo
{
    // Call from an async mod initialization or other async context.
    public async Task DemoAsync()
    {
        // 1) Wait for the game to be ready (UI/world loaded)
        await GameManager.instance.WaitForReadyState();

        // 2) Use GameManager helper to activate a built-in screen (runs the screen's Execute)
        //    This will handle activation and teardown via OverlayBindings.
        await GameManager.instance.SetScreenActive<EngagementScreen>();

        // 3) Alternatively, run a screen instance directly with a cancellation token.
        using var cts = new CancellationTokenSource(TimeSpan.FromSeconds(30));
        var validation = new ValidationScreen();
        try
        {
            await validation.Execute(GameManager.instance, cts.Token);
            // ValidationScreen currently logs OK/Cancel — add follow-up flow here.
        }
        catch (OperationCanceledException)
        {
            // Handle cancellation (timeout or requester cancelled)
        }

        // 4) Show the wait overlay while awaiting a long‑running task.
        var waitScreen = new WaitScreen();
        var backgroundWork = Task.Run(async () =>
        {
            // Simulate background work (save/export/network call, etc.)
            await Task.Delay(TimeSpan.FromSeconds(2));
        });

        // WaitScreen will activate the overlay and an input barrier for the duration of backgroundWork.
        await waitScreen.Execute(GameManager.instance, CancellationToken.None, backgroundWork);
    }
}
```

---

## Game.Serialization

A consolidated summary of the Game.Serialization module used by Cities: Skylines 2. This module implements the engine's ECS-based save/load, prefab remapping, and post-load data-migration/fixup pipeline. It is composed of many GameSystemBase systems and Burst IJobChunk jobs whose responsibilities include:

- Save/load orchestration
  - SaveGameSystem and LoadGameSystem coordinate one-shot save/load passes (RunOnce) and expose contexts/streams for serializer jobs.
  - SerializerSystem drives entity (de)serialization via component/system serializer libraries and exposes total size / SetDirty semantics.

- Raw I/O helpers
  - ReadSystem / ReadBuffer: read (optionally compressed) save data into NativeArray<byte> and return a ReadBuffer that must be disposed (Done/Done(JobHandle)).
  - WriteSystem / WriteBuffer: collect WriteBuffer objects (NativeList<byte> + JobHandle dependencies), compress/write them to the stream, and dispose them after job completion.

- Prefab indexing & remapping
  - BeginPrefabSerializationSystem, EndPrefabSerializationSystem, ResolvePrefabsSystem, Primary/SecondaryPrefabReferencesSystem and CheckPrefabReferencesSystem: build loaded-index → runtime-prefab maps, update PrefabData.m_Index, remap stored prefab indices to runtime Entities, and provide PrefabReferences helpers for jobs that mark/translate prefab references.
  - PrefabReferences: value helper that exposes mapping and a cache for repeated translation in jobs and supports a loading-mode.

- Post-deserialize buffer population and relationship repair
  - Many generated systems (ConnectedEdgeSystem, ConnectedBuildingSystem, PassengerSystem, HouseholdCitizenSystem, InstalledUpgradeSystem, OwnedVehicleSystem, etc.) append entries to owner DynamicBuffers after deserialization, or remove/mark entities when target buffers are missing.
  - Route/Flow/Electricity/Connectivity systems rebuild runtime relation buffers (ConnectedEdge, RouteWaypoint, ElectricityFlowEdge, etc.) from saved indices and prefab data.

- Data migrations & compatibility
  - Version/format-gated systems (e.g., CompanyAndCargoFixSystem, HomelessAndWorkerFixSystem, PlaceholderCleanupSystem, QuantityObjectMissingSystem) run once for older saves to add/remove components, set defaults, or convert obsolete data.
  - InitializeObsoleteSystem and RequiredComponentSystem perform heavier archetype/component migrations during load.

- Concurrency, safety and patterns
  - Most heavy work runs in Burst IJobChunk / IJobParallelFor with cached TypeHandle structs converted via InternalCompilerInterface calls in OnUpdate.
  - Structural changes from jobs are made via DeserializationBarrier (EntityCommandBuffer) or ECB.ParallelWriter; producers must register JobHandles with the barrier (AddJobHandleForProducer).
  - BufferLookup / ComponentLookup / BufferAccessor are used for safe random-access writes to dynamic buffers from jobs; use HasBuffer / TryGetBuffer checks before writes.
  - Temporary native containers (NativeArray, UnsafeList) follow explicit lifetimes and are disposed/deferred via JobHandles; many systems expose Begin/End patterns (e.g., CheckPrefabReferencesSystem.BeginPrefabCheck / EndPrefabCheck) to coordinate temporary state and dependencies.

Modder guidance / safety notes:
- Do not call system.OnUpdate manually unless you fully control dependency chains; instead obtain the system and let the world run it, or use the provided RunOnce helper APIs for single-pass flows.
- When you want entities to be processed by these systems, ensure they have the required components/buffers (AddComponent<T>(), AddBuffer<T>()) so the EntityQuery includes them.
- If your jobs write the same components/buffers as the built-in systems, combine JobHandles properly and register consumers with the appropriate system (CheckPrefabReferencesSystem.AddPrefabReferencesUser, DeserializationBarrier.AddJobHandleForProducer).
- Gate any migration code by save version/format flags in LoadGameSystem.context to avoid rerunning migrations on newer saves.
- If you add new prefab-referencing components, integrate them into CheckPrefabReferencesSystem / PatchReferences hooks so remapping runs on load and when prefabs are reindexed.

### Usage example
A compact example showing common interactions: (1) creating and writing a WriteBuffer and running a single save pass, and (2) running a one-shot load and using CheckPrefabReferencesSystem to provide PrefabReferences to jobs.

```csharp
using System;
using System.IO;
using System.Threading.Tasks;
using Unity.Collections;
using Unity.Jobs;
using Unity.Entities;
using Game.Serialization;

public static class SerializationExample
{
    // Save example: create a raw write buffer, fill bytes, and invoke SaveGameSystem.RunOnce()
    public static async Task DoSaveAsync(World world, Stream outStream)
    {
        var writeSystem = world.GetOrCreateSystemManaged<WriteSystem>();
        var saveSystem  = world.GetOrCreateSystemManaged<SaveGameSystem>();

        // Create a write buffer, write some bytes, and mark it done (no background jobs)
        var buf = writeSystem.AddBuffer(BufferFormat.Raw);
        buf.buffer.AddRange(new byte[] { 0xDE, 0xAD, 0xBE, 0xEF });
        buf.Done(); // no JobHandle attached

        // Configure save system and run a single save pass
        saveSystem.stream = outStream;
        // optionally set saveSystem.context / referencedContent if needed

        await saveSystem.RunOnce(); // returns when the write job(s) are completed
    }

    // Load example: run LoadGameSystem.RunOnce and use CheckPrefabReferencesSystem to mark references in worker jobs
    public static async Task DoLoadAndFixupAsync(World world, Colossal.Serialization.Entities.Context loadContext, NativeArray<Entity> referencedPrefabs)
    {
        var loadSys = world.GetOrCreateSystemManaged<LoadGameSystem>();
        var checkSys = world.GetOrCreateSystemManaged<CheckPrefabReferencesSystem>();

        loadSys.context = loadContext;

        // Start the single-frame deserialize pass
        await loadSys.RunOnce();

        // Example: initialize a prefab-check pass for jobs that will mark/translate prefab refs
        JobHandle incomingDeps = default;
        checkSys.BeginPrefabCheck(referencedPrefabs, isLoading: true, incomingDeps);

        // Obtain the PrefabReferences helper and dependency for user jobs
        JobHandle userDeps;
        var prefabRefs = checkSys.GetPrefabReferences(/*a SystemBase/owner if required*/ null, out userDeps);

        // Schedule a sample job that would use prefabRefs (pseudo-code; real jobs require proper TypeHandles)
        // MyMarkingJob.Schedule(..., userDeps);

        // Register your job handle as a user so the check system waits for your mark jobs to complete
        // checkSys.AddPrefabReferencesUser(myMarkingJobHandle);

        // Finalize the prefab check; this returns a handle that completes indexing and disposes temporaries
        checkSys.EndPrefabCheck(out JobHandle finalizeDeps);

        // Wait for finalizeDeps before disposing referencedPrefabs NativeArray (or any temporaries)
        finalizeDeps.Complete();
        referencedPrefabs.Dispose();
    }
}
```

If you want, I can:
- Produce per-system cheat sheets listing input components/buffers, outputs, and which buffers to add so a given system will process your entities, or
- Generate a minimal runnable test system that mirrors a concrete migration (e.g., QuantityObjectMissingSystem) to validate mod behavior against the serialization pipeline.

---

## Game.Settings

A consolidated overview of the Game.Settings module used by Cities: Skylines 2. This module implements the game's persisted/settings system, a flexible QualitySetting framework for graphics/HDRP subsystems, and a rich set of UI/attribute helpers used by the automatic settings UI. It is the central place where settings are declared, persisted, presented and applied to runtime systems (AudioManager, InputManager, HDRP Volume components, rendering/culling systems, AutoSave, Simulation, etc.).

Key concepts and responsibilities
- Setting / QualitySetting abstraction
  - Setting: base class for persisted, applyable setting groups. Exposes SetDefaults(), Apply()/ApplyAndSave(), reflection helpers for equality and registration with the Options UI, and an onSettingsApplied event.
  - QualitySetting<T>: generic base for per-subsystem quality control with Level presets (Disabled, Low, Medium, High, Custom). Presets are registered so the UI can enumerate and apply them; SetLevel initializes values, and Apply writes runtime changes.
- Persistence & grouping
  - Settings are saved to named FileLocation groups (SharedSettings builds and owns the main groups). SharedSettings.instance constructs and holds all top-level Setting subclasses (graphics, audio, input, gameplay, interface, editor, modding, radio, userState), loads/saves them, registers pages in the Options UI, and exposes bulk operations (Apply, Reset, LoadUserSettings).
- Graphics & HDRP integration
  - GraphicsSettings aggregates many QualitySetting subclasses for HDRP features: DynamicResolutionScale, AntiAliasing, Clouds, Fog, Volumetrics, DepthOfField, Shadows, Water, Terrain, Texture, LOD/Animation/SSAO/SSGI/SSR, MotionBlur and more.
  - Many quality wrappers map to HDRP Volume components or renderer APIs (HDAdditionalCameraData, HDShadowSettings, TerrainRendering, Fog, WaterRendering). Several create or locate VolumeProfile/VolumeComponents and set parameters at runtime.
  - DLSS/FSR2/upscaler interactions are handled (e.g., some settings disable camera AA or dynamic resolution when an upscaler is active to avoid conflicts).
- Input & UI
  - InputSettings / KeybindingSettings provide dynamic binding UIs constructed from InputManager and the Unity Input System; supports device groups, reset-to-default, and read-only default views.
  - InterfaceSettings handles locale resolution, UI style/scale/transparency, units/time formats and dismissed confirmations.
  - A large family of SettingsUI* attributes supply metadata (display name, descriptions, grouping, sliders, dropdowns, directory pickers, keybinding defaults, hide/disable-by-condition rules, confirmation dialogs, developer-only flags). The automatic Options UI consumes these via reflection.
- Screen & display utilities
  - ScreenHelper and ScreenResolution provide resolution lists, mapping between internal DisplayMode and Unity FullScreenMode, and helpers to pick the closest available resolution.
- Audio, Radio, Modding, UserState
  - AudioSettings maps master/menu/menu/UI/ingame/radio volumes, clip memory budget and forwards changes to AudioManager and Radio runtime APIs.
  - RadioSettings exposes FFT/visualizer options for the in-game radio.
  - ModdingSettings exposes the toolchain UI for install/repair/update/uninstall operations and per-dependency controls.
  - UserState stores per-user toggles (leftHandTraffic, cheats, cloud target), tutorial progress, last save metadata and exposes ResetTutorials/SetDefaults.
- Safe application patterns
  - Apply() implementations guard for missing runtime systems (null checks), perform lazy caching of runtime references, and may no-op in editor/test contexts. Many QualitySetting constructors call SetLevel(level, apply:false) to let callers tweak before Apply() persists changes.
- Notable behaviors & tips
  - Preset registration order matters for correct index/level transfer inside GlobalQualitySettings.
  - Many quality settings are implemented by writing to HDRP Volume components and updating scene/system instances (TerrainSurface.instances, WaterSurface.instances, ManagedBatchSystem, RenderingSystem).
  - The attribute system supports either literal values or a (Type, methodName) provider pattern; consumer code must call the provider via reflection with the expected signature.
  - Use SharedSettings.instance rather than constructing your own manager — it wires options UI registration, loading/saving and runtime hooks.

Major classes & examples (condensed)
- SharedSettings: central manager (holds audio, graphics, input, gameplay, interface, editor, modding, radio, userState).
- GraphicsSettings: top-level graphics options, display/resolution, vSync, DLSS/FSR2 integration, creates Volume override profiles, and aggregates many QualitySetting instances.
- About: runtime/version info and platform integrations list for the About settings page.
- AudioSettings: master/UI/menu/ingame/radio volumes + clip memory budget.
- InputSettings / KeybindingSettings: input sensitivities, invert toggles, dynamic binding UI and device-group handling.
- QualitySetting subclasses: AnimationQualitySettings, AntiAliasingQualitySettings, SSAO/SSGI/SSR/MotionBlur, ShadowsQualitySettings, TerrainQualitySettings, TextureQualitySettings, VolumetricsQualitySettings, WaterQualitySettings, LevelOfDetailQualitySettings, etc.
- ScreenHelper / ScreenResolution: resolution handling and helpers for main-thread resolution operations.
- UI attributes: SettingsUIDisplayNameAttribute, SettingsUISliderAttribute, SettingsUIDropdownAttribute, SettingsUIKeyboardBindingAttribute, SettingsUIGamepadBindingAttribute, SettingsUIHideByConditionAttribute, SettingsUIDisableByConditionAttribute, SettingsUIWarningAttribute, and many more.

Runtime integration
- Applies changes to AudioManager, Radio, HDAdditionalCameraData (DLSS/AA), AdaptiveDynamicResolutionScale, HDRP Volume components, Rendering/BatchMesh/ManagedBatch systems, AutoSaveSystem, SimulationSystem and PlatformManager/PdxSdkPlatform (telemetry/consent).
- Settings pages are auto-generated from Setting subclasses and property attributes; UI code uses reflection to call provider methods for dynamic dropdowns/warnings/conditions.

### Usage example
```csharp
using UnityEngine;
using Game.Settings;

// Use SharedSettings singleton (preferred)
var shared = SharedSettings.instance;

// Read "About" / version info
var about = new About();
Debug.Log($"Game version: {about.gameVersion}");
var aboutPage = about.GetPageData("About", showAdvanced: true);

// Change audio and apply immediately
var audio = shared?.audio ?? new AudioSettings();
audio.masterVolume = 0.8f;
audio.radioActive = false;
audio.clipMemoryBudget = 320; // MB
audio.Apply(); // forwards to AudioManager / Radio

// Modify graphics: set fullscreen/resolution and apply nested quality settings
var graphics = shared?.graphics ?? new GraphicsSettings();
graphics.displayMode = DisplayMode.Fullscreen;
graphics.resolution = ScreenHelper.currentResolution; // pick one from ScreenHelper
graphics.vSync = true;
graphics.dlssQuality = GraphicsSettings.DlssQuality.Auto;
graphics.Apply(); // updates window, camera HDAdditionalCameraData, nested QualitySettings

// Adjust one per-feature quality subsystem (animation skinning) and apply just it
var anim = graphics?.GetQualitySetting<AnimationQualitySettings>();
if (anim != null) {
    anim.maxBoneInfuence = AnimationQualitySettings.Skinning.TwoBones;
    anim.Apply(); // updates shader keyword / runtime skinning state
}

// Interface settings: force locale and UI style
var iface = shared?.interfaceSettings ?? new InterfaceSettings();
iface.locale = "en"; // use "os" to pick system locale
iface.interfaceStyle = "bright-blue";
iface.Apply();

// Persist user-state toggle and reset tutorials
var user = shared?.userState ?? new UserState();
user.leftHandTraffic = true;
user.ApplyAndSave();
user.ResetTutorials();
```

---

## Game.Simulation

A concise overview of the Game.Simulation module used by Cities: Skylines 2.

Summary
- Purpose: Game.Simulation implements the core city simulation: citizens & households, vehicles & transport, services (police, fire, healthcare, garbage, mail, utilities), resource production/consumption/flow (electricity, water, goods), land use/zone evaluation & spawning, environmental systems (air/noise/ground/groundwater pollution, wind, weather, water surface), and bookkeeping (budget, taxes, statistics, XP, milestones). It includes both high-level AI/dispatch pipelines (pathfind request → path results → dispatch/boarding) and low-level graph/solver code (electricity & fluid flow solvers, max-flow variants).
- Architectural patterns:
  - ECS-first: systems are GameSystemBase/SystemBase-like and operate over EntityQueries.
  - Burst + jobs: heavy per-entity logic is in Burst-compatible IJobChunk/IJob/IJobParallelFor to scale to thousands of entities.
  - Deferred structural changes: jobs record Add/Remove/Create operations through an EndFrameBarrier/EntityCommandBuffer.ParallelWriter (or ModificationBarrier), and systems must register producer JobHandles (AddJobHandleForProducer).
  - Native containers & queues: NativeArray/NativeList/NativeQueue and accumulators are used for inter-job communication and aggregation; when systems expose these arrays they usually return a JobHandle that callers must respect (Complete or combine).
  - Staggered updates: many systems use shared UpdateFrame / GetUpdateInterval/GetUpdateOffset or kUpdatesPerDay to spread work across frames.
  - Pathfinding pipeline: systems enqueue SetupQueueItem entries into PathfindSetupSystem which builds PathInformation; vehicle/citizen AI then consumes path results to act.
  - Serialization/versioning: many small POD structs implement custom serialization (ISerializable / stride serialization) and handle legacy save versions.
- Key subsystems (representative, not exhaustive):
  - Accidents / emergencies: AccidentCreatureSystem/AccidentVehicleSystem/AccidentSiteSystem, Police/Fire dispatch and station AI, FireEngineAISystem/FireAircraftAISystem, Evacuation systems.
  - Citizens & households: AgingSystem, CitizenFindJobSystem, CitizenHappinessSystem, CitizenTravelPurposeSystem, HouseholdSpawn/MoveAway/FindProperty/Behavior systems.
  - Vehicles & transport: CarNavigationSystem, CarMoveSystem, Train/Watercraft/Transport AI, TransportBoardingHelpers, TransportDepot/Line/Stop systems, VehicleLaunch/OutOfControl/Collision systems.
  - Utilities & flows: ElectricityFlowSystem (graph builders, multi-phase solver), WaterSystem & WaterPipeFlowSystem (graph & solver), ResourceProducer/Buyer/Exporter, ResourceFlow/Availability.
  - Environment & hazards: AirPollutionSystem, NoisePollutionSystem, GroundPollution/GroundWater, Wind/WindSimulation, WeatherPhenomenon, Water surface (GPU readback).
  - City economy & services: BudgetSystem, TaxSystem, CityServiceBudget/System/Upkeep/Statistics, Company systems (CommercialAISystem, BuyingCompanySystem), ProductionSpecialization, TradeSystem.
  - Zoning & placement: ZoneEvaluationUtils, ZoneSpawnSystem, AreaSpawnSystem, NaturalResourceSystem, LandValue/TerrainAttractiveness systems.
  - Support infra: EndFrameBarrier, PathfindSetupSystem, IconCommandSystem, various search systems (NetSearch/StaticSearch/Terrain/Water).
- Modding & integration guidance (practical rules):
  - Defer structural changes from jobs using an EndFrameBarrier ECB and call AddJobHandleForProducer(jobHandle).
  - When a system returns Native arrays/lists + JobHandle, either Complete the handle before reading or combine the handle into your job and register yourself (AddReader/AddQueueWriter APIs where provided).
  - Avoid managed types in jobs; use ComponentLookup/BufferLookup/TypeHandle prepared each frame.
  - Respect UpdateFrame slicing when adding chunk jobs to keep work distribution aligned with the game.
  - Use singletons / parameter data (prefab-driven data & parameter singletons) to tune behaviour rather than patching jobs.
  - For pathfinding & vehicle dispatch, use PathfindSetupSystem / PathfindQueue APIs rather than writing PathElement/PathInformation manually.
- Performance notes:
  - Many systems run at reduced intervals (16 / 64 / 128 / 256 frames) or use shared UpdateFrame filtering. Follow these conventions for any complementary jobs.
  - Large solvers (electricity & pipe flow) are incremental across frames—use their resume capabilities rather than forcing full solves in one frame.

### Usage example
```csharp
// Example mod snippet: obtain systems, create a simple accident event and read an exported popularity list safely.
// Run from main thread (SystemBase/mono behaviour context).

using Unity.Entities;
using Unity.Jobs;
using UnityEngine;

var world = World.DefaultGameObjectInjectionWorld;
if (world == null) return;
var em = world.EntityManager;

// 1) Get some core systems
var simSys = world.GetOrCreateSystemManaged<Game.Simulation.SimulationSystem>();
var accidentCreatureSys = world.GetOrCreateSystemManaged<Game.Simulation.AccidentCreatureSystem>();
var brandSys = world.GetExistingSystemManaged<Game.Simulation.BrandPopularitySystem>();
var airPollutionSys = world.GetExistingSystemManaged<Game.Simulation.AirPollutionSystem>();

// 2) Mark a citizen/creature entity as involved in an accident (systems will pick this up)
Entity target = /* some citizen/animal entity */;
if (em.Exists(target))
{
    em.AddComponentData(target, new Game.Simulation.InvolvedInAccident { m_Event = Entity.Null });
}

// 3) Manually create a lightweight AccidentSite event entity (optional)
var archetype = em.CreateArchetype(typeof(Game.Simulation.AccidentSite));
var site = em.CreateEntity(archetype);
em.SetComponentData(site, new Game.Simulation.AccidentSite {
    m_Event = Entity.Null,
    m_CreationFrame = simSys.frameIndex,
    m_Flags = Game.Simulation.AccidentSiteFlags.StageAccident
});

// 4) Read brand popularity list produced by BrandPopularitySystem (job handle returned must be completed)
if (brandSys != null)
{
    JobHandle h;
    var list = brandSys.ReadBrandPopularity(out h);
    h.Complete(); // ensure producer job finished
    for (int i = 0; i < list.Length; ++i)
    {
        var entry = list[i];
        Debug.Log($"Brand {entry.m_BrandPrefab} popularity {entry.m_Popularity}");
    }
    // list is owned by the system (do not dispose unless API says so)
}

// 5) Pollution helper: get center of a pollution cell (useful when adding pollution)
var cellCenter = Game.Simulation.AirPollutionSystem.GetCellCenter(10);
Debug.Log($"Air pollution cell center: {cellCenter}");

// Notes:
// - If you schedule jobs that enqueue into PathfindSetupSystem or write to EndFrameBarrier, register your job handles
//   with those systems (AddQueueWriter / AddJobHandleForProducer) so playback & consumers wait correctly.
```

If you want, I can produce:
- a one-page quick-reference for the most important public helpers (EndFrameBarrier usage, PathfindSetup patterns, reading Native arrays with JobHandles),
- or a focused deep-dive and runnable example for a single subsystem (electricity flow solver, water-pipe flow, transport boarding, or citizen/pathfind integration).

---

## Game.Tools

Game.Tools is the Cities: Skylines 2 tooling module: a collection of ECS components, Burst-friendly jobs, systems and helpers that implement the game's interactive tools pipeline (placement, snapping, previews, brushes, zoning, nets/routes, objects, water sources, notifications, prefabs) and the apply/commit lifecycle for edits. Its core design enforces a consistent workflow for multithreaded editing:

- Temp → Process → Apply
  - Tools create short-lived "Temp" / definition entities (CreationDefinition, BrushDefinition, ObjectDefinition, NetCourse, WaypointDefinition, WaterSourceDefinition, etc.) to represent previews/requests.
  - Many systems run Burst jobs (IJobChunk, IJobParallelForDefer) to compute geometry, snapping, search results, coverage, patches and reference remaps in parallel.
  - Structural changes are applied only via EntityCommandBuffer.ParallelWriter obtained from barrier systems (ToolOutputBarrier, ToolReadyBarrier, ModificationBarrier1/2, ToolOutputSystem) so playback is safe on the main thread.
  - Apply* systems (ApplyBrushesSystem, ApplyAreasSystem, ApplyNetSystem, ApplyObjectsSystem, ApplyRoutesSystem, ApplyPrefabsSystem, ApplyWaterSourcesSystem, etc.) detect Temp-marked entities and commit creates/updates/deletes using ECBs.

- Data copying, reference remap and reuse
  - UpdateComponent<T>/UpdateBuffer<T> helpers copy component values and buffers from Temp/preview entities to originals or new runtime entities inside jobs.
  - Jobs patch Temp references (temps pointing to other temps) and remap to originals or newly-created owners; deleted/reuse maps are commonly used to recycle deleted entities and avoid excess instantiation.
  - Prefab baking (ApplyPrefabsSystem) extracts sub-objects/nets/areas and writes PrefabBase assets when SaveInstance is requested.

- Tools, snapping and create-definition flow
  - ToolBaseSystem is the common base for interactive tools (ObjectToolSystem, NetToolSystem, TerrainToolSystem, ZoneToolSystem, SelectionToolSystem, RouteToolSystem, TerrainToolSystem, etc.). It handles input proxying, raycast setup, brush/prefab management and common lifecycle hooks.
  - SnapJob / CreateDefinitionsJob patterns: control points and snap results are collected into NativeLists/NativeArrays and jobs convert them into CreationDefinition/ObjectDefinition/NetCourse/BrushDefinition entities for preview or commit.
  - CourseSplitSystem, GenerateNodes/Edges/Areas/Objects/Routes/WaterSourcesSystems consume definitions to create or reuse runtime entities via modification barriers.

- Animation & previews
  - Lightweight Animation component stores per-entity preview animation state (target/current transform, sway, push factor). AnimationSystem (Burst) integrates sway and updates transforms; AnimationUpdateSystem builds prefab->animation template maps for writers.

- Performance & concurrency details
  - Systems use cached TypeHandle structs (ComponentTypeHandle/ComponentLookup/BufferLookup) for Burst jobs. Native containers (NativeHashMap, NativeParallelMultiHashMap, NativeList, NativeArray) are sized to entity counts; jobs return producer JobHandles which systems register with barriers (AddJobHandleForProducer / AddSearchTreeReader / AddOwnerMapReader) to avoid races.
  - Structural changes are always deferred to ECBs from modification barriers. Jobs must register dependencies with these barriers.

- Utilities, enums and tags
  - Useful small types: Temp/TempFlags, CreationFlags/CreationDefinition, Brush/BrushDefinition, PrefabRef, AgeMask, ApplyMode, Snap & SnapLine, Selection tags (Selected/Highlighted/Hidden), IconDefinition, Error/Warning tags, EditorContainer.
  - ZoningFlags and ZoningInfoSystem provide zoning evaluation result lists for paint/fill tools.

Modder guidance (practical rules)
- Create Temp/definition entities (with expected component sets) to trigger systems rather than directly mutating game-state entities from worker jobs.
- When scheduling Burst jobs that read shared systems (terrain/water/search/reuse maps), register the job handles with the appropriate system readers (AddSearchTreeReader/GetReusedOwnerMap/AddOwnerMapReader).
- Use Barrier-provided EntityCommandBuffer.ParallelWriter to perform structural changes; do not directly call EntityManager structural APIs from jobs.
- Preserve Burst-friendly code (blittable types, cached type handles) when writing new jobs or modifying internal job structs.
- Dispose temporary Native allocations and respect lifetimes (Allocator.Temp vs Persistent) and job dependencies.

Overall: Game.Tools provides the end-to-end, multithreaded tooling pipeline: from snapping and preview generation in Burst, through remapping and reuse, to safe ECB application and prefab baking — enabling scalable tool interactions and giving modders a well-defined pattern to extend or integrate into the toolflow.

### Usage example
```csharp
// Create a temporary brush/preview entity that the ApplyBrushesSystem / GenerateBrushesSystem will process.
// Run on main thread in a mod/system with access to EntityManager.

using Unity.Entities;
using Unity.Mathematics;
using Game.Tools;

public static class ToolExamples
{
    public static void CreateTempBrush(EntityManager em, Entity brushPrefab, Entity toolEntity)
    {
        // Create an entity with Temp, Brush and PrefabRef so tool systems pick it up
        var e = em.CreateEntity(typeof(Temp), typeof(Brush), typeof(PrefabRef));

        // Temp: no original => ApplyBrushes/GenerateBrushes treat this as a creation preview
        em.SetComponentData(e, new Temp { m_Original = Entity.Null, m_Flags = 0, m_Cost = 0 });

        // Brush: tool cursor state
        em.SetComponentData(e, new Brush
        {
            m_Tool = toolEntity,
            m_Position = new float3(100f, 0f, 200f),
            m_Start = new float3(99f, 0f, 199f),
            m_Target = new float3(101f, 0f, 201f),
            m_Angle = 0f,
            m_Size = new float2(30f, 30f),
            m_Strength = 0.5f,
            m_Opacity = 1f
        });

        // PrefabRef: points to a brush prefab entity carrying BrushData/BrushCell buffers
        em.SetComponentData(e, new PrefabRef { m_Prefab = brushPrefab });

        // Optionally add Updated so generation systems know to process it immediately
        em.AddComponentData(e, new Unity.Entities.Updated());
        // The tool pipeline (GenerateBrushesSystem / ApplyBrushesSystem) will pick this up,
        // schedule jobs to build cells/previews/terrain modifiers and then commit changes
        // via the ToolOutputBarrier/ApplyBrushesSystem ECB.
    }
}
```

---

## Game.Triggers

The Game.Triggers module implements Cities: Skylines 2’s in-game trigger/notification layer. It provides lightweight data components (Chirp, LifePathEvent, RadioEvent, TriggerAction, etc.), buffer elements (ChirpEntity, ChirpLink, LifePathEntry), enums/flags (ChirpFlags, TargetType) and multiple systems that create, deduplicate, schedule and persist trigger-driven events.

Summary of responsibilities and patterns:
- Producers/consumers: Systems expose NativeQueue/NativeQueue-like buffers (TriggerSystem.CreateActionBuffer, CreateChirpSystem.GetQueue, LifePathEventSystem.GetQueue, RadioTagSystem.GetInputQueue / GetEmergencyInputQueue). When enqueuing from Jobs you must return JobHandles to the consumer via AddActionBufferWriter / AddQueueWriter / AddInputQueueWriter so the consumer can wait for completion.
- Serialization and save/load: Many components implement ISerializable so entity references survive saves. TriggerSystem also persists per-prefab last-created frames (m_TriggerFrames) to enforce frequency limits across saves. Systems follow versioned deserialization: newer fields are read only when the save version supports them.
- High-throughput systems: Heavy use of Burst jobs and Native collections (NativeQueue, NativeParallelHashMap, NativeList) with throttling/deduplication (recent maps, frame delays, per‑prefab limits) to avoid spamming and reduce CPU.
- Chirps & virality: Chirp entities store sender/creation frame/like counts and viral parameters. ChirpLikeCountSystem advances like counts toward targets on a sparse interval using a viral curve with stochastic growth.
- Chirp creation & deduplication: CreateChirpSystem consumes ChirpCreationData, selects prefabs/participants, computes targetLikes/viral params (using city stats or randomness), and creates chirp entities via an ECB inside Burst jobs while avoiding duplicates using recent-chirps maps.
- LifePath events: LifePathEventSystem consumes LifePathEventCreationData, either creates LifePathEvent entities or forwards chirps to CreateChirpSystem; it appends LifePathEntry buffers to followed citizens and cleans up entries for deleted citizens.
- Trigger orchestration: TriggerSystem collects TriggerAction queues, evaluates trigger prefabs and conditions, enforces per-trigger/per-prefab intervals, and dispatches creation requests to CreateChirpSystem, LifePathEventSystem, RadioTagSystem, or tutorial systems.
- Notifications & radio: NotificationTriggerSystem converts created/resolved notifications into TriggerAction entries. RadioTagSystem buffers and deduplicates normal and emergency radio tags (with per-tag delays) for audio systems.
- Utilities: Systems like EarlyGameOutsideConnectionTriggerSystem detect early-game conditions (missing outside connection) and enqueue triggers after controlled delays.
- Modding tips:
  - Always use the provided queue/getter APIs and register job dependencies when writing from jobs.
  - Respect Burst/job-safety rules (no managed types inside jobs).
  - Honor update throttles (use GetUpdateInterval values) and per-prefab frequency limits to avoid performance or gameplay issues.

### Usage example
```csharp
// Example 1: Enqueue a generic TriggerAction (main-thread producer)
var triggerSystem = World.DefaultGameObjectInjectionWorld
    .GetExistingSystemManaged<Game.Triggers.TriggerSystem>();

var actionBuffer = triggerSystem.CreateActionBuffer();
actionBuffer.Enqueue(new Game.Triggers.TriggerAction
{
    m_TriggerType = /* your TriggerType value */,
    m_TriggerPrefab = somePrefabEntity,
    m_PrimaryTarget = senderEntity,
    m_SecondaryTarget = targetEntity,
    m_Value = 0f
});
// If you wrote to this buffer from a Job, call:
// triggerSystem.AddActionBufferWriter(yourJobHandle);

// --------------------------------------------------------------------
// Example 2: Enqueue a chirp creation request (main-thread or job producer)
var createChirpSystem = World.DefaultGameObjectInjectionWorld
    .GetExistingSystemManaged<Game.Triggers.CreateChirpSystem>();

JobHandle writerDeps;
var chirpQueue = createChirpSystem.GetQueue(out writerDeps);

// Main-thread enqueue:
chirpQueue.Enqueue(new Game.Triggers.ChirpCreationData
{
    m_TriggerPrefab = chirpTriggerPrefab,
    m_Sender = senderEntity,
    m_Target = targetEntity // or Entity.Null
});

// If you enqueued from a Job, you must pass the JobHandle to the system so it can wait:
// createChirpSystem.AddQueueWriter(jobHandleThatWroteToQueue);
```

---

## Game.Tutorials

The Game.Tutorials module is the Cities: Skylines 2 ECS-driven tutorial framework. It provides lightweight tag components, small data components, buffer element types, enums/flags, service interfaces, and many systems that detect runtime/game events (input, tool/infoview state, area/prefab changes, object placement, zoning, upgrades, fires, health problems, policy adjustments, control-scheme changes, etc.) and use those events to activate, advance, or complete tutorial entities and phases. It integrates with PrefabSystem, ToolSystem, ZoneSystem and the central TutorialSystem to produce unlock events and persist shown/passed state.

Key points
- Components and buffers
  - Tag components used as presence/absence markers (TutorialActive, TutorialActivated, TriggerActive, TriggerCompleted, TriggerPreCompleted, ForceActivation, ForceTutorial, ForceAdvisor, EditorTutorial, TutorialShown, etc.). Most tags are empty structs sized to 1 byte.
  - Small data components that carry minimal payloads for specific activation rules (AutoActivationData, InfoviewActivationData, ControlSchemeActivationData, HealthProblemActivationData, ObjectPlacementTriggerCountData, PolicyAdjustmentTriggerData, UIActivationData, TutorialData, TutorialPhaseData, etc.).
  - Buffer element types for multi-entry sets (AreaTriggerData, ObjectPlacementTriggerData, ObjectSelectionTriggerData, TutorialAlternative, ObjectSelectionActivationData, ZoningTriggerData, TutorialRef/TutorialPhaseRef).
  - Flags/enums to combine conditions (AreaTriggerFlags, ObjectPlacementTriggerFlags, PolicyAdjustmentTriggerFlags, PolicyAdjustmentTriggerTargetFlags).
- Systems
  - TutorialSystem: central manager for tutorial lists/phase flow, persistence of shown/completed state, API surface (ForceTutorial, CompleteCurrentTutorialPhase, ManualUnlock, SetAllTutorialsShown).
  - TutorialActivation/Trigger manager and many specialized subsystems: TutorialTriggerSystem / TutorialActivationSystem orchestrate concrete trigger subsystems (Input, Area, ObjectPlacement, ObjectSelection, Zoning, Upgrade, Fire, HealthProblem, Infoview, ControlScheme, PolicyAdjustment, UITrigger/UIActivation/UIDeactivation).
  - TutorialEventActivationSystem: exposes a NativeQueue for safe job/main-thread producers to request activation at end-of-frame.
  - Deactivation systems (TutorialDeactivationSystemBase / TutorialDeactivationSystem and concrete deactivation subsystems) to remove activation when conditions change.
- Patterns and performance
  - Heavy use of presence/absence tag components to represent state transitions.
  - DynamicBuffer<T> holds 0..N trigger entries on a single trigger entity. Prefab references in buffers are resolved via PrefabSystem when required.
  - Systems use EntityQuery, IJobChunk (Burst), ComponentTypeHandle/ComponentLookup, ToArchetypeChunkListAsync, and barrier EntityCommandBufferSystems (ModificationBarrier3/4/5) to record structural changes safely from jobs (ParallelWriter support for ECB).
  - TutorialSystem and subsystems provide job-friendly APIs (ManualUnlock with ParallelWriter and BufferLookup overloads) to create unlock events from jobs without violating safety.
- Integration and modder tips
  - Create a tutorial controller entity (or use prefab mapping) and populate with the appropriate tag/data/buffer entries. Let the built-in systems handle activation/phase transitions and unlock events.
  - For job producers, use TutorialEventActivationSystem.GetQueue/AddQueueWriter to enqueue activations safely.
  - Prefer using public systems/APIs (TutorialSystem.ForceTutorial, TutorialUIActivationSystem.SetTag, TutorialUITriggerSystem.ActivateTrigger, TutorialUIDeactivationSystem.DeactivateTag) instead of manually adding/removing components when possible.
  - When adding buffer entries that reference prefabs, resolve prefab entity via PrefabSystem.GetEntity(...) to ensure correct entity references.
  - Use EntityCommandBuffer (barrier) from the appropriate ModificationBarrier to schedule structural changes from jobs and keep dependencies registered.

### Usage example
```csharp
using Unity.Entities;
using Unity.Collections;
using Game.Tutorials;
using Game.Input; // for InputManager.ControlScheme (example)

// Create a tutorial entity with a mix of tags, data and a DynamicBuffer
public static class TutorialsExample
{
    public static void CreateTutorial(EntityManager em, World world, Entity requiredUnlockEntity, Entity infoviewEntity, Entity areaPrefab)
    {
        var tutorialEntity = em.CreateEntity();

        // Mark it as a tutorial and active/activated
        em.AddComponent<TutorialActivationData>(tutorialEntity);
        em.AddComponent<TutorialActive>(tutorialEntity);

        // Auto-activate when requiredUnlockEntity is unlocked/created
        em.AddComponentData(tutorialEntity, new AutoActivationData { m_RequiredUnlock = requiredUnlockEntity });

        // Show a specific infoview/tool while the tutorial is running
        em.AddComponentData(tutorialEntity, new InfoviewActivationData(infoviewEntity));

        // Ask the UI to prefer Gamepad controls for this tutorial
        em.AddComponentData(tutorialEntity, new ControlSchemeActivationData(InputManager.ControlScheme.Gamepad));

        // Add one area trigger (prefab + flags)
        var areaBuffer = em.AddBuffer<AreaTriggerData>(tutorialEntity);
        areaBuffer.Add(new AreaTriggerData(areaPrefab, AreaTriggerFlags.Created));

        // Require 3 placements of some object (count tracked by the system)
        em.AddComponentData(tutorialEntity, new ObjectPlacementTriggerCountData { m_RequiredCount = 3, m_Count = 0 });

        // Optionally force advisor or force the tutorial to run immediately
        em.AddComponent<ForceAdvisor>(tutorialEntity);
        // em.AddComponent<ForceTutorial>(tutorialEntity);
    }

    // Example: enqueue a tutorial for activation using the TutorialEventActivationSystem (job-safe pattern).
    public static void QueueActivation(World world, Entity tutorialEntity)
    {
        var activationSys = world.GetExistingSystemManaged<TutorialEventActivationSystem>();
        if (activationSys != null)
        {
            // Get the shared queue and the current dependency handle (main-thread -> usually default)
            JobHandle dep;
            NativeQueue<Entity> queue = activationSys.GetQueue(out dep);

            // Enqueue the tutorial on the main thread
            queue.Enqueue(tutorialEntity);

            // Tell the activation system about our "writer" dependency (main-thread use dep)
            activationSys.AddQueueWriter(dep);
        }
        else
        {
            // fallback (not job-safe): directly add the activation tag
            world.EntityManager.AddComponent<TutorialActivated>(tutorialEntity);
        }
    }
}

// Example SystemBase that increments a placement counter and marks the trigger completed via an ECB
public partial class TutorialPlacementSystem : SystemBase
{
    protected override void OnUpdate()
    {
        var ecb = new EntityCommandBuffer(Allocator.Temp);
        // For demonstration — in real usage, you'd check an event or placement buffer/notification
        Entities
            .WithName("TutorialPlacementIncrement")
            .ForEach((Entity e, ref ObjectPlacementTriggerCountData placement) =>
            {
                placement.m_Count++; // pretend we observed a placement relevant to this trigger
                if (placement.m_Count >= placement.m_RequiredCount)
                {
                    // mark trigger completed (structural change)
                    ecb.AddComponent<TriggerCompleted>(e);
                }
            })
            .Run();

        ecb.Playback(EntityManager);
        ecb.Dispose();
    }
}

// Example usage of the high-level TutorialSystem to force a tutorial + phase (if you have the phase entity)
public static class TutorialManagerCalls
{
    public static void ForceTutorial(World world, Entity tutorialEntity, Entity phaseEntity)
    {
        var tutorialSystem = world.GetExistingSystemManaged<Game.Tutorials.TutorialSystem>();
        if (tutorialSystem != null)
        {
            // Force tutorial to start, optionally show advisor UI
            tutorialSystem.ForceTutorial(tutorialEntity, phaseEntity, advisorActivation: true);
        }
    }
}
```

This example shows common operations: creating a tutorial entity, adding tag/data components and a DynamicBuffer entry, enqueueing activation via the TutorialEventActivationSystem (safe for job producers), and using an ECS SystemBase to update trigger progress and mark completion via an EntityCommandBuffer. Use the module's buffer types, flags and tag components to model your triggers and prefer manager/system APIs for lifecycle actions.

---

## Game.UI (Cities: Skylines 2) — combined module summary

Summary
- What it is: the Game.UI module is the game's full UI backend and editor tooling surface. It supplies bindings, dialog models, widget factories, panels, picker/adapters, tooltip systems, thumbnail/screenshot helpers, input/rebinding UI, menu/upload flows (Paradox platform), and many in‑game info-section/infoview systems that serialize ECS/simulation state into JSON consumable by the frontend.
- Responsibilities:
  - Core bindings & helpers: app-level bindings (AppBindings), audio triggers (AudioBindings), dialog payloads (ConfirmationDialog, ErrorDialog), and localization helpers (LocalizedString, LocalizationBindings, UILocalizationManager).
  - Editor tooling: editor panels and tools (EditorPanelUISystem, EditorToolUISystem, InspectorPanelSystem, PrefabEditor/Picker systems), asset import/upload (AssetImportPanel, AssetUploadPanelUISystem, PdxAssetUploadHandle), map/save panels and map metadata (MapPanelSystem, MapMetadataSystem).
  - In‑game UI systems: dozens of UISystem/InfoSection classes exposing city data — BudgetUISystem, CityInfoUISystem, ClimateUISystem, PopulationInfoviewUISystem, ProductionUISystem, Transport/Traffic/TransportOverview systems, MilestoneUISystem, NotificationsPanel, AchievementsUISystem, and many more.
  - Selected-entity/inspector: SelectedInfoUISystem and many InfoSectionBase subclasses (ResidentsSection, FireSection, PollutionSection, VehicleSection, UpkeepSection, etc.) that compute values (often via Burst IJobChunk) and write JSON via IJsonWriter for the inspector.
  - Tooltip & visual helpers: multiple TooltipSystemBase implementations that produce mouse/world tooltips (resource, pollution, net build previews, temp previews), plus tooltip widgets (IntTooltip, FloatTooltip, NameTooltip).
  - Rendering & thumbnails: GameUIResourceHandler, ImageSystem, ThumbnailCache, ScreenCaptureHelper and HDRP ThumbnailCustomPass for screenshots and UI thumbnails.
  - Widgets & editor fields: widget primitives and field-builder factories (Game.UI.Widgets) for colors, vectors, enums, lists, paged lists, expandables, numeric sliders/inputs and automatic editor generation (EditorGenerator + FieldBuilder factories).
  - Widget binding & patching: WidgetBindings manages widget trees, default binding factories (InvokableBindings, ExpandableBindings, ListBindings, SettableBindings), and incremental JSON patching.
  - Input & rebinding UI: InputBindings, InputHintBindings and InputRebindingUISystem integrating Unity InputSystem for interactive rebinding, conflict detection and resolution.
  - Menu & platform integration: MenuUISystem (main menu / load / save / cloud), ParadoxBindings, NotificationUISystem, AssetUploadUtils and Modding toolchain integration (toolchain widgets, ModdingToolchainDependency).
  - Performance & safety patterns: heavy use of Unity.Entities ECS, ComponentLookup/BufferLookup, NativeArray/NativeList, Burst jobs for aggregation, EndFrameBarrier for safe structural changes, synchronous Complete() of job handles when UI needs same-frame results, and careful disposal of persistent native memory.

Key patterns and modder notes
- Bindings: UI state is exposed with ValueBinding<T>, GetterValueBinding<T>, RawValueBinding and TriggerBinding<T>. Use the provided group/key strings (e.g., "populationInfo", "prefabs", "toolbarBottom") to hook into or simulate UI actions.
- JSON serialization: complex payloads are written via IJsonWriter (used by RawValueBinding / InfoSection OnWriteProperties).
- ECS + Jobs: heavy use of IJobChunk / Burst for performance. Many systems schedule jobs and immediately Complete() so the JSON writer can read results — if you change to async you must handle job dependencies and lifetime.
- Native memory: persistent NativeArray/NativeList allocations must be disposed in OnDestroy to avoid leaks; many sections explicitly follow this pattern.
- Structural changes: when making entity/component changes from UI triggers, use EndFrameBarrier.CreateCommandBuffer() so changes are applied safely at frame end.
- Widgets: use EditorGenerator and field builder factories to generate editors automatically. If building custom widgets, provide IJsonWritable implementations for frontend serialization and register bindings via WidgetBindings.
- Thumbnails/screenshots: use GameUIResourceHandler and ScreenCaptureHelper. Async GPU readback returns NativeArray memory — always Dispose() after use.
- Uploads & platform: PdxAssetUploadHandle and AssetUploadPanelUISystem coordinate upload packaging and platform interaction; these APIs are asynchronous and may copy files or create atlases.

### Usage example
```csharp
using System;
using System.Threading.Tasks;
using UnityEngine;
using Unity.Entities;
using Game.UI;
using Game.UI.Editor;
using Game.UI.InGame;
using Game.UI.Menu;

// Minimal examples showing common interactions with the module:

async Task Example(World world)
{
    // 1) App-level bindings & audio
    var appBindings = new AppBindings();
    var audioBindings = new AudioBindings();
    appBindings.ready = true;
    appBindings.SetGameActive();

    // show a confirmation dialog
    var title = LocalizedString.Id("Dialog.Title.Quit");
    var message = LocalizedString.Id("Dialog.Message.QuitConfirm");
    appBindings.ShowConfirmationDialog(
        new ConfirmationDialog(title, message, LocalizedString.Id(DialogAction.kYes), LocalizedString.Id(DialogAction.kNo)),
        result =>
        {
            if (result == 1) // convention: 1 == confirm
                GameManager.QuitGame();
        });

    // play a UI sound (via binding trigger system — pseudocode)
    // BindingSystem.Trigger("audio", "playSound", "ButtonClick", 1.0f);

    // 2) Open a prefab picker popup and attach an accessor to receive selection
    var prefabAccessor = new SimplePrefabAccessor(); // implements ITypedValueAccessor<PrefabBase>
    var popup = new PrefabPickerPopup(typeof(PrefabBase), filter: p => p != null && p.package?.isInternal != true);
    popup.nullable = true;
    popup.Attach(prefabAccessor);
    // call popup.Update() each frame in your UI loop; when done:
    // popup.Detach();

    // 3) Request the inspector to select a prefab (wire picker -> inspector)
    var prefabSystem = world.GetOrCreateSystemManaged<PrefabSystem>();
    var inspector = world.GetOrCreateSystemManaged<InspectorPanelSystem>();
    PrefabBase somePrefab = prefabSystem.GetAllPrefabs().FirstOrDefault(); // pseudocode
    if (somePrefab != null) inspector.SelectPrefab(somePrefab);

    // 4) Use EndFrameBarrier to enqueue safe structural changes from UI
    var barrier = world.GetOrCreateSystemManaged<Game.EndFrameBarrier>();
    var ecb = barrier.CreateCommandBuffer();
    var ev = ecb.CreateEntity();
    ecb.SetComponent(ev, new Game.Common.Event()); // example small event entity enqueued for end-of-frame

    // 5) Use the GameUIResourceHandler + ImageSystem to get a thumbnail URI
    var imageSys = world.GetOrCreateSystemManaged<ImageSystem>();
    Entity prefabEntity = Entity.Null; // obtain actual prefab entity from PrefabSystem
    string thumb = imageSys.GetThumbnail(prefabEntity) ?? imageSys.placeholderIcon;
    Debug.Log("Thumbnail URI: " + thumb);

    // 6) Trigger Photo Mode and capture a screenshot (PhotoModeUISystem handles camera swapping)
    var photoSys = world.GetOrCreateSystemManaged<Game.UI.InGame.PhotoModeUISystem>();
    photoSys.Activate(true);
    photoSys.SetOverlayHidden(true);
    photoSys.TakeScreenshot(); // triggers screenshot coroutine internally

    // 7) Prepare an upload for a chosen asset (Menu / PDX upload flow)
    var uploadSys = world.GetOrCreateSystemManaged<Game.UI.Menu.AssetUploadPanelUISystem>();
    AssetData myAsset = AssetDatabase.global.GetAsset<AssetData>(/*guid*/ default);
    if (myAsset != null) uploadSys.Show(myAsset, allowManualFileCopy: true);

    // 8) Clean up bindings when done
    appBindings.Dispose();
    audioBindings.Dispose();
}

// Simple prefab accessor example used above
class SimplePrefabAccessor : ITypedValueAccessor<PrefabBase>
{
    private PrefabBase _value;
    public PrefabBase GetTypedValue() => _value;
    public void SetTypedValue(PrefabBase v) => _value = v;
}
```

Notes:
- Replace pseudocode comments with concrete game APIs (PrefabSystem methods, binding invocation) when used inside a real mod environment.
- When writing systems that schedule jobs, follow the module patterns: register Component/Buffer/Type handles in OnCreate, allocate persistent native accumulators with Allocator.Persistent, Complete() job handles before reading results, and Dispose() natives in OnDestroy. Use EndFrameBarrier for structural changes triggered from UI.

---

## Game.Vehicles

Summary
This module is the Cities: Skylines 2 vehicle ECS layer: a large collection of Unity DOTS IComponentData structs, IBufferElementData types, bitflag enums, helper structs and several job-driven systems that together represent and manage vehicle runtime state, navigation and parking/spawn logic. Types cover cars, trains, watercraft, aircraft, work vehicles and many specialized service vehicles (fire, police, garbage, ambulance, post, maintenance, etc.). Many components are tiny marker/tag types (1-byte serializable structs) while others contain lane/entity references, curve positions, timing/distance metrics and counters used by movement, parking and path logic.

Key points
- DOTS-style components: Nearly all runtime data are IComponentData or IBufferElementData, often implementing Colossal.Serialization.Entities.ISerializable (or IEmptySerializable) so the engine can save/load entity state.
- Marker/tag components: Many one-byte structs (e.g., Vehicle, Airplane, CarTrailer, EvacuatingTransport) are used to mark behavior or categories.
- Flags & enums: Per-vehicle and per-lane state use [Flags] bitmask enums (CarFlags, TrainFlags, WatercraftFlags, CarLaneFlags, TrainLaneFlags, etc.) for compact state and fast bitwise checks.
- Lane/navigation components: Current lane and navigation components store Entity lane references, float2/float3 curve positions, lane flags, progress/duration/distance metrics and sometimes packed/compatibility fields for versioned saves.
- Buffers: IBufferElementData types model passengers, layout elements, owned vehicles, loading resources, bogie frames, etc.; many use InternalBufferCapacity attributes for small on-entity buffers.
- VehicleUtils: Large static helper class with constants and many functions used by pathfinding, parking, speed/braking calculations, train/watercraft pivots, lane checks and spawn/parking calculations. Many methods are designed to run inside Jobs with ComponentLookup/BufferLookup semantics.
- Systems: Several jobified systems coordinate references and parking/spawning:
  - ReferencesSystem: updates lane/layout/controller references, register writers for moving-object search trees and ensures entity references are consistent.
  - InitializeSystem / ComponentsSystem: initialize spawned vehicles/trailers, patch transport marker components onto newly spawned entities.
  - FixParkingLocationSystem: collects parked/unspawned vehicles and reassigns/validates parking locations and updates lane buffers and search trees.
  - ParkedVehiclesSystem: finds building parking/spawn locations, reuses deleted vehicles, spawns parked service vehicles and duplicates parked vehicles for building duplication.
- Search trees & lane buffers: Systems interact heavily with Game.Objects.SearchSystem / Game.Net.SearchSystem — adding/removing lane objects, updating moving/static search trees and registering producers to avoid race conditions.
- Serialization & versioning: Serialize/Deserialize methods are explicit and version-aware. When extending serialized components, append fields at the end and gate reads with version checks to preserve save compatibility.
- Performance patterns: Systems use Burst-compiled IJob/IJobChunk, Native collections (NativeList, NativeParallelMultiHashMap), and a ModificationBarrier(n) to create EntityCommandBuffers from jobs. Hot paths rely on bitwise flag checks and read-modify-write whole structs for component updates.

Modding guidance
- Use EntityManager / System APIs to add, read and modify components. When modifying struct components, follow read-modify-write patterns (get component, change fields, set component).
- Use bitwise checks ((flags & SomeFlag) != 0) for performance-sensitive logic.
- Preserve serialization order and add version checks in Deserialize when adding fields to avoid breaking saved games.
- When making structural changes inside jobs, register a ModificationBarrier producer and use the provided EntityCommandBuffer to avoid race conditions.
- Prefer VehicleUtils constants and helpers for consistent physics/parking/speed logic rather than hard-coded numbers.
- If interacting with search trees, follow the existing pattern of registering search-tree producers/writers and updating lane object buffers to keep spatial indices correct.

### Usage example
```csharp
using Unity.Entities;
using Unity.Mathematics;
using Unity.Mathematics;
using Game.Vehicles;

public static class VehiclesExample
{
    public static void InitializeVehicle(EntityManager em, Entity vehicleEntity, Entity laneEntity, Entity controllerEntity)
    {
        // Tag entity as a vehicle
        if (!em.HasComponent<Vehicle>(vehicleEntity))
            em.AddComponentData(vehicleEntity, new Vehicle());

        // Add a Car component with initial flags
        em.AddComponentData(vehicleEntity, new Car(CarFlags.None));

        // Add navigation target for the car
        var nav = new CarNavigation {
            m_TargetPosition = new float3(1000f, 0f, 2000f),
            m_TargetRotation = quaternion.LookRotationSafe(new float3(0f, 0f, 1f), math.up()),
            m_MaxSpeed = 25f
        };
        em.AddComponentData(vehicleEntity, nav);

        // Add current lane info
        var currentLane = new CarCurrentLane {
            m_Lane = laneEntity,
            m_ChangeLane = Entity.Null,
            m_CurvePosition = new float3(0.5f, 0f, 0f),
            m_LaneFlags = CarLaneFlags.FixedLane,
            m_ChangeProgress = 0f,
            m_Duration = 0f,
            m_Distance = 0f,
            m_LanePosition = 0f
        };
        em.AddComponentData(vehicleEntity, currentLane);

        // Ensure navigation buffer exists and add a lane entry
        if (!em.HasComponent<CarNavigationLane>(vehicleEntity))
            em.AddBuffer<CarNavigationLane>(vehicleEntity);

        var buffer = em.GetBuffer<CarNavigationLane>(vehicleEntity);
        buffer.Add(new CarNavigationLane {
            m_Lane = laneEntity,
            m_CurvePosition = new float2(0.5f, 0f),
            m_Flags = CarLaneFlags.Checked
        });

        // Add controller reference
        em.AddComponentData(vehicleEntity, new Controller(controllerEntity));

        // Read-modify-write flags safely
        var carComp = em.GetComponentData<Car>(vehicleEntity);
        carComp.m_Flags |= CarFlags.UsePublicTransportLanes;
        em.SetComponentData(vehicleEntity, carComp);

        // Use a VehicleUtils helper (example: compute max drive speed given lane speed)
        // Note: real call sites often run inside Jobs using lookups; this is illustrative.
        // float maxDrive = VehicleUtils.GetMaxDriveSpeed(/*prefabCar*/, laneSpeed: 50f, curviness: 0.5f);

        // Mark the vehicle as having a trailer
        em.AddComponentData(vehicleEntity, new CarTrailer());
    }
}
```

---

## Game.Zones

Game.Zones is the Cities: Skylines 2 zoning pipeline module: a DOTS/Burst-optimized set of ECS data types, flags, systems and jobs that implement placement, maintenance, scanning and conflict-resolution for zoning "blocks" (rectangular cell grids placed along roads). Responsibilities include generating/reusing Block entities from roads, per-cell state/occupancy/height/zone handling, scanning nearby geometry (networks, objects, areas) to mark blocked/overridden/occupied cells, grouping and resolving overlapping blocks (sharing/priority/depth), detecting vacant lots, spatial indexing (NativeQuadTree) for fast queries and raycast-to-zone resolution, and version-aware serialization for save compatibility.

Key pieces

- Core data and small containers
  - Block: Block position (float3), 2D direction, integer cell size (int2). Equality uses exact floats; GetHashCode uses position only.
  - Cell: per-cell state element (CellFlags m_State, ZoneType m_Zone, short m_Height). Used as a DynamicBuffer element and serialized/versioned.
  - BuildOrder, CurvePosition, ValidArea, VacantLot, SubBlock, ProcessEstimate: small IComponentData/IBufferElementData used during processing.
  - ZoneType, AreaType, CellFlags, LotFlags: compact enums and wrappers; many types implement version-aware Serialize/Deserialize.
  - ZoneUtils: constants and helper math for cell/block coordinate conversions, bounds/corner tests, adjacency/share tests and tolerances.

- Systems (coordination & entity lifecycle)
  - BlockSystem: creates/updates Block entities from network edges/nodes with a parallel UpdateBlocksJob; uses ModificationBarrier4 for safe parallel entity changes.
  - BlockReferencesSystem: maintains owner SubBlock buffers when Blocks are created/deleted.
  - CellCheckSystem: orchestrates the multi-stage job pipeline that updates cells, finds and groups overlapping blocks, runs occupancy/lot-size updates and writes results; coordinates with ModificationBarrier5 and several search/update-collect systems.
  - SearchSystem: maintains a persistent NativeQuadTree<Entity, Bounds2> of zone Blocks; exposes APIs to register reader/writer JobHandles and to retrieve the quad-tree safely.
  - UpdateCollectSystem: collects bounds for Blocks created/updated/deleted and exposes a consolidated NativeList<Bounds2> for consumers.
  - LoadSystem: marks Blocks as Updated during NewGame/load to force initial processing.

- Jobs and helpers (Burst-parallel work)
  - CellBlockJobs.BlockCellsJob: computes blocked/roadside flags and sampled heights for each cell by iterating nearby net and area geometry using NativeQuadTree iterators.
  - CellOccupyJobs.ZoneAndOccupyCellsJob: scans placed objects/deleted-blocks to set Overridden/Occupied flags and per-cell heights.
  - CellOverlapJobs.CheckBlockOverlapJob: reduces/merges overlapping blocks, resolves depth/priority/share rules, writes final Cell flags and reduced ValidArea.
  - LotSizeJobs.UpdateLotSizeJob / UpdateBoundsJob: scans Cell buffers to find contiguous vacant rectangles (vacant lots), optionally expanding across block edges, and writes VacantLot buffers or removes them; drains bounds into a NativeList.
  - RaycastJobs.FindZoneBlockJob: converts terrain raycast hits into zone block + cell hits by scanning the NativeQuadTree and per-cell visibility flags.
  - CellCheckHelpers: utilities for spatial queries, deduplication, grouping and final per-block visibility updates.

Design and modding notes / caveats
- Built for Burst & DOTS: jobs use ComponentLookup/BufferLookup, Native containers, NativeQuadTree and EntityCommandBuffer. Respect the same access patterns and update/lookups (use Lookup.Update/AssignHandles or SystemAPI/SystemState patterns). Do not mutate components/buffers on the main thread while jobs that use them are running.
- Thread-safety: many systems require registering job read/write handles with SearchSystem/UpdateCollectSystem and to use the game's ModificationBarrier4/5 or provided ECB to create/delete/update entities from parallel jobs.
- Equality/hash: Block.Equals uses exact float equality and Block.GetHashCode only uses position — collisions are possible if direction/size differ. Normalize/quantize or provide a custom hash if you need tolerant comparisons or full-field uniqueness.
- Serialization: types like Cell, VacantLot, ValidArea and ZoneType implement version-aware serialization. Keep signatures and numeric layouts stable to preserve save compatibility.
- Lot detection heuristics and cell-state semantics: algorithms (width/depth heuristics, road-facing detection, share/priority) are sensitive to CellFlags/ZoneType semantics — change flags or thresholds only with full understanding of downstream jobs.
- Performance: jobs are carefully structured for parallelism (IJobParallelForDeferred, NativeArray temporaries). When scheduling, match the expected access patterns and register job handles where required (SearchSystem, UpdateCollectSystem).

### Usage example
A compact example that (A) creates a Block entity with a Cell buffer and (B) schedules the LotSize update job pattern (illustrative — adapt lookups and lifetimes to your System implementation and DOTS version):

```csharp
using Unity.Entities;
using Unity.Mathematics;
using Unity.Collections;
using Game.Zones;

public static class ZoneExample
{
    // Part A: create a Block entity and initialize Cells
    public static Entity CreateSimpleBlock(EntityManager em, Entity owner)
    {
        var block = new Block {
            m_Position = new float3(100f, 0f, 200f),
            m_Direction = new float2(1f, 0f),
            m_Size = new int2(8, 12)
        };

        Entity e = em.CreateEntity(typeof(Block), typeof(Owner), typeof(BuildOrder), typeof(Updated));
        em.SetComponentData(e, block);
        em.SetComponentData(e, new Owner { m_Owner = owner });
        em.SetComponentData(e, new BuildOrder { m_Order = 3u });

        var cells = em.AddBuffer<Cell>(e);
        int count = block.m_Size.x * block.m_Size.y;
        cells.ResizeUninitialized(count);
        for (int i = 0; i < count; i++)
        {
            cells[i] = new Cell {
                m_State = CellFlags.None,
                m_Zone = new ZoneType(),    // default
                m_Height = short.MaxValue   // no stored height
            };
        }

        // Example: mark first cell as roadside and visible
        var first = cells[0];
        first.m_State |= CellFlags.Roadside | CellFlags.Visible;
        cells[0] = first;

        return e;
    }

    // Part B: schedule LotSize update job (illustrative — resolve lookups from your System)
    public static JobHandle ScheduleLotSizeUpdate(
        LotSizeJobs.UpdateLotSizeJob updateJobTemplate,
        NativeArray<CellCheckHelpers.SortedEntity> blocksArray,
        JobHandle dependency,
        SearchSystem searchSystem,
        UpdateCollectSystem collectSystem)
    {
        // populate the template with your prepared lookups/buffers; this example assumes
        // you've created/obtained:
        // - ComponentLookup<Block> blockLookup (read-only)
        // - BufferLookup<Cell> cellBufferLookup (read-only)
        // - BufferLookup<VacantLot> vacantLotBufferLookup (read-write)
        // - NativeQuadTree<Entity, Bounds2> searchTree
        // - EntityCommandBuffer.ParallelWriter commandBuffer
        // - NativeQueue<Bounds2>.ParallelWriter boundsQueue

        var updateJob = updateJobTemplate;
        updateJob.m_Blocks = blocksArray; // deferred-length driver
        // ... (fill other fields: m_BlockData, m_Cells, m_VacantLots, m_SearchTree, m_CommandBuffer, m_BoundsQueue)

        // Schedule deferred parallel work (IJobParallelForDefer pattern)
        JobHandle h = updateJob.Schedule(updateJob.m_Blocks.Length, 64, dependency);

        // Register with SearchSystem if job writes/reads the quad-tree
        searchSystem?.AddSearchTreeWriter(h);

        // Then drain bounds queue into a NativeList (single-threaded follow-up job)
        var boundsJob = new LotSizeJobs.UpdateBoundsJob {
            m_BoundsQueue = /* boundsQueue */,
            m_BoundsList = /* boundsList (NativeList<Bounds2>) */
        };
        JobHandle h2 = boundsJob.Schedule(h);

        // Register collect system writer/reader if you will later read updated bounds
        collectSystem?.AddBoundsWriter(h2);

        return h2;
    }
}
```

If you want, I can produce focused, copy-pasteable examples for any of:
- Modifying BlockSystem placement logic (how to alter Block creation from networks),
- Safely preparing and scheduling a specific job (exact BufferLookup/ComponentLookup setup and Update/AssignHandles calls),
- Writing version-safe serialization for a custom component type compatible with Game.Zones. Tell me which and I’ll provide the exact code.

---

