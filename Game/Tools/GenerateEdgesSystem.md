# Game.Tools.GenerateEdgesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GenerateEdgesSystem : Game.GameSystemBase
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Tools.GenerateObjectsSystem m_GenerateObjectsSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Common.ModificationBarrier2 m_TempEdgesBarrier;
    private Colossal.Collections.NativeValue<System.UInt32> m_BuildOrder;
    private Unity.Entities.EntityQuery m_CreatedEdgesQuery;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_DeletedQuery;
    private Game.Tools.GenerateEdgesSystem+TypeHandle __TypeHandle;

    public GenerateEdgesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public Colossal.Collections.NativeValue<System.UInt32> GetBuildOrder();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Tools.GenerateObjectsSystem m_GenerateObjectsSystem`  

```csharp
private Game.Tools.GenerateObjectsSystem m_GenerateObjectsSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Common.ModificationBarrier2 m_TempEdgesBarrier`  

```csharp
private Game.Common.ModificationBarrier2 m_TempEdgesBarrier;
```

- `private Colossal.Collections.NativeValue<System.UInt32> m_BuildOrder`  

```csharp
private Colossal.Collections.NativeValue<System.UInt32> m_BuildOrder;
```

- `private Unity.Entities.EntityQuery m_CreatedEdgesQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedEdgesQuery;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedQuery;
```

- `private Game.Tools.GenerateEdgesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.GenerateEdgesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GenerateEdgesSystem()`  

```csharp
public GenerateEdgesSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public GetBuildOrder() : Colossal.Collections.NativeValue<System.UInt32>`  

```csharp
public Colossal.Collections.NativeValue<System.UInt32> GetBuildOrder();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Tools.GenerateEdgesSystem+NodeMapKey`  
- `Game.Tools.GenerateEdgesSystem+LocalConnectItem`  
- `Game.Tools.GenerateEdgesSystem+OldEdgeKey`  
- `Game.Tools.GenerateEdgesSystem+CheckNodesJob`  
- `Game.Tools.GenerateEdgesSystem+FillOldEdgesJob`  
- `Game.Tools.GenerateEdgesSystem+CheckDefinitionsJob`  
- `Game.Tools.GenerateEdgesSystem+CollectLocalConnectItemsJob`  
- `Game.Tools.GenerateEdgesSystem+GenerateEdgesJob`  
- `Game.Tools.GenerateEdgesSystem+UpdateBuildOrderJob`  
- `Game.Tools.GenerateEdgesSystem+TypeHandle`  

