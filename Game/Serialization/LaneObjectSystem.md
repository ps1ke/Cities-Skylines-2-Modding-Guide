# Game.Serialization.LaneObjectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneObjectSystem : Game.GameSystemBase
{
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.LaneObjectSystem+TypeHandle __TypeHandle;

    public LaneObjectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Game.Serialization.LaneObjectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.LaneObjectSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneObjectSystem()`  

```csharp
public LaneObjectSystem();
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

- `Game.Serialization.LaneObjectSystem+LaneObjectJob`  
- `Game.Serialization.LaneObjectSystem+TypeHandle`  

