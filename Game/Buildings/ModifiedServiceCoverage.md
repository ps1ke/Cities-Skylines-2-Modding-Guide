# Game.Buildings.ModifiedServiceCoverage

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ModifiedServiceCoverage : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_Range;
    public System.Single m_Capacity;
    public System.Single m_Magnitude;

    public ModifiedServiceCoverage(Game.Prefabs.CoverageData coverage);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void ReplaceData(Game.Prefabs.CoverageData& coverage);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_Range`  

```csharp
public System.Single m_Range;
```

- `public System.Single m_Capacity`  

```csharp
public System.Single m_Capacity;
```

- `public System.Single m_Magnitude`  

```csharp
public System.Single m_Magnitude;
```


## Constructors

- `public ModifiedServiceCoverage(Game.Prefabs.CoverageData coverage)`  

```csharp
public ModifiedServiceCoverage(CoverageData coverage)
	{
		m_Capacity = coverage.m_Capacity;
		m_Range = coverage.m_Range;
		m_Magnitude = coverage.m_Magnitude;
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public ReplaceData(Game.Prefabs.CoverageData& coverage) : System.Void`  

```csharp
public void ReplaceData(ref CoverageData coverage)
	{
		coverage.m_Capacity = m_Capacity;
		coverage.m_Range = m_Range;
		coverage.m_Magnitude = m_Magnitude;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


