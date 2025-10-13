# Game.Simulation.HouseholdPetSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdPetSpawnSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_HouseholdPetQuery;
    private Unity.Entities.EntityQuery m_AnimalPrefabQuery;
    private Unity.Entities.EntityArchetype m_ResetTripArchetype;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.HouseholdPetSpawnSystem+TypeHandle __TypeHandle;

    public HouseholdPetSpawnSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `private Unity.Entities.EntityQuery m_AnimalPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_AnimalPrefabQuery;
```

- `private Unity.Entities.EntityArchetype m_ResetTripArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ResetTripArchetype;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.HouseholdPetSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.HouseholdPetSpawnSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HouseholdPetSpawnSystem()`  

```csharp
public HouseholdPetSpawnSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `Game.Simulation.HouseholdPetSpawnSystem+HouseholdPetSpawnJob`  
- `Game.Simulation.HouseholdPetSpawnSystem+TypeHandle`  

