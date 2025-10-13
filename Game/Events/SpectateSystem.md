# Game.Events.SpectateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SpectateSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_SpectateQuery;
    private Game.Events.SpectateSystem+TypeHandle __TypeHandle;

    public SpectateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_SpectateQuery`  

```csharp
private Unity.Entities.EntityQuery m_SpectateQuery;
```

- `private Game.Events.SpectateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.SpectateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SpectateSystem()`  

```csharp
public SpectateSystem();
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

- `Game.Events.SpectateSystem+SpectateJob`  
- `Game.Events.SpectateSystem+TypeHandle`  

