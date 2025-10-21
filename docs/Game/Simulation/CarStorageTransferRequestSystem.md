# Game.Simulation.CarStorageTransferRequestSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CarStorageTransferRequestSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_TransferGroup;
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.CarStorageTransferRequestSystem+TypeHandle __TypeHandle;

    public CarStorageTransferRequestSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_TransferGroup`  

```csharp
private Unity.Entities.EntityQuery m_TransferGroup;
```

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.CarStorageTransferRequestSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CarStorageTransferRequestSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CarStorageTransferRequestSystem()`  

```csharp
public CarStorageTransferRequestSystem();
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

- `Game.Simulation.CarStorageTransferRequestSystem+TransferJob`  
- `Game.Simulation.CarStorageTransferRequestSystem+TypeHandle`  

