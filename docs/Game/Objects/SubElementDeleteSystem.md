# Game.Objects.SubElementDeleteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SubElementDeleteSystem : Game.GameSystemBase
{
    private Game.Tools.ToolReadyBarrier m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DeletedQuery;
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Unity.Entities.ComponentTypeSet m_AppliedTypes;
    private Game.Objects.SubElementDeleteSystem+TypeHandle __TypeHandle;

    public SubElementDeleteSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolReadyBarrier m_ModificationBarrier`  

```csharp
private Game.Tools.ToolReadyBarrier m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DeletedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AppliedTypes;
```

- `private Game.Objects.SubElementDeleteSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.SubElementDeleteSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SubElementDeleteSystem()`  

```csharp
public SubElementDeleteSystem();
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

- `Game.Objects.SubElementDeleteSystem+DeleteSubElementsJob`  
- `Game.Objects.SubElementDeleteSystem+CheckDeletedOwnersJob`  
- `Game.Objects.SubElementDeleteSystem+TypeHandle`  

