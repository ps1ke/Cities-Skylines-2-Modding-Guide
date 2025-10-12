# Game.Effects.SearchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Effects.EffectFlagSystem m_EffectFlagSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Effects.EffectControlData m_EffectControlData`  
- `private Colossal.Collections.NativeQuadTree<Game.Effects.SourceInfo, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  
- `private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Effects.SearchSystem+AddedSource> m_AddedSources`  
- `private Unity.Entities.EntityQuery m_UpdatedEffectsQuery`  
- `private Unity.Entities.EntityQuery m_AllEffectsQuery`  
- `private Unity.Jobs.JobHandle m_ReadDependencies`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private System.Boolean m_Loaded`  
- `private Game.Effects.SearchSystem+TypeHandle __TypeHandle`  

## Constructors

- `public SearchSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public static GetBounds(Unity.Collections.NativeArray<Game.Objects.Transform> transforms, Unity.Collections.NativeArray<Game.Net.Curve> curves, System.Int32 index, Game.Prefabs.Effect effect, Unity.Entities.ComponentLookup`1[[Game.Prefabs.LightEffectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabLightEffectData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.AudioEffectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabAudioEffectData) : Game.Common.QuadTreeBoundsXZ`  
- `private GetLoaded() : System.Boolean`  
- `public GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Game.Effects.SourceInfo, Game.Common.QuadTreeBoundsXZ>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Effects.SearchSystem+AddedSource`  
- `Game.Effects.SearchSystem+UpdateSearchTreeJob`  
- `Game.Effects.SearchSystem+TypeHandle`  

