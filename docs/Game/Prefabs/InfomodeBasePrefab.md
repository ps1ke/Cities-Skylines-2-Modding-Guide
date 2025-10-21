# Game.Prefabs.InfomodeBasePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.InfomodePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public abstract class InfomodeBasePrefab : Game.Prefabs.InfomodePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.InfomodeGroupPrefab[] m_IncludeInGroups;

    protected InfomodeBasePrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
}
```


## Fields

- `public Game.Prefabs.InfomodeGroupPrefab[] m_IncludeInGroups`  

```csharp
public Game.Prefabs.InfomodeGroupPrefab[] m_IncludeInGroups;
```


## Constructors

- `protected InfomodeBasePrefab()`  

```csharp
protected InfomodeBasePrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```


