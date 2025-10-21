# Game.Prefabs.DevTreeNodePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `RequireComponent`  

## Code

```csharp
public class DevTreeNodePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.ServicePrefab m_Service;
    public Game.Prefabs.DevTreeNodePrefab[] m_Requirements;
    public System.Int32 m_Cost;
    public System.Int32 m_HorizontalPosition;
    public System.Single m_VerticalPosition;
    public System.String m_IconPath;
    public Game.Prefabs.PrefabBase m_IconPrefab;

    public DevTreeNodePrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    private System.Boolean HasRequirements();
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.ServicePrefab m_Service`  

```csharp
public Game.Prefabs.ServicePrefab m_Service;
```

- `public Game.Prefabs.DevTreeNodePrefab[] m_Requirements`  

```csharp
public Game.Prefabs.DevTreeNodePrefab[] m_Requirements;
```

- `public System.Int32 m_Cost`  

```csharp
public System.Int32 m_Cost;
```

- `public System.Int32 m_HorizontalPosition`  

```csharp
public System.Int32 m_HorizontalPosition;
```

- `public System.Single m_VerticalPosition`  

```csharp
public System.Single m_VerticalPosition;
```

- `public System.String m_IconPath`  

```csharp
public System.String m_IconPath;
```

- `public Game.Prefabs.PrefabBase m_IconPrefab`  

```csharp
public Game.Prefabs.PrefabBase m_IconPrefab;
```


## Constructors

- `public DevTreeNodePrefab()`  

```csharp
public DevTreeNodePrefab();
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

- `private HasRequirements() : System.Boolean`  

```csharp
private System.Boolean HasRequirements();
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


