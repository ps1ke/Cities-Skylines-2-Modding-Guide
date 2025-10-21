# Game.Prefabs.ResourcePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public class ResourcePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public UnityEngine.Color m_Color;
    public Game.Economy.ResourceInEditor m_Resource;
    public System.Boolean m_IsProduceable;
    public System.Boolean m_IsTradable;
    public System.Boolean m_IsMaterial;
    public System.Boolean m_IsLeisure;
    public System.Single m_Weight;
    public Unity.Mathematics.float2 m_InitialPrice;
    public System.Single m_WealthModifier;
    public System.Single m_BaseConsumption;
    public System.Int32 m_CarConsumption;
    public System.Int32 m_ChildWeight;
    public System.Int32 m_TeenWeight;
    public System.Int32 m_AdultWeight;
    public System.Int32 m_ElderlyWeight;
    public System.Boolean m_RequireTemperature;
    public System.Single m_RequiredTemperature;
    public System.Boolean m_RequireNaturalResource;
    public Unity.Mathematics.int2 m_NeededWorkPerUnit;

    public ResourcePrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public UnityEngine.Color m_Color`  

```csharp
public UnityEngine.Color m_Color;
```

- `public Game.Economy.ResourceInEditor m_Resource`  

```csharp
public Game.Economy.ResourceInEditor m_Resource;
```

- `public System.Boolean m_IsProduceable`  

```csharp
public System.Boolean m_IsProduceable;
```

- `public System.Boolean m_IsTradable`  

```csharp
public System.Boolean m_IsTradable;
```

- `public System.Boolean m_IsMaterial`  

```csharp
public System.Boolean m_IsMaterial;
```

- `public System.Boolean m_IsLeisure`  

```csharp
public System.Boolean m_IsLeisure;
```

- `public System.Single m_Weight`  

```csharp
public System.Single m_Weight;
```

- `public Unity.Mathematics.float2 m_InitialPrice`  

```csharp
public Unity.Mathematics.float2 m_InitialPrice;
```

- `public System.Single m_WealthModifier`  

```csharp
public System.Single m_WealthModifier;
```

- `public System.Single m_BaseConsumption`  

```csharp
public System.Single m_BaseConsumption;
```

- `public System.Int32 m_CarConsumption`  

```csharp
public System.Int32 m_CarConsumption;
```

- `public System.Int32 m_ChildWeight`  

```csharp
public System.Int32 m_ChildWeight;
```

- `public System.Int32 m_TeenWeight`  

```csharp
public System.Int32 m_TeenWeight;
```

- `public System.Int32 m_AdultWeight`  

```csharp
public System.Int32 m_AdultWeight;
```

- `public System.Int32 m_ElderlyWeight`  

```csharp
public System.Int32 m_ElderlyWeight;
```

- `public System.Boolean m_RequireTemperature`  

```csharp
public System.Boolean m_RequireTemperature;
```

- `public System.Single m_RequiredTemperature`  

```csharp
public System.Single m_RequiredTemperature;
```

- `public System.Boolean m_RequireNaturalResource`  

```csharp
public System.Boolean m_RequireNaturalResource;
```

- `public Unity.Mathematics.int2 m_NeededWorkPerUnit`  

```csharp
public Unity.Mathematics.int2 m_NeededWorkPerUnit;
```


## Constructors

- `public ResourcePrefab()`  

```csharp
public ResourcePrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```


