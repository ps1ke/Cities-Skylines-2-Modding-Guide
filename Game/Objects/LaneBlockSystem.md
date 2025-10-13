# Game.Objects.LaneBlockSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneBlockSystem : Game.GameSystemBase
{
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Unity.Entities.EntityQuery m_ObjectQuery;
    private Game.Net.LaneObjectUpdater m_LaneObjectUpdater;
    private Game.Objects.LaneBlockSystem+TypeHandle __TypeHandle;

    public LaneBlockSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Unity.Entities.EntityQuery m_ObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectQuery;
```

- `private Game.Net.LaneObjectUpdater m_LaneObjectUpdater`  

```csharp
private Game.Net.LaneObjectUpdater m_LaneObjectUpdater;
```

- `private Game.Objects.LaneBlockSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.LaneBlockSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneBlockSystem()`  

```csharp
public LaneBlockSystem();
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

- `Game.Objects.LaneBlockSystem+FindBlockedLanesJob`  
- `Game.Objects.LaneBlockSystem+TypeHandle`  

