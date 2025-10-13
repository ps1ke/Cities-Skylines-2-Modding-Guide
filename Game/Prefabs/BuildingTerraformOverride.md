# Game.Prefabs.BuildingTerraformOverride

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class BuildingTerraformOverride : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Unity.Mathematics.float2 m_LevelMinOffset;
    public Unity.Mathematics.float2 m_LevelMaxOffset;
    public Unity.Mathematics.float2 m_LevelFrontLeft;
    public Unity.Mathematics.float2 m_LevelFrontRight;
    public Unity.Mathematics.float2 m_LevelBackLeft;
    public Unity.Mathematics.float2 m_LevelBackRight;
    public Unity.Mathematics.float2 m_SmoothMinOffset;
    public Unity.Mathematics.float2 m_SmoothMaxOffset;
    public System.Single m_HeightOffset;
    public Game.Prefabs.BuildingTerraformOverride+SubLot[] m_AdditionalSmoothAreas;
    public System.Boolean m_DontRaise;
    public System.Boolean m_DontLower;

    public BuildingTerraformOverride();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Unity.Mathematics.float2 m_LevelMinOffset`  

```csharp
public Unity.Mathematics.float2 m_LevelMinOffset;
```

- `public Unity.Mathematics.float2 m_LevelMaxOffset`  

```csharp
public Unity.Mathematics.float2 m_LevelMaxOffset;
```

- `public Unity.Mathematics.float2 m_LevelFrontLeft`  

```csharp
public Unity.Mathematics.float2 m_LevelFrontLeft;
```

- `public Unity.Mathematics.float2 m_LevelFrontRight`  

```csharp
public Unity.Mathematics.float2 m_LevelFrontRight;
```

- `public Unity.Mathematics.float2 m_LevelBackLeft`  

```csharp
public Unity.Mathematics.float2 m_LevelBackLeft;
```

- `public Unity.Mathematics.float2 m_LevelBackRight`  

```csharp
public Unity.Mathematics.float2 m_LevelBackRight;
```

- `public Unity.Mathematics.float2 m_SmoothMinOffset`  

```csharp
public Unity.Mathematics.float2 m_SmoothMinOffset;
```

- `public Unity.Mathematics.float2 m_SmoothMaxOffset`  

```csharp
public Unity.Mathematics.float2 m_SmoothMaxOffset;
```

- `public System.Single m_HeightOffset`  

```csharp
public System.Single m_HeightOffset;
```

- `public Game.Prefabs.BuildingTerraformOverride+SubLot[] m_AdditionalSmoothAreas`  

```csharp
public Game.Prefabs.BuildingTerraformOverride+SubLot[] m_AdditionalSmoothAreas;
```

- `public System.Boolean m_DontRaise`  

```csharp
public System.Boolean m_DontRaise;
```

- `public System.Boolean m_DontLower`  

```csharp
public System.Boolean m_DontLower;
```


## Constructors

- `public BuildingTerraformOverride()`  

```csharp
public BuildingTerraformOverride();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (base.prefab is BuildingExtensionPrefab)
		{
			components.Add(ComponentType.ReadWrite<Lot>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<BuildingTerraformData>());
		if (m_AdditionalSmoothAreas != null && m_AdditionalSmoothAreas.Length != 0)
		{
			components.Add(ComponentType.ReadWrite<AdditionalBuildingTerraformElement>());
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		if (m_AdditionalSmoothAreas != null && m_AdditionalSmoothAreas.Length != 0)
		{
			DynamicBuffer<AdditionalBuildingTerraformElement> buffer = entityManager.GetBuffer<AdditionalBuildingTerraformElement>(entity);
			buffer.ResizeUninitialized(m_AdditionalSmoothAreas.Length);
			for (int i = 0; i < m_AdditionalSmoothAreas.Length; i++)
			{
				SubLot subLot = m_AdditionalSmoothAreas[i];
				buffer[i] = new AdditionalBuildingTerraformElement
				{
					m_Area = subLot.m_Area,
					m_HeightOffset = subLot.m_HeightOffset,
					m_Circular = subLot.m_Circular,
					m_DontRaise = subLot.m_DontRaise,
					m_DontLower = subLot.m_DontLower
				};
			}
		}
	}
```


## Nested types

- `Game.Prefabs.BuildingTerraformOverride+SubLot`  

