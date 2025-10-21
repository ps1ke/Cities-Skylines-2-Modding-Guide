# Game.Serialization.HouseholdCitizenSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdCitizenSystem : Game.GameSystemBase
{
    private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.HouseholdCitizenSystem+TypeHandle __TypeHandle;

    public HouseholdCitizenSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.DeserializationBarrier m_DeserializationBarrier`  

```csharp
private Game.Serialization.DeserializationBarrier m_DeserializationBarrier;
```

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Game.Serialization.HouseholdCitizenSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.HouseholdCitizenSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HouseholdCitizenSystem()`  

```csharp
public HouseholdCitizenSystem();
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

- `Game.Serialization.HouseholdCitizenSystem+HouseholdCitizenJob`  
- `Game.Serialization.HouseholdCitizenSystem+TypeHandle`  

