# Game.Simulation.ZoneAmbiences

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ZoneAmbiences : Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_ResidentialLow;
    public System.Single m_CommercialLow;
    public System.Single m_Industrial;
    public System.Single m_Agriculture;
    public System.Single m_Forestry;
    public System.Single m_Oil;
    public System.Single m_Ore;
    public System.Single m_OfficeLow;
    public System.Single m_OfficeHigh;
    public System.Single m_ResidentialMedium;
    public System.Single m_ResidentialHigh;
    public System.Single m_ResidentialMixed;
    public System.Single m_CommercialHigh;
    public System.Single m_ResidentialLowRent;
    public System.Single m_Forest;
    public System.Single m_WaterfrontLow;
    public System.Single m_AquacultureLand;
    public System.Single m_SeagullAmbience;

    public System.Void AddAmbience(Game.Simulation.GroupAmbienceType type, System.Single value);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Single GetAmbience(Game.Simulation.GroupAmbienceType type);
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_ResidentialLow`  

```csharp
public System.Single m_ResidentialLow;
```

- `public System.Single m_CommercialLow`  

```csharp
public System.Single m_CommercialLow;
```

- `public System.Single m_Industrial`  

```csharp
public System.Single m_Industrial;
```

- `public System.Single m_Agriculture`  

```csharp
public System.Single m_Agriculture;
```

- `public System.Single m_Forestry`  

```csharp
public System.Single m_Forestry;
```

- `public System.Single m_Oil`  

```csharp
public System.Single m_Oil;
```

- `public System.Single m_Ore`  

```csharp
public System.Single m_Ore;
```

- `public System.Single m_OfficeLow`  

```csharp
public System.Single m_OfficeLow;
```

- `public System.Single m_OfficeHigh`  

```csharp
public System.Single m_OfficeHigh;
```

- `public System.Single m_ResidentialMedium`  

```csharp
public System.Single m_ResidentialMedium;
```

- `public System.Single m_ResidentialHigh`  

```csharp
public System.Single m_ResidentialHigh;
```

- `public System.Single m_ResidentialMixed`  

```csharp
public System.Single m_ResidentialMixed;
```

- `public System.Single m_CommercialHigh`  

```csharp
public System.Single m_CommercialHigh;
```

- `public System.Single m_ResidentialLowRent`  

```csharp
public System.Single m_ResidentialLowRent;
```

- `public System.Single m_Forest`  

```csharp
public System.Single m_Forest;
```

- `public System.Single m_WaterfrontLow`  

```csharp
public System.Single m_WaterfrontLow;
```

- `public System.Single m_AquacultureLand`  

```csharp
public System.Single m_AquacultureLand;
```

- `public System.Single m_SeagullAmbience`  

```csharp
public System.Single m_SeagullAmbience;
```


## Methods

- `public AddAmbience(Game.Simulation.GroupAmbienceType type, System.Single value) : System.Void`  

```csharp
public void AddAmbience(GroupAmbienceType type, float value)
	{
		switch (type)
		{
		case GroupAmbienceType.ResidentialLow:
			m_ResidentialLow += value;
			break;
		case GroupAmbienceType.CommercialLow:
			m_CommercialLow += value;
			break;
		case GroupAmbienceType.Industrial:
			m_Industrial += value;
			break;
		case GroupAmbienceType.Agriculture:
			m_Agriculture += value;
			break;
		case GroupAmbienceType.Forestry:
			m_Forestry += value;
			break;
		case GroupAmbienceType.Oil:
			m_Oil += value;
			break;
		case GroupAmbienceType.Ore:
			m_Ore += value;
			break;
		case GroupAmbienceType.OfficeLow:
			m_OfficeLow += value;
			break;
		case GroupAmbienceType.OfficeHigh:
			m_OfficeHigh += value;
			break;
		case GroupAmbienceType.ResidentialMedium:
			m_ResidentialMedium += value;
			break;
		case GroupAmbienceType.ResidentialHigh:
			m_ResidentialHigh += value;
			break;
		case GroupAmbienceType.ResidentialMixed:
			m_ResidentialMixed += value;
			break;
		case GroupAmbienceType.CommercialHigh:
			m_CommercialHigh += value;
			break;
		case GroupAmbienceType.ResidentialLowRent:
			m_ResidentialLowRent += value;
			break;
		case GroupAmbienceType.Forest:
			m_Forest += value;
			break;
		case GroupAmbienceType.WaterfrontLow:
			m_WaterfrontLow += value;
			break;
		case GroupAmbienceType.AquacultureLand:
			m_AquacultureLand += value;
			break;
		case GroupAmbienceType.SeagullAmbience:
			m_SeagullAmbience += value;
			break;
		case GroupAmbienceType.Traffic:
		case GroupAmbienceType.Rain:
		case GroupAmbienceType.NightForest:
			break;
		}
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetAmbience(Game.Simulation.GroupAmbienceType type) : System.Single`  

```csharp
public float GetAmbience(GroupAmbienceType type)
	{
		return type switch
		{
			GroupAmbienceType.ResidentialLow => m_ResidentialLow, 
			GroupAmbienceType.CommercialLow => m_CommercialLow, 
			GroupAmbienceType.Industrial => m_Industrial, 
			GroupAmbienceType.Agriculture => m_Agriculture, 
			GroupAmbienceType.Forestry => m_Forestry, 
			GroupAmbienceType.Oil => m_Oil, 
			GroupAmbienceType.Ore => m_Ore, 
			GroupAmbienceType.OfficeLow => m_OfficeLow, 
			GroupAmbienceType.OfficeHigh => m_OfficeHigh, 
			GroupAmbienceType.ResidentialMedium => m_ResidentialMedium, 
			GroupAmbienceType.ResidentialHigh => m_ResidentialHigh, 
			GroupAmbienceType.ResidentialMixed => m_ResidentialMixed, 
			GroupAmbienceType.CommercialHigh => m_CommercialHigh, 
			GroupAmbienceType.ResidentialLowRent => m_ResidentialLowRent, 
			GroupAmbienceType.Forest => m_Forest, 
			GroupAmbienceType.WaterfrontLow => m_WaterfrontLow, 
			GroupAmbienceType.AquacultureLand => m_AquacultureLand, 
			GroupAmbienceType.SeagullAmbience => m_SeagullAmbience, 
			_ => 0f, 
		};
	}
```

- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  

```csharp
public int GetStride(Context context)
	{
		return 72;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


