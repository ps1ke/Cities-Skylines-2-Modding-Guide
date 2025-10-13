# Game.Prefabs.StatisticParameterData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

## Code

```csharp
public sealed struct StatisticParameterData : Unity.Entities.IBufferElementData
{
    public System.Int32 m_Value;
    public UnityEngine.Color m_Color;

    public StatisticParameterData(System.Int32 value, UnityEngine.Color color);

}
```


## Fields

- `public System.Int32 m_Value`  

```csharp
public System.Int32 m_Value;
```

- `public UnityEngine.Color m_Color`  

```csharp
public UnityEngine.Color m_Color;
```


## Constructors

- `public StatisticParameterData(System.Int32 value, UnityEngine.Color color)`  

```csharp
public StatisticParameterData(int value, Color color)
	{
		m_Value = value;
		m_Color = color;
	}
```


