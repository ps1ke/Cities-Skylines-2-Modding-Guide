# Game.Tools.FindOwnersSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FindOwnersSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier3 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_OwnersQuery;
    private Unity.Entities.EntityQuery m_SubEntityQuery;
    private Game.Tools.FindOwnersSystem+TypeHandle __TypeHandle;

    public FindOwnersSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier3 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier3 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_OwnersQuery`  

```csharp
private Unity.Entities.EntityQuery m_OwnersQuery;
```

- `private Unity.Entities.EntityQuery m_SubEntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubEntityQuery;
```

- `private Game.Tools.FindOwnersSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.FindOwnersSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public FindOwnersSystem()`  

```csharp
public FindOwnersSystem();
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

- `Game.Tools.FindOwnersSystem+SetSubEntityOwnerJob`  
- `Game.Tools.FindOwnersSystem+TypeHandle`  

