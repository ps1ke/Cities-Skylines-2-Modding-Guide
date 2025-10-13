# Game.Simulation.StorageTransferSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StorageTransferSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_TransferGroup;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Collections.NativeQueue<Game.Simulation.StorageTransferSystem+StorageTransferEvent> m_TransferQueue;
    private Game.Simulation.StorageTransferSystem+TypeHandle __TypeHandle;
    public static readonly System.Single kStorageProfit;
    public static readonly System.Single kMaxTransportUnitCost;

    public StorageTransferSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Int32 CalculateTransferableAmount(System.Int32 original, System.Int32 sourceAmount, System.Int32 sourceCapacity, System.Int32 targetAmount, System.Int32 targetCapacity);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_TransferGroup`  

```csharp
private Unity.Entities.EntityQuery m_TransferGroup;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.StorageTransferSystem+StorageTransferEvent> m_TransferQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.StorageTransferSystem+StorageTransferEvent> m_TransferQueue;
```

- `private Game.Simulation.StorageTransferSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.StorageTransferSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Single kStorageProfit`  

```csharp
public static readonly System.Single kStorageProfit;
```

- `public static readonly System.Single kMaxTransportUnitCost`  

```csharp
public static readonly System.Single kMaxTransportUnitCost;
```


## Constructors

- `public StorageTransferSystem()`  

```csharp
public StorageTransferSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static CalculateTransferableAmount(System.Int32 original, System.Int32 sourceAmount, System.Int32 sourceCapacity, System.Int32 targetAmount, System.Int32 targetCapacity) : System.Int32`  

```csharp
public static System.Int32 CalculateTransferableAmount(System.Int32 original, System.Int32 sourceAmount, System.Int32 sourceCapacity, System.Int32 targetAmount, System.Int32 targetCapacity);
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.StorageTransferSystem+StorageTransferEvent`  
- `Game.Simulation.StorageTransferSystem+TransferJob`  
- `Game.Simulation.StorageTransferSystem+HandleTransfersJob`  
- `Game.Simulation.StorageTransferSystem+TypeHandle`  

