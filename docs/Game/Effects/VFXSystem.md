# Game.Effects.VFXSystem

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Collections.Generic.Queue<Unity.Collections.NativeQueue<Game.Effects.VFXUpdateInfo>> m_SourceUpdateQueue`  
- `private Unity.Jobs.JobHandle m_SourceUpdateWriter`  
- `private Unity.Entities.EntityQuery m_VFXPrefabQuery`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private System.Boolean m_Initialized`  
- `private Game.Effects.VFXSystem+EffectInfo[] m_Effects`  
- `private Unity.Jobs.JobHandle m_TextureUpdate`  
- `private Game.Rendering.WindTextureSystem m_WindTextureSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Effects.EffectControlSystem m_EffectControlSystem`  
- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

## Constructors

- `public VFXSystem()`  

## Methods

- `public AddSourceUpdateWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `private ClearQueue() : System.Void`  
- `public GetSourceUpdateData() : Unity.Collections.NativeQueue<Game.Effects.VFXUpdateInfo>`  
- `private Initialize() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Effects.VFXSystem+VFXIDs`  
- `Game.Effects.VFXSystem+EffectInfo`  
- `Game.Effects.VFXSystem+VFXTextureUpdateJob`  

