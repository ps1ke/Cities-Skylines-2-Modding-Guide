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
public CitizenSelectedSoundData(System.Boolean isSickOrInjured, Game.Citizens.CitizenAge age, Game.Citizens.CitizenHappiness happiness, Unity.Entities.Entity selectedSound);
```


## Methods

- `public Equals(Game.Citizens.CitizenSelectedSoundData other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Citizens.CitizenSelectedSoundData other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


