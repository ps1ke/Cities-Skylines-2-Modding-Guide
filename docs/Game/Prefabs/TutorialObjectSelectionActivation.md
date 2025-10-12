# Game.Prefabs.TutorialObjectSelectionActivation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TutorialActivation`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.PrefabBase[] m_Prefabs`  
- `public System.Boolean m_AllowTool`  

## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

## Constructors

- `public TutorialObjectSelectionActivation()`  

## Methods

- `public virtual GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs) : System.Void`  
- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

