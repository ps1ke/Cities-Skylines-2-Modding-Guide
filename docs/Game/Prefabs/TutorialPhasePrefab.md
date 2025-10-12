# Game.Prefabs.TutorialPhasePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Fields

- `public System.String m_Image`  
- `public System.String m_OverrideImagePS`  
- `public System.String m_OverrideImageXBox`  
- `public System.String m_Icon`  
- `public System.Boolean m_TitleVisible`  
- `public System.Boolean m_DescriptionVisible`  
- `public System.Boolean m_CanDeactivate`  
- `public Game.Prefabs.TutorialPhasePrefab+ControlScheme m_ControlScheme`  
- `public Game.Prefabs.TutorialTriggerPrefabBase m_Trigger`  
- `public System.Single m_OverrideCompletionDelay`  

## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

## Constructors

- `protected TutorialPhasePrefab()`  

## Methods

- `public virtual GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs) : System.Void`  
- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

## Nested types

- `Game.Prefabs.TutorialPhasePrefab+ControlScheme`  

