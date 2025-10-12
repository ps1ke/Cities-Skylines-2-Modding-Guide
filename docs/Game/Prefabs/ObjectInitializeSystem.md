# Game.Prefabs.ObjectInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Unity.Entities.EntityQuery m_PlaceholderQuery`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Prefabs.ObjectInitializeSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ObjectInitializeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private static GetMeshGroupFlag(Game.Objects.ObjectState state, System.Boolean inverse) : Game.Prefabs.MeshGroupFlags`  
- `private GetRandomSeed(System.String name) : System.UInt16`  
- `private InitializePrefab(Game.Prefabs.AssetStampPrefab stampPrefab, Game.Prefabs.AssetStampData& assetStampData, Game.Prefabs.PlaceableObjectData& placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData) : System.Void`  
- `private InitializePrefab(Game.Prefabs.ObjectGeometryPrefab objectPrefab, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData, Game.Prefabs.GrowthScaleData& growthScaleData, Game.Prefabs.StackData& stackData, Game.Prefabs.QuantityObjectData& quantityObjectData, Game.Prefabs.CreatureData& creatureData, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMesh> meshes, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMeshGroup> meshGroups, Unity.Entities.DynamicBuffer<Game.Prefabs.CharacterElement> characterElements, System.Boolean isPlantObject, System.Boolean isHumanObject, System.Boolean isBuildingObject, System.Boolean isVehicleObject, System.Boolean isCreatureObject) : System.Void`  
- `private InitializePrefab(Game.Prefabs.MarkerObjectPrefab objectPrefab, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMesh> meshes) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private UpdateStackBounds(Colossal.Mathematics.Bounds1& stackBounds, Colossal.Mathematics.Bounds3& meshBounds, Game.Prefabs.StackProperties properties) : System.Void`  

## Nested types

- `Game.Prefabs.ObjectInitializeSystem+FixPlaceholdersJob`  
- `Game.Prefabs.ObjectInitializeSystem+InitializeSubNetsJob`  
- `Game.Prefabs.ObjectInitializeSystem+FindPlaceholderRequirementsJob`  
- `Game.Prefabs.ObjectInitializeSystem+FindSubObjectRequirementsJob`  
- `Game.Prefabs.ObjectInitializeSystem+TypeHandle`  

