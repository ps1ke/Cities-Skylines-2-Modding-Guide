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
protected void AddBlinkTag(string tag)
	{
		AddBlinkTagAtPosition(tag, 0);
	}
```

- `protected AddBlinkTagAtPosition(System.String tag, System.Int32 position) : System.Void`  

```csharp
protected void AddBlinkTagAtPosition(string tag, int position)
	{
		if (!m_BlinkDict.ContainsKey(position))
		{
			m_BlinkDict[position] = new List<string>();
		}
		if (!m_BlinkDict[position].Contains(tag))
		{
			m_BlinkDict[position].Add(tag);
		}
	}
```

- `protected virtual GenerateBlinkTags() : System.Void`  

```csharp
protected virtual void GenerateBlinkTags()
	{
		if (m_BlinkDict == null)
		{
			m_BlinkDict = new Dictionary<int, List<string>>();
		}
		else
		{
			m_BlinkDict.Clear();
		}
	}
```

- `public virtual GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs) : System.Void`  

```csharp
public virtual void GenerateTutorialLinks(EntityManager entityManager, NativeParallelHashSet<Entity> linkedPrefabs)
	{
	}
```

- `public GetBlinkTags() : System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<System.String>>`  

```csharp
public Dictionary<int, List<string>> GetBlinkTags()
	{
		return m_BlinkDict;
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<TutorialTriggerData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		GenerateBlinkTags();
	}
```


