# Game.Tools.FindOwnersSystem2

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FindOwnersSystem2 : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier2B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_OwnersQuery;
    private Unity.Entities.EntityQuery m_SubEntityQuery;
    private Game.Tools.FindOwnersSystem2+TypeHandle __TypeHandle;

    public FindOwnersSystem2();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier2B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_OwnersQuery`  

```csharp
private Unity.Entities.EntityQuery m_OwnersQuery;
```

- `private Unity.Entities.EntityQuery m_SubEntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubEntityQuery;
```

- `private Game.Tools.FindOwnersSystem2+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.FindOwnersSystem2+TypeHandle __TypeHandle;
```


## Constructors

- `public FindOwnersSystem2()`  

```csharp
public FindOwnersSystem2();
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

- `Game.Tools.FindOwnersSystem2+TypeHandle`  

