# Game.Rendering.UtilityLodUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UtilityLodUpdateSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_TreeUpdateQuery;
    private Unity.Entities.EntityQuery m_CullingUpdateQuery;
    private Unity.Entities.EntityQuery m_BatchUpdateQuery;
    private System.Boolean m_Loaded;
    private Game.Rendering.UtilityLodUpdateSystem+TypeHandle __TypeHandle;

    public UtilityLodUpdateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem`  

```csharp
private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_TreeUpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_TreeUpdateQuery;
```

- `private Unity.Entities.EntityQuery m_CullingUpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_CullingUpdateQuery;
```

- `private Unity.Entities.EntityQuery m_BatchUpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_BatchUpdateQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Rendering.UtilityLodUpdateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.UtilityLodUpdateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public UtilityLodUpdateSystem()`  

```csharp
public UtilityLodUpdateSystem();
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

- `Game.Rendering.UtilityLodUpdateSystem+TypeHandle`  

