# Game.Prefabs.AudioSettingsPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AudioSettingsPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.EffectPrefab[] m_Effects;
    public System.Single m_MinHeight;
    public System.Single m_MaxHeight;
    public System.Single m_OverlapRatio;
    public System.Single m_MinDistanceRatio;
    public System.Int32 m_FireCullMaxAmount;
    public System.Single m_FireCullMaxDistance;
    public System.Int32 m_CarEngineCullMaxAmount;
    public System.Single m_CarEngineCullMaxDistance;
    public System.Int32 m_PublicTransCullMaxAmount;
    public System.Single m_PublicTransCullMaxDistance;

    public AudioSettingsPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.EffectPrefab[] m_Effects`  

```csharp
public Game.Prefabs.EffectPrefab[] m_Effects;
```

- `public System.Single m_MinHeight`  

```csharp
public System.Single m_MinHeight;
```

- `public System.Single m_MaxHeight`  

```csharp
public System.Single m_MaxHeight;
```

- `public System.Single m_OverlapRatio`  

```csharp
public System.Single m_OverlapRatio;
```

- `public System.Single m_MinDistanceRatio`  

```csharp
public System.Single m_MinDistanceRatio;
```

- `public System.Int32 m_FireCullMaxAmount`  

```csharp
public System.Int32 m_FireCullMaxAmount;
```

- `public System.Single m_FireCullMaxDistance`  

```csharp
public System.Single m_FireCullMaxDistance;
```

- `public System.Int32 m_CarEngineCullMaxAmount`  

```csharp
public System.Int32 m_CarEngineCullMaxAmount;
```

- `public System.Single m_CarEngineCullMaxDistance`  

```csharp
public System.Single m_CarEngineCullMaxDistance;
```

- `public System.Int32 m_PublicTransCullMaxAmount`  

```csharp
public System.Int32 m_PublicTransCullMaxAmount;
```

- `public System.Single m_PublicTransCullMaxDistance`  

```csharp
public System.Single m_PublicTransCullMaxDistance;
```


## Constructors

- `public AudioSettingsPrefab()`  

```csharp
public AudioSettingsPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


