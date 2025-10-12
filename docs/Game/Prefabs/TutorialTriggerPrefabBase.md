# Game.Prefabs.TutorialTriggerPrefabBase

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Fields

- `private System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<System.String>> m_BlinkDict`  
- `public System.Boolean m_DisplayUI`  

## Properties

- `public System.Boolean phaseBranching { get }`  
- `public System.Boolean ignoreUnlockDependencies { get }`  

## Constructors

- `protected TutorialTriggerPrefabBase()`  

## Methods

- `protected AddBlinkTag(System.String tag) : System.Void`  
- `protected AddBlinkTagAtPosition(System.String tag, System.Int32 position) : System.Void`  
- `protected virtual GenerateBlinkTags() : System.Void`  
- `public virtual GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs) : System.Void`  
- `public GetBlinkTags() : System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<System.String>>`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

