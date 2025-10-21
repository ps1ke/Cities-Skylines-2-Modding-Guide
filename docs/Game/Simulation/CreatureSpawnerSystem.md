# Game.Simulation.CreatureSpawnerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CreatureSpawnerSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_SpawnerQuery;
    private Unity.Entities.ComponentTypeSet m_AnimalSpawnTypes;
    private Game.Simulation.CreatureSpawnerSystem+TypeHandle __TypeHandle;

    public CreatureSpawnerSystem();

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

- `private Unity.Entities.EntityQuery m_SpawnerQuery`  

```csharp
private Unity.Entities.EntityQuery m_SpawnerQuery;
```

- `private Unity.Entities.ComponentTypeSet m_AnimalSpawnTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AnimalSpawnTypes;
```

- `private Game.Simulation.CreatureSpawnerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CreatureSpawnerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CreatureSpawnerSystem()`  

```csharp
public CreatureSpawnerSystem();
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

- `Game.Simulation.CreatureSpawnerSystem+CreatureSpawnerJob`  
- `Game.Simulation.CreatureSpawnerSystem+TypeHandle`  

