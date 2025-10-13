# Game.Events.FaceWeatherSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FaceWeatherSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_FaceWeatherQuery;
    private Unity.Entities.EntityArchetype m_JournalDataArchetype;
    private Game.Events.FaceWeatherSystem+TypeHandle __TypeHandle;

    public FaceWeatherSystem();

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

- `private Unity.Entities.EntityQuery m_FaceWeatherQuery`  

```csharp
private Unity.Entities.EntityQuery m_FaceWeatherQuery;
```

- `private Unity.Entities.EntityArchetype m_JournalDataArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_JournalDataArchetype;
```

- `private Game.Events.FaceWeatherSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.FaceWeatherSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public FaceWeatherSystem()`  

```csharp
public FaceWeatherSystem();
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

- `Game.Events.FaceWeatherSystem+FaceWeatherJob`  
- `Game.Events.FaceWeatherSystem+TypeHandle`  

