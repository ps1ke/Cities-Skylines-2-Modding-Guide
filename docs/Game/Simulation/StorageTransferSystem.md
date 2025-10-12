# Game.Simulation.StorageTransferSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_TransferGroup`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Unity.Collections.NativeQueue<Game.Simulation.StorageTransferSystem+StorageTransferEvent> m_TransferQueue`  
- `private Game.Simulation.StorageTransferSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Single kStorageProfit`  
- `public static readonly System.Single kMaxTransportUnitCost`  

## Constructors

- `public StorageTransferSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static CalculateTransferableAmount(System.Int32 original, System.Int32 sourceAmount, System.Int32 sourceCapacity, System.Int32 targetAmount, System.Int32 targetCapacity) : System.Int32`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.StorageTransferSystem+StorageTransferEvent`  
- `Game.Simulation.StorageTransferSystem+TransferJob`  
- `Game.Simulation.StorageTransferSystem+HandleTransfersJob`  
- `Game.Simulation.StorageTransferSystem+TypeHandle`  

