# Game.Prefabs.UICompositeTagPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.UITagPrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class UICompositeTagPrefab : Game.Prefabs.UITagPrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.PrefabBase[] m_UITagProviders;

    public System.String uiTag { get; }

    public UICompositeTagPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
}
```


## Fields

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

- `public UICompositeTagPrefab()`  

```csharp
public UICompositeTagPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```


## Nested types

- `Game.Prefabs.UICompositeTagPrefab+<>c`  

