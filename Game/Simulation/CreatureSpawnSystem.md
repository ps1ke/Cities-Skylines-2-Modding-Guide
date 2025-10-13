# Game.Simulation.CreatureSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CreatureSpawnSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_CreatureQuery;
    private Unity.Entities.ComponentTypeSet m_TripSourceRemoveTypes;
    private Game.Simulation.CreatureSpawnSystem+TypeHandle __TypeHandle;

    public CreatureSpawnSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_CreatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatureQuery;
```

- `private Unity.Entities.ComponentTypeSet m_TripSourceRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_TripSourceRemoveTypes;
```

- `private Game.Simulation.CreatureSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CreatureSpawnSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CreatureSpawnSystem()`  

```csharp
public CreatureSpawnSystem();
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

- `Game.Simulation.CreatureSpawnSystem+SpawnData`  
- `Game.Simulation.CreatureSpawnSystem+SpawnRange`  
- `Game.Simulation.CreatureSpawnSystem+GroupSpawnSourcesJob`  
- `Game.Simulation.CreatureSpawnSystem+TrySpawnCreaturesJob`  
- `Game.Simulation.CreatureSpawnSystem+TypeHandle`  

