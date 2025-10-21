# Game.Prefabs.IconConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class IconConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public UnityEngine.Material m_Material;
    public Game.Prefabs.NotificationIconPrefab m_SelectedMarker;
    public Game.Prefabs.NotificationIconPrefab m_FollowedMarker;
    public Game.Prefabs.IconAnimationInfo[] m_Animations;
    public UnityEngine.Texture2D m_MissingIcon;

    public IconConfigurationPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public UnityEngine.Material m_Material`  

```csharp
public UnityEngine.Material m_Material;
```

- `public Game.Prefabs.NotificationIconPrefab m_SelectedMarker`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_SelectedMarker;
```

- `public Game.Prefabs.NotificationIconPrefab m_FollowedMarker`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_FollowedMarker;
```

- `public Game.Prefabs.IconAnimationInfo[] m_Animations`  

```csharp
public Game.Prefabs.IconAnimationInfo[] m_Animations;
```

- `public UnityEngine.Texture2D m_MissingIcon`  

```csharp
public UnityEngine.Texture2D m_MissingIcon;
```


## Constructors

- `public IconConfigurationPrefab()`  

```csharp
public IconConfigurationPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


