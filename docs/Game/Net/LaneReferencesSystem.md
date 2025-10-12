# Game.Net.LaneReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_LanesQuery`  
- `private Unity.Entities.EntityQuery m_UpdatedOwnersQuery`  
- `private Unity.Entities.EntityQuery m_AllOwnersQuery`  
- `private Unity.Collections.NativeQueue<Game.Net.Lane> m_SkipLaneQueue`  
- `private Unity.Jobs.JobHandle m_SkipLaneDeps`  
- `private System.Boolean m_Loaded`  
- `private Game.Net.LaneReferencesSystem+TypeHandle __TypeHandle`  

## Constructors

- `public LaneReferencesSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddSkipLaneWriter(Unity.Jobs.JobHandle dependency) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `public GetSkipLaneQueue() : Unity.Collections.NativeQueue<Game.Net.Lane>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Net.LaneReferencesSystem+UpdateLaneReferencesJob`  
- `Game.Net.LaneReferencesSystem+FillNodeMapJob`  
- `Game.Net.LaneReferencesSystem+FixSkippedLanesJob`  
- `Game.Net.LaneReferencesSystem+UpdateLaneIndicesJob`  
- `Game.Net.LaneReferencesSystem+SubLaneOrder`  
- `Game.Net.LaneReferencesSystem+TypeHandle`  

