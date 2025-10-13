# Game.Rendering.MeshColorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MeshColorSystem : Game.GameSystemBase
{
    private System.Boolean <smoothColorsUpdated>k__BackingField;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.RenderPrefabBase m_OverridePrefab;
    private System.Collections.Generic.Dictionary<System.String, System.Int32> m_GroupIDs;
    private Unity.Entities.EntityQuery m_UpdateQuery;
    private Unity.Entities.EntityQuery m_AllQuery;
    private Unity.Entities.EntityQuery m_PlantQuery;
    private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
    private Unity.Entities.Entity m_LastSeason1;
    private Unity.Entities.Entity m_LastSeason2;
    private Unity.Entities.Entity m_OverrideEntity;
    private System.UInt32 m_LastUpdateGroup;
    private System.UInt32 m_UpdateGroupCount;
    private System.Int32 m_OverrideIndex;
    private System.Single m_LastSeasonBlend;
    private System.Boolean m_Loaded;
    private Game.Rendering.MeshColorSystem+TypeHandle __TypeHandle;

    public System.Boolean smoothColorsUpdated { get; private set; }

    public MeshColorSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public Game.Rendering.ColorGroupID GetColorGroupID(System.String name);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private static System.Void RandomizeAlphas(Game.Rendering.ColorSet& colorSet, Unity.Mathematics.Random& random, Unity.Mathematics.float3 min, Unity.Mathematics.float3 max);
    private static System.Void RandomizeColor(UnityEngine.Color& color, Unity.Mathematics.Random& random, Unity.Mathematics.float3 min, Unity.Mathematics.float3 max);
    public System.Void SetOverride(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase prefab, System.Int32 variationIndex);
}
```


## Fields

- `private System.Boolean <smoothColorsUpdated>k__BackingField`  

```csharp
private System.Boolean <smoothColorsUpdated>k__BackingField;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.RenderPrefabBase m_OverridePrefab`  

```csharp
private Game.Prefabs.RenderPrefabBase m_OverridePrefab;
```

- `private System.Collections.Generic.Dictionary<System.String, System.Int32> m_GroupIDs`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Int32> m_GroupIDs;
```

- `private Unity.Entities.EntityQuery m_UpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdateQuery;
```

- `private Unity.Entities.EntityQuery m_AllQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllQuery;
```

- `private Unity.Entities.EntityQuery m_PlantQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlantQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
```

- `private Unity.Entities.Entity m_LastSeason1`  

```csharp
private Unity.Entities.Entity m_LastSeason1;
```

- `private Unity.Entities.Entity m_LastSeason2`  

```csharp
private Unity.Entities.Entity m_LastSeason2;
```

- `private Unity.Entities.Entity m_OverrideEntity`  

```csharp
private Unity.Entities.Entity m_OverrideEntity;
```

- `private System.UInt32 m_LastUpdateGroup`  

```csharp
private System.UInt32 m_LastUpdateGroup;
```

- `private System.UInt32 m_UpdateGroupCount`  

```csharp
private System.UInt32 m_UpdateGroupCount;
```

- `private System.Int32 m_OverrideIndex`  

```csharp
private System.Int32 m_OverrideIndex;
```

- `private System.Single m_LastSeasonBlend`  

```csharp
private System.Single m_LastSeasonBlend;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Rendering.MeshColorSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.MeshColorSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean smoothColorsUpdated { get; private set }`  

```csharp
public System.Boolean smoothColorsUpdated { get; private set; }
```


## Constructors

- `public MeshColorSystem()`  

```csharp
public MeshColorSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public GetColorGroupID(System.String name) : Game.Rendering.ColorGroupID`  

```csharp
public Game.Rendering.ColorGroupID GetColorGroupID(System.String name);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private static RandomizeAlphas(Game.Rendering.ColorSet& colorSet, Unity.Mathematics.Random& random, Unity.Mathematics.float3 min, Unity.Mathematics.float3 max) : System.Void`  

```csharp
private static System.Void RandomizeAlphas(Game.Rendering.ColorSet& colorSet, Unity.Mathematics.Random& random, Unity.Mathematics.float3 min, Unity.Mathematics.float3 max);
```

- `private static RandomizeColor(UnityEngine.Color& color, Unity.Mathematics.Random& random, Unity.Mathematics.float3 min, Unity.Mathematics.float3 max) : System.Void`  

```csharp
private static System.Void RandomizeColor(UnityEngine.Color& color, Unity.Mathematics.Random& random, Unity.Mathematics.float3 min, Unity.Mathematics.float3 max);
```

- `public SetOverride(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase prefab, System.Int32 variationIndex) : System.Void`  

```csharp
public System.Void SetOverride(Unity.Entities.Entity entity, Game.Prefabs.RenderPrefabBase prefab, System.Int32 variationIndex);
```


## Nested types

- `Game.Rendering.MeshColorSystem+FindUpdatedMeshColorsJob`  
- `Game.Rendering.MeshColorSystem+ListUpdatedMeshColorsJob`  
- `Game.Rendering.MeshColorSystem+CopyColorData`  
- `Game.Rendering.MeshColorSystem+UpdateStage`  
- `Game.Rendering.MeshColorSystem+SetMeshColorsJob`  
- `Game.Rendering.MeshColorSystem+CopyMeshColorsJob`  
- `Game.Rendering.MeshColorSystem+TypeHandle`  

