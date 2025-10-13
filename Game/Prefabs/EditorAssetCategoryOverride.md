# Game.Prefabs.EditorAssetCategoryOverride

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class EditorAssetCategoryOverride : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.String[] m_IncludeCategories;
    public System.String[] m_ExcludeCategories;

    public EditorAssetCategoryOverride();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public System.String[] m_IncludeCategories`  

```csharp
public System.String[] m_IncludeCategories;
```

- `public System.String[] m_ExcludeCategories`  

```csharp
public System.String[] m_ExcludeCategories;
```


## Constructors

- `public EditorAssetCategoryOverride()`  

```csharp
public EditorAssetCategoryOverride();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		if ((m_IncludeCategories != null && m_IncludeCategories.Length != 0) || (m_ExcludeCategories != null && m_ExcludeCategories.Length != 0))
		{
			components.Add(ComponentType.ReadWrite<EditorAssetCategoryOverrideData>());
		}
	}
```


