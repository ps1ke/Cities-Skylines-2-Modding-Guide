# Game.Prefabs.MultipleUnitTrainFrontPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TrainPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class MultipleUnitTrainFrontPrefab : Game.Prefabs.TrainPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int32 m_MinMultipleUnitCount;
    public System.Int32 m_MaxMultipleUnitCount;
    public Game.Prefabs.MultipleUnitTrainCarriageInfo[] m_Carriages;
    public System.Boolean m_AddReversedEndCarriage;

    public MultipleUnitTrainFrontPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_MinMultipleUnitCount`  

```csharp
public System.Int32 m_MinMultipleUnitCount;
```

- `public System.Int32 m_MaxMultipleUnitCount`  

```csharp
public System.Int32 m_MaxMultipleUnitCount;
```

- `public Game.Prefabs.MultipleUnitTrainCarriageInfo[] m_Carriages`  

```csharp
public Game.Prefabs.MultipleUnitTrainCarriageInfo[] m_Carriages;
```

- `public System.Boolean m_AddReversedEndCarriage`  

```csharp
public System.Boolean m_AddReversedEndCarriage;
```


## Constructors

- `public MultipleUnitTrainFrontPrefab()`  

```csharp
public MultipleUnitTrainFrontPrefab();
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


