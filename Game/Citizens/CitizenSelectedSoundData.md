# Game.Citizens.CitizenSelectedSoundData

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Citizens.CitizenSelectedSoundData>`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct CitizenSelectedSoundData : Unity.Entities.IBufferElementData, System.IEquatable<Game.Citizens.CitizenSelectedSoundData>
{
    public System.Boolean m_IsSickOrInjured;
    public Game.Citizens.CitizenAge m_Age;
    public Game.Citizens.CitizenHappiness m_Happiness;
    public Unity.Entities.Entity m_SelectedSound;

    public CitizenSelectedSoundData(System.Boolean isSickOrInjured, Game.Citizens.CitizenAge age, Game.Citizens.CitizenHappiness happiness, Unity.Entities.Entity selectedSound);

    public System.Boolean Equals(Game.Citizens.CitizenSelectedSoundData other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public System.Boolean m_IsSickOrInjured`  

```csharp
public System.Boolean m_IsSickOrInjured;
```

- `public Game.Citizens.CitizenAge m_Age`  

```csharp
public Game.Citizens.CitizenAge m_Age;
```

- `public Game.Citizens.CitizenHappiness m_Happiness`  

```csharp
public Game.Citizens.CitizenHappiness m_Happiness;
```

- `public Unity.Entities.Entity m_SelectedSound`  

```csharp
public Unity.Entities.Entity m_SelectedSound;
```


## Constructors

- `public CitizenSelectedSoundData(System.Boolean isSickOrInjured, Game.Citizens.CitizenAge age, Game.Citizens.CitizenHappiness happiness, Unity.Entities.Entity selectedSound)`  

```csharp
public CitizenSelectedSoundData(bool isSickOrInjured, CitizenAge age, CitizenHappiness happiness, Entity selectedSound)
	{
		m_IsSickOrInjured = isSickOrInjured;
		m_Age = age;
		m_Happiness = happiness;
		m_SelectedSound = selectedSound;
	}
```


## Methods

- `public Equals(Game.Citizens.CitizenSelectedSoundData other) : System.Boolean`  

```csharp
public bool Equals(CitizenSelectedSoundData other)
	{
		if (!m_IsSickOrInjured.Equals(other.m_IsSickOrInjured) || !m_Age.Equals(other.m_Age))
		{
			return false;
		}
		if (!m_IsSickOrInjured)
		{
			return m_Happiness.Equals(other.m_Happiness);
		}
		return true;
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return (m_IsSickOrInjured, m_Age, m_Happiness).GetHashCode();
	}
```


