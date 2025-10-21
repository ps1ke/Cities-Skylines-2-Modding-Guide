# Game.Prefabs.TutorialTriggerPrefabBase

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public abstract class TutorialTriggerPrefabBase : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    private System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<System.String>> m_BlinkDict;
    public System.Boolean m_DisplayUI;

    public System.Boolean phaseBranching { get; }
    public System.Boolean ignoreUnlockDependencies { get; }

    protected TutorialTriggerPrefabBase();

    protected System.Void AddBlinkTag(System.String tag);
    protected System.Void AddBlinkTagAtPosition(System.String tag, System.Int32 position);
    protected virtual System.Void GenerateBlinkTags();
    public virtual System.Void GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs);
    public System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<System.String>> GetBlinkTags();
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `private System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<System.String>> m_BlinkDict`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<System.String>> m_BlinkDict;
```

- `public System.Boolean m_DisplayUI`  

```csharp
public System.Boolean m_DisplayUI;
```


## Properties

- `public System.Boolean phaseBranching { get }`  

```csharp
public System.Boolean phaseBranching { get; }
```

- `public System.Boolean ignoreUnlockDependencies { get }`  

```csharp
public System.Boolean ignoreUnlockDependencies { get; }
```


## Constructors

- `protected TutorialTriggerPrefabBase()`  

```csharp
protected TutorialTriggerPrefabBase();
```


## Methods

- `protected AddBlinkTag(System.String tag) : System.Void`  

```csharp
protected System.Void AddBlinkTag(System.String tag);
```

- `protected AddBlinkTagAtPosition(System.String tag, System.Int32 position) : System.Void`  

```csharp
protected System.Void AddBlinkTagAtPosition(System.String tag, System.Int32 position);
```

- `protected virtual GenerateBlinkTags() : System.Void`  

```csharp
protected virtual System.Void GenerateBlinkTags();
```

- `public virtual GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs) : System.Void`  

```csharp
public virtual System.Void GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs);
```

- `public GetBlinkTags() : System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<System.String>>`  

```csharp
public System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<System.String>> GetBlinkTags();
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


