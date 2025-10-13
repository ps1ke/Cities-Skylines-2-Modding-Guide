# Game.UI.InGame.EmploymentData

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct EmploymentData : Colossal.UI.Binding.IJsonWritable
{
    private readonly System.Int32 <uneducated>k__BackingField;
    private readonly System.Int32 <poorlyEducated>k__BackingField;
    private readonly System.Int32 <educated>k__BackingField;
    private readonly System.Int32 <wellEducated>k__BackingField;
    private readonly System.Int32 <highlyEducated>k__BackingField;
    private readonly System.Int32 <openPositions>k__BackingField;
    private readonly System.Int32 <total>k__BackingField;

    public System.Int32 uneducated { get; }
    public System.Int32 poorlyEducated { get; }
    public System.Int32 educated { get; }
    public System.Int32 wellEducated { get; }
    public System.Int32 highlyEducated { get; }
    public System.Int32 openPositions { get; }
    public System.Int32 total { get; }

    public EmploymentData(System.Int32 uneducated, System.Int32 poorlyEducated, System.Int32 educated, System.Int32 wellEducated, System.Int32 highlyEducated, System.Int32 openPositions);

    public static Game.UI.InGame.EmploymentData GetEmployeesData(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, System.Int32 openPositions);
    public static Game.UI.InGame.EmploymentData GetWorkplacesData(System.Int32 maxWorkers, System.Int32 buildingLevel, Game.Prefabs.WorkplaceComplexity complexity);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly System.Int32 <uneducated>k__BackingField`  

```csharp
private readonly System.Int32 <uneducated>k__BackingField;
```

- `private readonly System.Int32 <poorlyEducated>k__BackingField`  

```csharp
private readonly System.Int32 <poorlyEducated>k__BackingField;
```

- `private readonly System.Int32 <educated>k__BackingField`  

```csharp
private readonly System.Int32 <educated>k__BackingField;
```

- `private readonly System.Int32 <wellEducated>k__BackingField`  

```csharp
private readonly System.Int32 <wellEducated>k__BackingField;
```

- `private readonly System.Int32 <highlyEducated>k__BackingField`  

```csharp
private readonly System.Int32 <highlyEducated>k__BackingField;
```

- `private readonly System.Int32 <openPositions>k__BackingField`  

```csharp
private readonly System.Int32 <openPositions>k__BackingField;
```

- `private readonly System.Int32 <total>k__BackingField`  

```csharp
private readonly System.Int32 <total>k__BackingField;
```


## Properties

- `public System.Int32 uneducated { get }`  

```csharp
public System.Int32 uneducated { get; }
```

- `public System.Int32 poorlyEducated { get }`  

```csharp
public System.Int32 poorlyEducated { get; }
```

- `public System.Int32 educated { get }`  

```csharp
public System.Int32 educated { get; }
```

- `public System.Int32 wellEducated { get }`  

```csharp
public System.Int32 wellEducated { get; }
```

- `public System.Int32 highlyEducated { get }`  

```csharp
public System.Int32 highlyEducated { get; }
```

- `public System.Int32 openPositions { get }`  

```csharp
public System.Int32 openPositions { get; }
```

- `public System.Int32 total { get }`  

```csharp
public System.Int32 total { get; }
```


## Constructors

- `public EmploymentData(System.Int32 uneducated, System.Int32 poorlyEducated, System.Int32 educated, System.Int32 wellEducated, System.Int32 highlyEducated, System.Int32 openPositions)`  

```csharp
public EmploymentData(int uneducated, int poorlyEducated, int educated, int wellEducated, int highlyEducated, int openPositions)
	{
		this.uneducated = uneducated;
		this.poorlyEducated = poorlyEducated;
		this.educated = educated;
		this.wellEducated = wellEducated;
		this.highlyEducated = highlyEducated;
		this.openPositions = openPositions;
		total = uneducated + poorlyEducated + educated + wellEducated + highlyEducated + openPositions;
	}
```


## Methods

- `public static GetEmployeesData(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, System.Int32 openPositions) : Game.UI.InGame.EmploymentData`  

```csharp
public static EmploymentData GetEmployeesData(DynamicBuffer<Employee> employees, int openPositions)
	{
		int num = 0;
		int num2 = 0;
		int num3 = 0;
		int num4 = 0;
		int num5 = 0;
		for (int i = 0; i < employees.Length; i++)
		{
			switch (employees[i].m_Level)
			{
			case 0:
				num++;
				break;
			case 1:
				num2++;
				break;
			case 2:
				num3++;
				break;
			case 3:
				num4++;
				break;
			case 4:
				num5++;
				break;
			}
		}
		return new EmploymentData(num, num2, num3, num4, num5, openPositions);
	}
```

- `public static GetWorkplacesData(System.Int32 maxWorkers, System.Int32 buildingLevel, Game.Prefabs.WorkplaceComplexity complexity) : Game.UI.InGame.EmploymentData`  

```csharp
public static EmploymentData GetWorkplacesData(int maxWorkers, int buildingLevel, WorkplaceComplexity complexity)
	{
		Workplaces workplaces = EconomyUtils.CalculateNumberOfWorkplaces(maxWorkers, complexity, buildingLevel);
		return new EmploymentData(workplaces.m_Uneducated, workplaces.m_PoorlyEducated, workplaces.m_Educated, workplaces.m_WellEducated, workplaces.m_HighlyEducated, 0);
	}
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin("selectedInfo.ChartData");
		writer.PropertyName("values");
		writer.ArrayBegin(6u);
		writer.Write(uneducated);
		writer.Write(poorlyEducated);
		writer.Write(educated);
		writer.Write(wellEducated);
		writer.Write(highlyEducated);
		writer.Write(openPositions);
		writer.ArrayEnd();
		writer.PropertyName("total");
		writer.Write(total);
		writer.TypeEnd();
	}
```


