# Game.Prefabs.AssetCollection

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `UnityEngine.ScriptableObject`  

**Attributes:** `CreateAssetMenu`  

## Code

```csharp
public class AssetCollection : UnityEngine.ScriptableObject
{
    public System.Boolean isActive;
    public System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_Prefabs;
    public System.Collections.Generic.List<Game.Prefabs.AssetCollection> m_Collections;

    public System.Int32 Count { get; }

    public AssetCollection();

    public System.Void AddPrefabsTo(Game.Prefabs.PrefabSystem prefabSystem);
    public System.Void SortAssets();
}
```


## Fields

- `public System.Boolean isActive`  

```csharp
public System.Boolean isActive;
```

- `public System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_Prefabs`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.PrefabBase> m_Prefabs;
```

- `public System.Collections.Generic.List<Game.Prefabs.AssetCollection> m_Collections`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.AssetCollection> m_Collections;
```


## Properties

- `public System.Int32 Count { get }`  

```csharp
public System.Int32 Count { get; }
```


## Constructors

- `public AssetCollection()`  

```csharp
public AssetCollection();
```


## Methods

- `public AddPrefabsTo(Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public void AddPrefabsTo(PrefabSystem prefabSystem)
	{
		if (!isActive)
		{
			return;
		}
		foreach (PrefabBase prefab in m_Prefabs)
		{
			prefabSystem.AddPrefab(prefab, base.name);
		}
		foreach (AssetCollection collection in m_Collections)
		{
			collection.AddPrefabsTo(prefabSystem);
		}
	}
```

- `public SortAssets() : System.Void`  

```csharp
public void SortAssets()
	{
		m_Prefabs.Sort((PrefabBase a, PrefabBase b) => string.Compare(a.name, b.name, StringComparison.Ordinal));
	}
```


## Nested types

- `Game.Prefabs.AssetCollection+<>c`  

