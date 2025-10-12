# Game.Prefabs.Effects.SFX

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Effects`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Fields

- `public UnityEngine.AudioClip m_AudioClip`  
- `public System.Single m_Volume`  
- `public System.Single m_Pitch`  
- `public System.Single m_SpatialBlend`  
- `public System.Single m_Doppler`  
- `public System.Single m_Spread`  
- `public UnityEngine.AudioRolloffMode m_RolloffMode`  
- `public Unity.Mathematics.float2 m_MinMaxDistance`  
- `public System.Boolean m_Loop`  
- `public Game.Effects.MixerGroup m_MixerGroup`  
- `public System.Byte m_Priority`  
- `public UnityEngine.AnimationCurve m_RolloffCurve`  
- `public Unity.Mathematics.float3 m_SourceSize`  
- `public Unity.Mathematics.float2 m_FadeTimes`  
- `public System.Boolean m_RandomStartTime`  

## Constructors

- `public SFX()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

