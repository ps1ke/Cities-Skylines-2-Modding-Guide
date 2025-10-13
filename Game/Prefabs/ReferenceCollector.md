# Game.Prefabs.ReferenceCollector

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class ReferenceCollector
{
    private readonly System.Collections.Generic.Dictionary<System.Object, System.Boolean> m_VisitedObjects;
    private readonly System.Collections.Generic.Dictionary<System.Type, System.Reflection.FieldInfo[]> m_CachedFields;

    public ReferenceCollector();

    public Game.Prefabs.ReferenceCollector+CollectedReferences CollectDependencies(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.IAssetData> objs, System.Boolean addRoot);
    public Game.Prefabs.ReferenceCollector+CollectedReferences CollectDependencies(Colossal.IO.AssetDatabase.IAssetData obj);
    private System.Void TraverseObject(System.Object obj, Game.Prefabs.ReferenceCollector+CollectedReferences references);
    private System.Void TraverseSurfaceAsset(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset, Game.Prefabs.ReferenceCollector+CollectedReferences references);
    private System.Boolean TryAddVisited(System.Object obj);
}
```


## Fields

- `private readonly System.Collections.Generic.Dictionary<System.Object, System.Boolean> m_VisitedObjects`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.Object, System.Boolean> m_VisitedObjects;
```

- `private readonly System.Collections.Generic.Dictionary<System.Type, System.Reflection.FieldInfo[]> m_CachedFields`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.Type, System.Reflection.FieldInfo[]> m_CachedFields;
```


## Constructors

- `public ReferenceCollector()`  

```csharp
public ReferenceCollector()
	{
		m_VisitedObjects = new Dictionary<object, bool>();
		m_CachedFields = new Dictionary<Type, FieldInfo[]>(100);
	}
```


## Methods

- `public CollectDependencies(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.IAssetData> objs, System.Boolean addRoot) : Game.Prefabs.ReferenceCollector+CollectedReferences`  

```csharp
public CollectedReferences CollectDependencies(IAssetData obj)
	{
		m_VisitedObjects.Clear();
		CollectedReferences collectedReferences = new CollectedReferences();
		TraverseObject(obj, collectedReferences);
		return collectedReferences;
	}
```

- `public CollectDependencies(Colossal.IO.AssetDatabase.IAssetData obj) : Game.Prefabs.ReferenceCollector+CollectedReferences`  

```csharp
public CollectedReferences CollectDependencies(IAssetData obj)
	{
		m_VisitedObjects.Clear();
		CollectedReferences collectedReferences = new CollectedReferences();
		TraverseObject(obj, collectedReferences);
		return collectedReferences;
	}
```

- `private TraverseObject(System.Object obj, Game.Prefabs.ReferenceCollector+CollectedReferences references) : System.Void`  

```csharp
private void TraverseObject(object obj, CollectedReferences references)
	{
		if (obj == null || !TryAddVisited(obj))
		{
			return;
		}
		if (obj is PrefabBase prefabBase)
		{
			references.Add(prefabBase);
			references.Add(prefabBase.asset);
		}
		else if (obj is PrefabAsset prefabAsset)
		{
			TraverseObject(prefabAsset.Load<PrefabBase>(), references);
		}
		else if (obj is SurfaceAsset surfaceAsset)
		{
			TraverseSurfaceAsset(surfaceAsset, references);
		}
		else if (obj is AssetReference<SurfaceAsset> assetReference)
		{
			TraverseSurfaceAsset(assetReference, references);
		}
		if (obj is AssetReference assetReference2)
		{
			references.Add(AssetDatabase.global.GetAsset(assetReference2.guid));
		}
		Type type = obj.GetType();
		if (!m_CachedFields.TryGetValue(type, out var value))
		{
			List<FieldInfo> list = type.GetFields(BindingFlags.Instance | BindingFlags.Public).ToList();
			list.AddRange(from field in type.GetFields(BindingFlags.Instance | BindingFlags.NonPublic)
				where field.GetCustomAttribute<SerializeField>() != null
				select field);
			value = list.ToArray();
			m_CachedFields.Add(type, value);
		}
		FieldInfo[] array = value;
		for (int num = 0; num < array.Length; num++)
		{
			object value2 = array[num].GetValue(obj);
			if (value2 == null)
			{
				continue;
			}
			references.Add(value2);
			if (value2 is IDictionary dictionary)
			{
				foreach (DictionaryEntry item in dictionary)
				{
					references.Add(item.Key);
					references.Add(item.Value);
					TraverseObject(item.Key, references);
					TraverseObject(item.Value, references);
				}
			}
			else if (value2 is IEnumerable enumerable)
			{
				foreach (object item2 in enumerable)
				{
					references.Add(item2);
					TraverseObject(item2, references);
				}
			}
			else
			{
				TraverseObject(value2, references);
			}
		}
	}
```

- `private TraverseSurfaceAsset(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset, Game.Prefabs.ReferenceCollector+CollectedReferences references) : System.Void`  

```csharp
private void TraverseSurfaceAsset(SurfaceAsset surfaceAsset, CollectedReferences references)
	{
		if (surfaceAsset == null || !TryAddVisited(surfaceAsset))
		{
			return;
		}
		surfaceAsset.LoadProperties(useVT: false);
		foreach (KeyValuePair<string, TextureAsset> texture in surfaceAsset.textures)
		{
			references.Add(texture.Value);
		}
		if (!surfaceAsset.isVTMaterial)
		{
			return;
		}
		references.Add(surfaceAsset.vtSurfaceAsset);
		for (int i = 0; i < surfaceAsset.stackCount; i++)
		{
			for (int j = 0; j < 4; j++)
			{
				Colossal.Hash128 preProcessedTextureGuid = surfaceAsset.GetPreProcessedTextureGuid(i, j);
				references.Add(AssetDatabase.global.GetAsset(preProcessedTextureGuid));
			}
		}
	}
```

- `private TryAddVisited(System.Object obj) : System.Boolean`  

```csharp
private bool TryAddVisited(object obj)
	{
		return m_VisitedObjects.TryAdd(obj, value: true);
	}
```


## Nested types

- `Game.Prefabs.ReferenceCollector+CollectedReferences`  
- `Game.Prefabs.ReferenceCollector+<>c`  

