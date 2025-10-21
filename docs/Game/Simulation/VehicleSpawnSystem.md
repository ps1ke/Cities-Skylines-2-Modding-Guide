# Game.Simulation.VehicleSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class VehicleSpawnSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Game.Simulation.VehicleSpawnSystem+TypeHandle __TypeHandle;

    public VehicleSpawnSystem();

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

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Game.Simulation.VehicleSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.VehicleSpawnSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public VehicleSpawnSystem()`  

```csharp
public VehicleSpawnSystem();
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

- `Game.Simulation.VehicleSpawnSystem+SpawnData`  
- `Game.Simulation.VehicleSpawnSystem+SpawnRange`  
- `Game.Simulation.VehicleSpawnSystem+GroupSpawnSourcesJob`  
- `Game.Simulation.VehicleSpawnSystem+LaneBufferItem`  
- `Game.Simulation.VehicleSpawnSystem+TrySpawnVehiclesJob`  
- `Game.Simulation.VehicleSpawnSystem+TypeHandle`  

