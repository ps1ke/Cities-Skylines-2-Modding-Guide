# Game.Serialization.HouseholdSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

## Code

```csharp
public class HouseholdSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Unity.Entities.EntityQuery m_MovingInHouseholdQuery;

    public HouseholdSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_MovingInHouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_MovingInHouseholdQuery;
```


## Constructors

- `public HouseholdSystem()`  

```csharp
public HouseholdSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```


