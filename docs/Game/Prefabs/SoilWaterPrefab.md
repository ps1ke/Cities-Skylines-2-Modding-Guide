# Game.Prefabs.SoilWaterPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class SoilWaterPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_RainMultiplier;
    public System.Single m_HeightEffect;
    public System.Single m_MaxDiffusion;
    public System.Single m_WaterPerUnit;
    public System.Single m_MoistureUnderWater;
    public System.Single m_MaximumWaterDepth;
    public System.Single m_OverflowRate;

    public SoilWaterPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_RainMultiplier`  

```csharp
public System.Single m_RainMultiplier;
```

- `public System.Single m_HeightEffect`  

```csharp
public System.Single m_HeightEffect;
```

- `public System.Single m_MaxDiffusion`  

```csharp
public System.Single m_MaxDiffusion;
```

- `public System.Single m_WaterPerUnit`  

```csharp
public System.Single m_WaterPerUnit;
```

- `public System.Single m_MoistureUnderWater`  

```csharp
public System.Single m_MoistureUnderWater;
```

- `public System.Single m_MaximumWaterDepth`  

```csharp
public System.Single m_MaximumWaterDepth;
```

- `public System.Single m_OverflowRate`  

```csharp
public System.Single m_OverflowRate;
```


## Constructors

- `public SoilWaterPrefab()`  

```csharp
public SoilWaterPrefab();
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


