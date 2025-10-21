# Game.Serialization.GarbageProducerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GarbageProducerSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.GarbageProducerSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_31347557_0;

    public GarbageProducerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Game.Serialization.GarbageProducerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.GarbageProducerSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_31347557_0`  

```csharp
private Unity.Entities.EntityQuery __query_31347557_0;
```


## Constructors

- `public GarbageProducerSystem()`  

```csharp
public GarbageProducerSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Serialization.GarbageProducerSystem+TypeHandle`  

