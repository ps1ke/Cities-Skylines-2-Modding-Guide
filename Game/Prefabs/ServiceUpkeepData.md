# Game.Prefabs.ServiceUpkeepData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Game.Prefabs.ICombineBuffer<Game.Prefabs.ServiceUpkeepData>`  

## Code

```csharp
public sealed struct ServiceUpkeepData : Unity.Entities.IBufferElementData, Game.Prefabs.ICombineBuffer<Game.Prefabs.ServiceUpkeepData>
{
    public Game.Prefabs.ResourceStack m_Upkeep;
    public System.Boolean m_ScaleWithUsage;

    public Game.Prefabs.ServiceUpkeepData ApplyServiceUsage(System.Single scale);
    public System.Void Combine(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> result);
}
```


## Fields

- `public Game.Prefabs.ResourceStack m_Upkeep`  

```csharp
public Game.Prefabs.ResourceStack m_Upkeep;
```

- `public System.Boolean m_ScaleWithUsage`  

```csharp
public System.Boolean m_ScaleWithUsage;
```


## Methods

- `public ApplyServiceUsage(System.Single scale) : Game.Prefabs.ServiceUpkeepData`  

```csharp
public ServiceUpkeepData ApplyServiceUsage(float scale)
	{
		return new ServiceUpkeepData
		{
			m_Upkeep = new ResourceStack
			{
				m_Amount = (int)((float)m_Upkeep.m_Amount * scale),
				m_Resource = m_Upkeep.m_Resource
			},
			m_ScaleWithUsage = m_ScaleWithUsage
		};
	}
```

- `public Combine(Unity.Collections.NativeList<Game.Prefabs.ServiceUpkeepData> result) : System.Void`  

```csharp
public void Combine(NativeList<ServiceUpkeepData> result)
	{
		for (int i = 0; i < result.Length; i++)
		{
			ref ServiceUpkeepData reference = ref result.ElementAt(i);
			if (reference.m_Upkeep.m_Resource == m_Upkeep.m_Resource && reference.m_ScaleWithUsage == m_ScaleWithUsage)
			{
				reference.m_Upkeep.m_Amount += m_Upkeep.m_Amount;
				return;
			}
		}
		result.Add(in this);
	}
```


