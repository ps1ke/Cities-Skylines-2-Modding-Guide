# Game.Prefabs.TaxableResourceData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct TaxableResourceData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public System.Byte m_TaxAreas;

    public TaxableResourceData(System.Collections.Generic.IEnumerable<Game.Simulation.TaxAreaType> taxAreas);

    public System.Boolean Contains(Game.Simulation.TaxAreaType areaType);
    private static System.Int32 GetBit(Game.Simulation.TaxAreaType areaType);
}
```


## Fields

- `public System.Byte m_TaxAreas`  

```csharp
public System.Byte m_TaxAreas;
```


## Constructors

- `public TaxableResourceData(System.Collections.Generic.IEnumerable<Game.Simulation.TaxAreaType> taxAreas)`  

```csharp
public TaxableResourceData(IEnumerable<TaxAreaType> taxAreas)
	{
		m_TaxAreas = 0;
		foreach (TaxAreaType taxArea in taxAreas)
		{
			m_TaxAreas |= (byte)GetBit(taxArea);
		}
	}
```


## Methods

- `public Contains(Game.Simulation.TaxAreaType areaType) : System.Boolean`  

```csharp
public bool Contains(TaxAreaType areaType)
	{
		return (m_TaxAreas & GetBit(areaType)) != 0;
	}
```

- `private static GetBit(Game.Simulation.TaxAreaType areaType) : System.Int32`  

```csharp
private static int GetBit(TaxAreaType areaType)
	{
		return 1 << (int)(areaType - 1);
	}
```


