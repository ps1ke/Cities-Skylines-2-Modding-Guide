# Game.Prefabs.VehicleSelectRequirementData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct VehicleSelectRequirementData
{
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.Locked> m_LockedType;
    private Unity.Entities.BufferTypeHandle<Game.Prefabs.ObjectRequirementElement> m_ObjectRequirementType;
    private Unity.Entities.ComponentLookup<Game.Prefabs.ThemeData> m_ThemeData;
    private Unity.Entities.Entity m_DefaultTheme;

    public VehicleSelectRequirementData(Unity.Entities.SystemBase system);

    public System.Boolean CheckRequirements(Game.Prefabs.VehicleSelectRequirementData+Chunk& chunk, System.Int32 index, System.Boolean ignoreTheme);
    public Game.Prefabs.VehicleSelectRequirementData+Chunk GetChunk(Unity.Entities.ArchetypeChunk chunk);
    public System.Void Update(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem);
}
```


## Fields

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.Locked> m_LockedType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.Locked> m_LockedType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Prefabs.ObjectRequirementElement> m_ObjectRequirementType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Prefabs.ObjectRequirementElement> m_ObjectRequirementType;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.ThemeData> m_ThemeData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.ThemeData> m_ThemeData;
```

- `private Unity.Entities.Entity m_DefaultTheme`  

```csharp
private Unity.Entities.Entity m_DefaultTheme;
```


## Constructors

- `public VehicleSelectRequirementData(Unity.Entities.SystemBase system)`  

```csharp
public VehicleSelectRequirementData(SystemBase system)
	{
		m_LockedType = system.GetComponentTypeHandle<Locked>(isReadOnly: true);
		m_ObjectRequirementType = system.GetBufferTypeHandle<ObjectRequirementElement>(isReadOnly: true);
		m_ThemeData = system.GetComponentLookup<ThemeData>(isReadOnly: true);
		m_DefaultTheme = default(Entity);
	}
```


## Methods

- `public CheckRequirements(Game.Prefabs.VehicleSelectRequirementData+Chunk& chunk, System.Int32 index, System.Boolean ignoreTheme = False) : System.Boolean`  

```csharp
public bool CheckRequirements(ref Chunk chunk, int index, bool ignoreTheme = false)
	{
		if (chunk.m_LockedMask.EnableBit.IsValid && chunk.m_LockedMask[index])
		{
			return false;
		}
		if (chunk.m_ObjectRequirements.Length != 0)
		{
			DynamicBuffer<ObjectRequirementElement> dynamicBuffer = chunk.m_ObjectRequirements[index];
			int num = -1;
			bool flag = true;
			for (int i = 0; i < dynamicBuffer.Length; i++)
			{
				ObjectRequirementElement objectRequirementElement = dynamicBuffer[i];
				if (objectRequirementElement.m_Group != num)
				{
					if (!flag)
					{
						break;
					}
					num = objectRequirementElement.m_Group;
					flag = false;
				}
				flag |= m_DefaultTheme == objectRequirementElement.m_Requirement || (ignoreTheme && m_ThemeData.HasComponent(objectRequirementElement.m_Requirement));
			}
			if (!flag)
			{
				return false;
			}
		}
		return true;
	}
```

- `public GetChunk(Unity.Entities.ArchetypeChunk chunk) : Game.Prefabs.VehicleSelectRequirementData+Chunk`  

```csharp
public Chunk GetChunk(ArchetypeChunk chunk)
	{
		return new Chunk
		{
			m_LockedMask = chunk.GetEnabledMask(ref m_LockedType),
			m_ObjectRequirements = chunk.GetBufferAccessor(ref m_ObjectRequirementType)
		};
	}
```

- `public Update(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem) : System.Void`  

```csharp
public void Update(SystemBase system, CityConfigurationSystem cityConfigurationSystem)
	{
		m_LockedType.Update(system);
		m_ObjectRequirementType.Update(system);
		m_ThemeData.Update(system);
		m_DefaultTheme = cityConfigurationSystem.defaultTheme;
	}
```


## Nested types

- `Game.Prefabs.VehicleSelectRequirementData+Chunk`  

