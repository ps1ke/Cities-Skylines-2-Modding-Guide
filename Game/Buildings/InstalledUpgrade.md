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
public InstalledUpgrade(Unity.Entities.Entity upgrade, System.UInt32 optionMask);
```


## Methods

- `public Equals(Game.Buildings.InstalledUpgrade other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Buildings.InstalledUpgrade other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


