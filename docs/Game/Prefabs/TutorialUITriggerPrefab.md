# Game.Prefabs.TutorialUITriggerPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TutorialTriggerPrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.TutorialUITriggerPrefab+UITriggerInfo[] m_UITriggers`  

## Properties

- `public System.Boolean phaseBranching { get }`  

## Constructors

- `public TutorialUITriggerPrefab()`  

## Methods

- `protected virtual GenerateBlinkTags() : System.Void`  
- `public virtual GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs) : System.Void`  
- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

## Nested types

- `Game.Prefabs.TutorialUITriggerPrefab+UITriggerInfo`  
- `Game.Prefabs.TutorialUITriggerPrefab+<>c`  

