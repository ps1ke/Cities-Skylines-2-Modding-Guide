# Game.Tools.GenerateNodesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GenerateNodesSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Net.SearchSystem m_SearchSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Tools.GenerateObjectsSystem m_GenerateObjectsSystem;
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_DeletedQuery;
    private Game.Tools.GenerateNodesSystem+TypeHandle __TypeHandle;

    public GenerateNodesSystem();

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

- `private Game.Net.SearchSystem m_SearchSystem`  

```csharp
private Game.Net.SearchSystem m_SearchSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Tools.GenerateObjectsSystem m_GenerateObjectsSystem`  

```csharp
private Game.Tools.GenerateObjectsSystem m_GenerateObjectsSystem;
```

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier1 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedQuery;
```

- `private Game.Tools.GenerateNodesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.GenerateNodesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GenerateNodesSystem()`  

```csharp
public GenerateNodesSystem();
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

- `Game.Tools.GenerateNodesSystem+UpdateData`  
- `Game.Tools.GenerateNodesSystem+NodeKey`  
- `Game.Tools.GenerateNodesSystem+DefinitionData`  
- `Game.Tools.GenerateNodesSystem+OldNodeKey`  
- `Game.Tools.GenerateNodesSystem+OldNodeValue`  
- `Game.Tools.GenerateNodesSystem+FillOldNodesJob`  
- `Game.Tools.GenerateNodesSystem+FillNodeMapJob`  
- `Game.Tools.GenerateNodesSystem+CollectUpdatesJob`  
- `Game.Tools.GenerateNodesSystem+CreateNodesJob`  
- `Game.Tools.GenerateNodesSystem+TypeHandle`  

