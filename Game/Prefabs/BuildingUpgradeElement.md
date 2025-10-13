# Game.Prefabs.BuildingUpgradeElement

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Prefabs.BuildingUpgradeElement>`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct BuildingUpgradeElement : Unity.Entities.IBufferElementData, System.IEquatable<Game.Prefabs.BuildingUpgradeElement>
{
    public Unity.Entities.Entity m_Upgrade;

    public BuildingUpgradeElement(Unity.Entities.Entity upgrade);

    public System.Boolean Equals(Game.Prefabs.BuildingUpgradeElement other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Upgrade`  

```csharp
public Unity.Entities.Entity m_Upgrade;
```


## Constructors

- `public BuildingUpgradeElement(Unity.Entities.Entity upgrade)`  

```csharp
public BuildingUpgradeElement(Entity upgrade)
	{
		m_Upgrade = upgrade;
	}
```


## Methods

- `public Equals(Game.Prefabs.BuildingUpgradeElement other) : System.Boolean`  

```csharp
public bool Equals(BuildingUpgradeElement other)
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


