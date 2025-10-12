# Game.Prefabs.EmissiveProperties

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Collections.Generic.List<Game.Prefabs.EmissiveProperties+SingleLightMapping> m_SingleLights`  
- `public System.Collections.Generic.List<Game.Prefabs.EmissiveProperties+MultiLightMapping> m_MultiLights`  
- `public System.Collections.Generic.List<Game.Prefabs.EmissiveProperties+AnimationProperties> m_AnimationCurves`  
- `public System.Collections.Generic.List<Game.Prefabs.EmissiveProperties+SignalGroupAnimation> m_SignalGroupAnimations`  
- `public static const System.Single kIntensityMultiplier`  

## Properties

- `public System.Boolean hasSingleLights { get }`  
- `public System.Boolean hasMultiLights { get }`  
- `public System.Boolean hasAnyLights { get }`  
- `public System.Int32 lightsCount { get }`  

## Constructors

- `public EmissiveProperties()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public GetSingleLightOffset(System.Int32 materialId) : System.Int32`  
- `public IsSingleLightMaterialId(System.Int32 materialId) : System.Boolean`  

## Nested types

- `Game.Prefabs.EmissiveProperties+Purpose`  
- `Game.Prefabs.EmissiveProperties+MultiLightMapping`  
- `Game.Prefabs.EmissiveProperties+SingleLightMapping`  
- `Game.Prefabs.EmissiveProperties+LightProperties`  
- `Game.Prefabs.EmissiveProperties+AnimationProperties`  
- `Game.Prefabs.EmissiveProperties+SignalGroupAnimation`  

