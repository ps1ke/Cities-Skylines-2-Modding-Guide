# Game.Prefabs.UIMultiTagPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class UIMultiTagPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.String m_Override;
    public Game.Prefabs.PrefabBase[] m_UITagProviders;

    public System.String uiTag { get; }

    public UIMultiTagPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> prefabComponents);
}
```


## Fields

- `public System.String m_Override`  

```csharp
public System.String m_Override;
```

- `public Game.Prefabs.PrefabBase[] m_UITagProviders`  

```csharp
public Game.Prefabs.PrefabBase[] m_UITagProviders;
```


## Properties

- `public System.String uiTag { get }`  

```csharp
public System.String uiTag { get; }
```


## Constructors

- `public UIMultiTagPrefab()`  

```csharp
public UIMultiTagPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_UITagProviders != null)
		{
			for (int i = 0; i < m_UITagProviders.Length; i++)
			{
				prefabs.Add(m_UITagProviders[i]);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> prefabComponents) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> prefabComponents)
	{
		base.GetPrefabComponents(prefabComponents);
		prefabComponents.Add(ComponentType.ReadWrite<UITagPrefabData>());
	}
```


## Nested types

- `Game.Prefabs.UIMultiTagPrefab+<>c`  

