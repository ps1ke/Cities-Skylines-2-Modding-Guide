# Game.Prefabs.ColorProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Collections.Generic.List<Game.Prefabs.ColorProperties+VariationSet> m_ColorVariations`  
- `public System.Collections.Generic.List<Game.Prefabs.ColorProperties+ColorChannelBinding> m_ChannelsBinding`  
- `public System.Collections.Generic.List<Game.Prefabs.ColorProperties+VariationGroup> m_VariationGroups`  
- `public Unity.Mathematics.int3 m_VariationRanges`  
- `public Unity.Mathematics.int3 m_AlphaRanges`  
- `public Game.Rendering.ColorSourceType m_ExternalColorSource`  

## Constructors

- `public ColorProperties()`  

## Methods

- `public CanBeModifiedByExternal(System.SByte channel) : System.Boolean`  
- `public GetAlpha(Unity.Mathematics.int3 alphas, System.SByte channel, System.Int32 def) : System.Int32`  
- `public GetAlpha(Unity.Mathematics.float3 alphas, System.SByte channel, System.Single def) : System.Single`  
- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public GetColor(System.Int32 index, System.SByte channel) : UnityEngine.Color`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public SanityCheck(System.SByte channel) : System.Boolean`  

## Nested types

- `Game.Prefabs.ColorProperties+VariationSet`  
- `Game.Prefabs.ColorProperties+ColorChannelBinding`  
- `Game.Prefabs.ColorProperties+VariationGroup`  

