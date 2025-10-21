# Game.Citizens.HouseholdPetInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdPetInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_HouseholdPetQuery;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Citizens.HouseholdPetInitializeSystem+TypeHandle __TypeHandle;

    public HouseholdPetInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_HouseholdPetQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdPetQuery;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Citizens.HouseholdPetInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Citizens.HouseholdPetInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HouseholdPetInitializeSystem()`  

```csharp
public HouseholdPetInitializeSystem();
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

- `Game.Citizens.HouseholdPetInitializeSystem+InitializeHouseholdPetJob`  
- `Game.Citizens.HouseholdPetInitializeSystem+TypeHandle`  

