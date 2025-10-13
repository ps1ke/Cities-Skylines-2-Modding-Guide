# Game.Prefabs.LotPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.AreaPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class LotPrefab : Game.Prefabs.AreaPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_MaxRadius;
    public UnityEngine.Color m_RangeColor;
    public System.Boolean m_OnWater;
    public System.Boolean m_AllowOverlap;
    public System.Boolean m_AllowEditing;

    public LotPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_MaxRadius`  

```csharp
public System.Single m_MaxRadius;
```

- `public UnityEngine.Color m_RangeColor`  

```csharp
public UnityEngine.Color m_RangeColor;
```

- `public System.Boolean m_OnWater`  

```csharp
public System.Boolean m_OnWater;
```

- `public System.Boolean m_AllowOverlap`  

```csharp
public System.Boolean m_AllowOverlap;
```

- `public System.Boolean m_AllowEditing`  

```csharp
public System.Boolean m_AllowEditing;
```


## Constructors

- `public LotPrefab()`  

```csharp
public LotPrefab();
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


