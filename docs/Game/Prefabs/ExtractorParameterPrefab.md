# Game.Prefabs.ExtractorParameterPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ExtractorParameterPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_FertilityConsumption;
    public System.Single m_FishConsumption;
    public System.Single m_OreConsumption;
    public System.Single m_ForestConsumption;
    public System.Single m_OilConsumption;
    public System.Single m_FullFertility;
    public System.Single m_FullFish;
    public System.Single m_FullOre;
    public System.Single m_FullOil;

    public ExtractorParameterPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_FertilityConsumption`  

```csharp
public System.Single m_FertilityConsumption;
```

- `public System.Single m_FishConsumption`  

```csharp
public System.Single m_FishConsumption;
```

- `public System.Single m_OreConsumption`  

```csharp
public System.Single m_OreConsumption;
```

- `public System.Single m_ForestConsumption`  

```csharp
public System.Single m_ForestConsumption;
```

- `public System.Single m_OilConsumption`  

```csharp
public System.Single m_OilConsumption;
```

- `public System.Single m_FullFertility`  

```csharp
public System.Single m_FullFertility;
```

- `public System.Single m_FullFish`  

```csharp
public System.Single m_FullFish;
```

- `public System.Single m_FullOre`  

```csharp
public System.Single m_FullOre;
```

- `public System.Single m_FullOil`  

```csharp
public System.Single m_FullOil;
```


## Constructors

- `public ExtractorParameterPrefab()`  

```csharp
public ExtractorParameterPrefab();
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

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


