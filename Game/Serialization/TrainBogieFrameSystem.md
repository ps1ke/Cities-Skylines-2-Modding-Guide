# Game.Serialization.TrainBogieFrameSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TrainBogieFrameSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.TrainBogieFrameSystem+TypeHandle __TypeHandle;

    public TrainBogieFrameSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Game.Serialization.TrainBogieFrameSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.TrainBogieFrameSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TrainBogieFrameSystem()`  

```csharp
public TrainBogieFrameSystem();
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

- `Game.Serialization.TrainBogieFrameSystem+BogieFrameJob`  
- `Game.Serialization.TrainBogieFrameSystem+TypeHandle`  

