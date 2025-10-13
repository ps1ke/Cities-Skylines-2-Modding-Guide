# Game.Prefabs.ParametricStatistic

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.StatisticsPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public abstract class ParametricStatistic : Game.Prefabs.StatisticsPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    protected ParametricStatistic();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public abstract System.String GetParameterName(System.Int32 parameter);
    public abstract System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData> GetParameters();
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Constructors

- `protected ParametricStatistic()`  

```csharp
protected ParametricStatistic();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public abstract GetParameterName(System.Int32 parameter) : System.String`  

```csharp
public abstract System.String GetParameterName(System.Int32 parameter);
```

- `public abstract GetParameters() : System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData>`  

```csharp
public abstract System.Collections.Generic.IEnumerable<Game.Prefabs.StatisticParameterData> GetParameters();
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


