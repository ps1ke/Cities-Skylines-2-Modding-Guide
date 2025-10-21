# Game.Serialization.LifepathEntrySystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LifepathEntrySystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ChirpQuery;
    private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
    private Game.Serialization.LifepathEntrySystem+TypeHandle __TypeHandle;

    public LifepathEntrySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChirpQuery;
```

- `private Game.Serialization.DeserializationBarrier m_DeserializationBarrier`  

```csharp
private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
```

- `private Game.Serialization.LifepathEntrySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.LifepathEntrySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LifepathEntrySystem()`  

```csharp
public LifepathEntrySystem();
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

- `Game.Serialization.LifepathEntrySystem+FixLifepathChirpReferencesJob`  
- `Game.Serialization.LifepathEntrySystem+TypeHandle`  

