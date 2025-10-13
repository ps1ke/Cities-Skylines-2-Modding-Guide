# Game.Companies.FreeWorkplaces

**Assembly:** `Game`  
**Namespace:** `Game.Companies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct FreeWorkplaces : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Byte m_Uneducated;
    public System.Byte m_PoorlyEducated;
    public System.Byte m_Educated;
    public System.Byte m_WellEducated;
    public System.Byte m_HighlyEducated;

    public System.Int32 Count { get; }

    public FreeWorkplaces(Game.Companies.Workplaces free);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Int32 GetBestFor(System.Int32 level);
    public System.Byte GetFree(System.Int32 level);
    public System.Byte GetLowestFree();
    public System.Void Refresh(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, System.Int32 maxWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 level);
    public System.Void Serialize<TWriter>(TWriter writer);
    private System.Void SetFree(System.Int32 level, System.Byte amount);
}
```


## Fields

- `public System.Byte m_Uneducated`  

```csharp
public System.Byte m_Uneducated;
```

- `public System.Byte m_PoorlyEducated`  

```csharp
public System.Byte m_PoorlyEducated;
```

- `public System.Byte m_Educated`  

```csharp
public System.Byte m_Educated;
```

- `public System.Byte m_WellEducated`  

```csharp
public System.Byte m_WellEducated;
```

- `public System.Byte m_HighlyEducated`  

```csharp
public System.Byte m_HighlyEducated;
```


## Properties

- `public System.Int32 Count { get }`  

```csharp
public System.Int32 Count { get; }
```


## Constructors

- `public FreeWorkplaces(Game.Companies.Workplaces free)`  

```csharp
public FreeWorkplaces(Workplaces free)
	{
		m_Uneducated = (byte)math.clamp(free.m_Uneducated, 0, 255);
		m_PoorlyEducated = (byte)math.clamp(free.m_PoorlyEducated, 0, 255);
		m_Educated = (byte)math.clamp(free.m_Educated, 0, 255);
		m_WellEducated = (byte)math.clamp(free.m_WellEducated, 0, 255);
		m_HighlyEducated = (byte)math.clamp(free.m_HighlyEducated, 0, 255);
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetBestFor(System.Int32 level) : System.Int32`  

```csharp
public int GetBestFor(int level)
	{
		for (int num = level; num >= 0; num--)
		{
			if (GetFree((byte)num) > 0)
			{
				return num;
			}
		}
		return -1;
	}
```

- `public GetFree(System.Int32 level) : System.Byte`  

```csharp
public byte GetFree(int level)
	{
		return level switch
		{
			0 => m_Uneducated, 
			1 => m_PoorlyEducated, 
			2 => m_Educated, 
			3 => m_WellEducated, 
			4 => m_HighlyEducated, 
			_ => 0, 
		};
	}
```

- `public GetLowestFree() : System.Byte`  

```csharp
public byte GetLowestFree()
	{
		for (byte b = 0; b <= 4; b++)
		{
			if (GetFree(b) > 0)
			{
				return b;
			}
		}
		return 5;
	}
```

- `public Refresh(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, System.Int32 maxWorkers, Game.Prefabs.WorkplaceComplexity complexity, System.Int32 level) : System.Void`  

```csharp
public void Refresh(DynamicBuffer<Employee> employees, int maxWorkers, WorkplaceComplexity complexity, int level)
	{
		Workplaces workplaces = EconomyUtils.CalculateNumberOfWorkplaces(maxWorkers, complexity, level);
		for (int i = 0; i < employees.Length; i++)
		{
			workplaces[employees[i].m_Level]--;
		}
		m_Uneducated = (byte)math.clamp(workplaces.m_Uneducated, 0, 255);
		m_PoorlyEducated = (byte)math.clamp(workplaces.m_PoorlyEducated, 0, 255);
		m_Educated = (byte)math.clamp(workplaces.m_Educated, 0, 255);
		m_WellEducated = (byte)math.clamp(workplaces.m_WellEducated, 0, 255);
		m_HighlyEducated = (byte)math.clamp(workplaces.m_HighlyEducated, 0, 255);
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `private SetFree(System.Int32 level, System.Byte amount) : System.Void`  

```csharp
private void SetFree(int level, byte amount)
	{
		switch (level)
		{
		case 0:
			m_Uneducated = amount;
			break;
		case 1:
			m_PoorlyEducated = amount;
			break;
		case 2:
			m_Educated = amount;
			break;
		case 3:
			m_WellEducated = amount;
			break;
		case 4:
			m_HighlyEducated = amount;
			break;
		}
	}
```


