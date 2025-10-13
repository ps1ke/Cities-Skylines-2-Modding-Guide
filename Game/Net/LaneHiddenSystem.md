# Game.Net.LaneHiddenSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneHiddenSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_HiddenQuery;
    private Game.Net.LaneHiddenSystem+TypeHandle __TypeHandle;

    public LaneHiddenSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_HiddenQuery`  

```csharp
private Unity.Entities.EntityQuery m_HiddenQuery;
```

- `private Game.Net.LaneHiddenSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.LaneHiddenSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneHiddenSystem()`  

```csharp
public LaneHiddenSystem();
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

- `Game.Net.LaneHiddenSystem+HiddenSubObjectJob`  
- `Game.Net.LaneHiddenSystem+TypeHandle`  

