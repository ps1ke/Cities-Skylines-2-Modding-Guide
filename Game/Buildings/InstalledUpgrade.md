# Game.Buildings.InstalledUpgrade

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Buildings.InstalledUpgrade>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct InstalledUpgrade : Unity.Entities.IBufferElementData, System.IEquatable<Game.Buildings.InstalledUpgrade>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Upgrade;
    public System.UInt32 m_OptionMask;

    public InstalledUpgrade(Unity.Entities.Entity upgrade, System.UInt32 optionMask);

    public System.Boolean Equals(Game.Buildings.InstalledUpgrade other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Upgrade`  

```csharp
public Unity.Entities.Entity m_Upgrade;
```

- `public System.UInt32 m_OptionMask`  

```csharp
public System.UInt32 m_OptionMask;
```


## Constructors

- `public InstalledUpgrade(Unity.Entities.Entity upgrade, System.UInt32 optionMask)`  

```csharp
public InstalledUpgrade(Entity upgrade, uint optionMask)
	{
		m_Upgrade = upgrade;
		m_OptionMask = optionMask;
	}
```


## Methods

- `public Equals(Game.Buildings.InstalledUpgrade other) : System.Boolean`  

```csharp
public bool Equals(InstalledUpgrade other)
	{
		return m_Upgrade.Equals(other.m_Upgrade);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_Upgrade.GetHashCode();
	}
```


