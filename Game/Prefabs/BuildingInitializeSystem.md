# Game.Prefabs.BuildingInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuildingInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.BuildingInitializeSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_547773813_0;
    private static Colossal.Logging.ILog log;

    public BuildingInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void InitializeLotSize(Game.Prefabs.BuildingPrefab buildingPrefab, Game.Prefabs.BuildingTerraformOverride terraformOverride, Game.Prefabs.ObjectGeometryData& objectGeometryData, Game.Prefabs.BuildingTerraformData& buildingTerraformData, Game.Prefabs.BuildingData& buildingData);
    public static System.Void InitializeTerraformData(Game.Prefabs.BuildingTerraformOverride terraformOverride, Game.Prefabs.BuildingTerraformData& buildingTerraformData, Colossal.Mathematics.Bounds2 lotBounds, Colossal.Mathematics.Bounds2 flatBounds);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.BuildingInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.BuildingInitializeSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_547773813_0`  

```csharp
private Unity.Entities.EntityQuery __query_547773813_0;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```


## Constructors

- `public BuildingInitializeSystem()`  

```csharp
public BuildingInitializeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private InitializeLotSize(Game.Prefabs.BuildingPrefab buildingPrefab, Game.Prefabs.BuildingTerraformOverride terraformOverride, Game.Prefabs.ObjectGeometryData& objectGeometryData, Game.Prefabs.BuildingTerraformData& buildingTerraformData, Game.Prefabs.BuildingData& buildingData) : System.Void`  

```csharp
private System.Void InitializeLotSize(Game.Prefabs.BuildingPrefab buildingPrefab, Game.Prefabs.BuildingTerraformOverride terraformOverride, Game.Prefabs.ObjectGeometryData& objectGeometryData, Game.Prefabs.BuildingTerraformData& buildingTerraformData, Game.Prefabs.BuildingData& buildingData);
```

- `public static InitializeTerraformData(Game.Prefabs.BuildingTerraformOverride terraformOverride, Game.Prefabs.BuildingTerraformData& buildingTerraformData, Colossal.Mathematics.Bounds2 lotBounds, Colossal.Mathematics.Bounds2 flatBounds) : System.Void`  

```csharp
public static System.Void InitializeTerraformData(Game.Prefabs.BuildingTerraformOverride terraformOverride, Game.Prefabs.BuildingTerraformData& buildingTerraformData, Colossal.Mathematics.Bounds2 lotBounds, Colossal.Mathematics.Bounds2 flatBounds);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Prefabs.BuildingInitializeSystem+FindConnectionRequirementsJob`  
- `Game.Prefabs.BuildingInitializeSystem+TypeHandle`  

