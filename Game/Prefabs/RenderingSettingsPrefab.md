# Game.Prefabs.RenderingSettingsPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RenderingSettingsPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public UnityEngine.Color m_HoveredColor;
    public UnityEngine.Color m_OverrideColor;
    public UnityEngine.Color m_WarningColor;
    public UnityEngine.Color m_ErrorColor;
    public UnityEngine.Color m_OwnerColor;

    public RenderingSettingsPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public UnityEngine.Color m_HoveredColor`  

```csharp
public UnityEngine.Color m_HoveredColor;
```

- `public UnityEngine.Color m_OverrideColor`  

```csharp
public UnityEngine.Color m_OverrideColor;
```

- `public UnityEngine.Color m_WarningColor`  

```csharp
public UnityEngine.Color m_WarningColor;
```

- `public UnityEngine.Color m_ErrorColor`  

```csharp
public UnityEngine.Color m_ErrorColor;
```

- `public UnityEngine.Color m_OwnerColor`  

```csharp
public UnityEngine.Color m_OwnerColor;
```


## Constructors

- `public RenderingSettingsPrefab()`  

```csharp
public RenderingSettingsPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


