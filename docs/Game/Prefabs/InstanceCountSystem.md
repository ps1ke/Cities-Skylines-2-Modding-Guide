# Game.Prefabs.InstanceCountSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_UpdatedInstancesQuery`  
- `private Unity.Entities.EntityQuery m_AllInstancesQuery`  
- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_InstanceCounts`  
- `private Unity.Jobs.JobHandle m_ReadDependencies`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private System.Boolean m_Loaded`  
- `private Game.Prefabs.InstanceCountSystem+TypeHandle __TypeHandle`  

## Constructors

- `public InstanceCountSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddCountReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddCountWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public GetInstanceCounts(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32>`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Prefabs.InstanceCountSystem+UpdateCountsJob`  
- `Game.Prefabs.InstanceCountSystem+TypeHandle`  

