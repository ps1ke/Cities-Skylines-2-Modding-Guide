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
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<GuideLineSettingsData>());
		components.Add(ComponentType.ReadWrite<WaterSourceColorElement>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		GuideLineSettingsData componentData = new GuideLineSettingsData
		{
			m_VeryLowPriorityColor = m_VeryLowPriorityColor,
			m_LowPriorityColor = m_LowPriorityColor,
			m_MediumPriorityColor = m_MediumPriorityColor,
			m_HighPriorityColor = m_HighPriorityColor,
			m_PositiveFeedbackColor = m_PositiveFeedbackColor
		};
		entityManager.SetComponentData(entity, componentData);
		if (m_WaterSourceColors != null)
		{
			DynamicBuffer<WaterSourceColorElement> buffer = entityManager.GetBuffer<WaterSourceColorElement>(entity);
			buffer.ResizeUninitialized(m_WaterSourceColors.Length);
			for (int i = 0; i < m_WaterSourceColors.Length; i++)
			{
				WaterSourceColor waterSourceColor = m_WaterSourceColors[i];
				buffer[i] = new WaterSourceColorElement
				{
					m_Outline = waterSourceColor.m_Outline,
					m_Fill = waterSourceColor.m_Fill,
					m_ProjectedOutline = waterSourceColor.m_ProjectedOutline,
					m_ProjectedFill = waterSourceColor.m_ProjectedFill
				};
			}
		}
	}
```


## Nested types

- `Game.Prefabs.GuideLineSettings+WaterSourceColor`  

