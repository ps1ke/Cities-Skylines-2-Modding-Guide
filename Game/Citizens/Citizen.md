# Game.Citizens.Citizen

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Citizen : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.UInt16 m_PseudoRandom;
    public Game.Citizens.CitizenFlags m_State;
    public System.Byte m_WellBeing;
    public System.Byte m_Health;
    public System.Byte m_LeisureCounter;
    public System.Byte m_PenaltyCounter;
    public System.Int32 m_UnemploymentCounter;
    public System.Int16 m_BirthDay;

    public System.Int32 Happiness { get; }

    public System.Void Deserialize<TReader>(TReader reader);
    public Game.Citizens.CitizenAge GetAge();
    public System.Single GetAgeInDays(System.UInt32 simulationFrame, Game.Common.TimeData timeData);
    public System.Int32 GetEducationLevel();
    public System.Int32 GetFailedEducationCount();
    public Unity.Mathematics.Random GetPseudoRandom(Game.Citizens.CitizenPseudoRandom reason);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetAge(Game.Citizens.CitizenAge newAge);
    public System.Void SetEducationLevel(System.Int32 level);
    public System.Void SetFailedEducationCount(System.Int32 fails);
}
```


## Fields

- `public System.UInt16 m_PseudoRandom`  

```csharp
public System.UInt16 m_PseudoRandom;
```

- `public Game.Citizens.CitizenFlags m_State`  

```csharp
public Game.Citizens.CitizenFlags m_State;
```

- `public System.Byte m_WellBeing`  

```csharp
public System.Byte m_WellBeing;
```

- `public System.Byte m_Health`  

```csharp
public System.Byte m_Health;
```

- `public System.Byte m_LeisureCounter`  

```csharp
public System.Byte m_LeisureCounter;
```

- `public System.Byte m_PenaltyCounter`  

```csharp
public System.Byte m_PenaltyCounter;
```

- `public System.Int32 m_UnemploymentCounter`  

```csharp
public System.Int32 m_UnemploymentCounter;
```

- `public System.Int16 m_BirthDay`  

```csharp
public System.Int16 m_BirthDay;
```


## Properties

- `public System.Int32 Happiness { get }`  

```csharp
public System.Int32 Happiness { get; }
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetAge() : Game.Citizens.CitizenAge`  

```csharp
public CitizenAge GetAge()
	{
		return (CitizenAge)(2 * (((m_State & CitizenFlags.AgeBit1) != CitizenFlags.None) ? 1 : 0) + (((m_State & CitizenFlags.AgeBit2) != CitizenFlags.None) ? 1 : 0));
	}
```

- `public GetAgeInDays(System.UInt32 simulationFrame, Game.Common.TimeData timeData) : System.Single`  

```csharp
public float GetAgeInDays(uint simulationFrame, TimeData timeData)
	{
		return TimeSystem.GetDay(simulationFrame, timeData) - m_BirthDay;
	}
```

- `public GetEducationLevel() : System.Int32`  

```csharp
public int GetEducationLevel()
	{
		if ((m_State & CitizenFlags.EducationBit3) != CitizenFlags.None)
		{
			return 4;
		}
		return (((m_State & CitizenFlags.EducationBit1) != CitizenFlags.None) ? 2 : 0) + (((m_State & CitizenFlags.EducationBit2) != CitizenFlags.None) ? 1 : 0);
	}
```

- `public GetFailedEducationCount() : System.Int32`  

```csharp
public int GetFailedEducationCount()
	{
		return (((m_State & CitizenFlags.FailedEducationBit1) != CitizenFlags.None) ? 2 : 0) + (((m_State & CitizenFlags.FailedEducationBit2) != CitizenFlags.None) ? 1 : 0);
	}
```

- `public GetPseudoRandom(Game.Citizens.CitizenPseudoRandom reason) : Unity.Mathematics.Random`  

```csharp
public Random GetPseudoRandom(CitizenPseudoRandom reason)
	{
		Random random = new Random((uint)((ulong)reason ^ (ulong)((m_PseudoRandom << 16) | m_PseudoRandom)));
		random.NextUInt();
		uint num = random.NextUInt();
		num = math.select(num, uint.MaxValue, num == 0);
		return new Random(num);
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetAge(Game.Citizens.CitizenAge newAge) : System.Void`  

```csharp
public void SetAge(CitizenAge newAge)
	{
		m_State = (CitizenFlags)((int)((uint)(m_State & ~(CitizenFlags.AgeBit1 | CitizenFlags.AgeBit2)) | (uint)(((newAge & CitizenAge.Adult) != CitizenAge.Child) ? 1 : 0)) | (((int)newAge % 2 != 0) ? 2 : 0));
	}
```

- `public SetEducationLevel(System.Int32 level) : System.Void`  

```csharp
public void SetEducationLevel(int level)
	{
		if (level == 4)
		{
			m_State |= CitizenFlags.EducationBit3;
		}
		else
		{
			m_State &= ~CitizenFlags.EducationBit3;
		}
		if (level >= 2)
		{
			m_State |= CitizenFlags.EducationBit1;
		}
		else
		{
			m_State &= ~CitizenFlags.EducationBit1;
		}
		if (level % 2 != 0)
		{
			m_State |= CitizenFlags.EducationBit2;
		}
		else
		{
			m_State &= ~CitizenFlags.EducationBit2;
		}
	}
```

- `public SetFailedEducationCount(System.Int32 fails) : System.Void`  

```csharp
public void SetFailedEducationCount(int fails)
	{
		if (fails >= 2)
		{
			m_State |= CitizenFlags.FailedEducationBit1;
		}
		else
		{
			m_State &= ~CitizenFlags.FailedEducationBit1;
		}
		if (fails % 2 != 0)
		{
			m_State |= CitizenFlags.FailedEducationBit2;
		}
		else
		{
			m_State &= ~CitizenFlags.FailedEducationBit2;
		}
	}
```


