# Game.Prefabs.CharacterStyle

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Fields

- `public System.Int32 m_ShapeCount`  
- `public System.Int32 m_BoneCount`  
- `public Game.Prefabs.GenderMask m_Gender`  
- `public Game.Prefabs.CharacterStyle+AnimationInfo[] m_Animations`  

## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

## Constructors

- `public CharacterStyle()`  

## Methods

- `public CalculateRootMotion(Colossal.Animations.BoneHierarchy hierarchy, Colossal.Animations.Animation animation, Colossal.Animations.Animation restPose, System.Int32 infoIndex) : System.Void`  
- `public GetAnimation(System.Int32 index) : Colossal.IO.AssetDatabase.AnimationAsset`  
- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

## Nested types

- `Game.Prefabs.CharacterStyle+AnimationMotion`  
- `Game.Prefabs.CharacterStyle+AnimationInfo`  

