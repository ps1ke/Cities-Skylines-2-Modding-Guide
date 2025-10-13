# Game.Prefabs.GuideLineSettings

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class GuideLineSettings : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public UnityEngine.Color m_VeryLowPriorityColor;
    public UnityEngine.Color m_LowPriorityColor;
    public UnityEngine.Color m_MediumPriorityColor;
    public UnityEngine.Color m_HighPriorityColor;
    public UnityEngine.Color m_PositiveFeedbackColor;
    public Game.Prefabs.GuideLineSettings+WaterSourceColor[] m_WaterSourceColors;

    public GuideLineSettings();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public UnityEngine.Color m_VeryLowPriorityColor`  

```csharp
public UnityEngine.Color m_VeryLowPriorityColor;
```

- `public UnityEngine.Color m_LowPriorityColor`  

```csharp
public UnityEngine.Color m_LowPriorityColor;
```

- `public UnityEngine.Color m_MediumPriorityColor`  

```csharp
public UnityEngine.Color m_MediumPriorityColor;
```

- `public UnityEngine.Color m_HighPriorityColor`  

```csharp
public UnityEngine.Color m_HighPriorityColor;
```

- `public UnityEngine.Color m_PositiveFeedbackColor`  

```csharp
public UnityEngine.Color m_PositiveFeedbackColor;
```

- `public Game.Prefabs.GuideLineSettings+WaterSourceColor[] m_WaterSourceColors`  

```csharp
public Game.Prefabs.GuideLineSettings+WaterSourceColor[] m_WaterSourceColors;
```


## Constructors

- `public GuideLineSettings()`  

```csharp
public GuideLineSettings();
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


## Nested types

- `Game.Prefabs.GuideLineSettings+WaterSourceColor`  

