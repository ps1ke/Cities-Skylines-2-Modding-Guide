# Game.Prefabs.AtmospherePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AtmospherePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public UnityEngine.Texture2D m_MoonAlbedo;
    public UnityEngine.Texture2D m_MoonNormal;

    public AtmospherePrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public UnityEngine.Texture2D m_MoonAlbedo`  

```csharp
public UnityEngine.Texture2D m_MoonAlbedo;
```

- `public UnityEngine.Texture2D m_MoonNormal`  

```csharp
public UnityEngine.Texture2D m_MoonNormal;
```


## Constructors

- `public AtmospherePrefab()`  

```csharp
public AtmospherePrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<AtmospherePrefabData>());
	}
```


