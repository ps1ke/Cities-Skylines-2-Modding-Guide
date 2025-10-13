# Game.Tools.ValidationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ValidationSystem : Game.GameSystemBase
{
    private Game.Common.ModificationEndBarrier m_ModificationBarrier;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.ValidationSystem+Components m_Components;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_UpdatedAreaQuery;
    private Unity.Entities.EntityQuery m_ToolErrorPrefabQuery;
    private Game.Tools.ValidationSystem+ChunkType m_ChunkType;
    private Game.Tools.ValidationSystem+EntityData m_EntityData;
    private Game.Tools.ValidationSystem+TypeHandle __TypeHandle;

    public ValidationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationBarrier;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.ValidationSystem+Components m_Components`  

```csharp
private Game.Tools.ValidationSystem+Components m_Components;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem`  

```csharp
private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedAreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedAreaQuery;
```

- `private Unity.Entities.EntityQuery m_ToolErrorPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_ToolErrorPrefabQuery;
```

- `private Game.Tools.ValidationSystem+ChunkType m_ChunkType`  

```csharp
private Game.Tools.ValidationSystem+ChunkType m_ChunkType;
```

- `private Game.Tools.ValidationSystem+EntityData m_EntityData`  

```csharp
private Game.Tools.ValidationSystem+EntityData m_EntityData;
```

- `private Game.Tools.ValidationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ValidationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ValidationSystem()`  

```csharp
public ValidationSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `Game.Tools.ValidationSystem+ChunkType`  
- `Game.Tools.ValidationSystem+EntityData`  
- `Game.Tools.ValidationSystem+Components`  
- `Game.Tools.ValidationSystem+BoundsData`  
- `Game.Tools.ValidationSystem+BoundsComparerX`  
- `Game.Tools.ValidationSystem+BoundsComparerZ`  
- `Game.Tools.ValidationSystem+BoundsListJob`  
- `Game.Tools.ValidationSystem+ValidationJob`  
- `Game.Tools.ValidationSystem+CollectAreaTrianglesJob`  
- `Game.Tools.ValidationSystem+ValidateAreaTrianglesJob`  
- `Game.Tools.ValidationSystem+FillErrorPrefabsJob`  
- `Game.Tools.ValidationSystem+IconKey`  
- `Game.Tools.ValidationSystem+IconValue`  
- `Game.Tools.ValidationSystem+ProcessValidationResultsJob`  
- `Game.Tools.ValidationSystem+TypeHandle`  

