# Game.Prefabs.ZoneBuiltRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_UpdatedBuildingsQuery`  
- `private Unity.Entities.EntityQuery m_AllBuildingsQuery`  
- `private Unity.Entities.EntityQuery m_RequirementQuery`  
- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  
- `private Unity.Collections.NativeParallelHashMap<Game.Prefabs.ZoneBuiltDataKey, Game.Prefabs.ZoneBuiltDataValue> m_ZoneBuiltData`  
- `private Unity.Collections.NativeQueue<Game.Prefabs.ZoneBuiltLevelUpdate> m_ZoneBuiltLevelQueue`  
- `private Unity.Jobs.JobHandle m_WriteDeps`  
- `private Unity.Jobs.JobHandle m_QueueWriteDeps`  
- `private System.Boolean m_Loaded`  
- `private Game.Prefabs.ZoneBuiltRequirementSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ZoneBuiltRequirementSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `public GetZoneBuiltLevelQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Prefabs.ZoneBuiltLevelUpdate>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Prefabs.ZoneBuiltRequirementSystem+ZoneBuiltData`  
- `Game.Prefabs.ZoneBuiltRequirementSystem+UpdateZoneBuiltDataJob`  
- `Game.Prefabs.ZoneBuiltRequirementSystem+ZoneBuiltRequirementJob`  
- `Game.Prefabs.ZoneBuiltRequirementSystem+TypeHandle`  

