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
public BuildingUpgradeElement(Unity.Entities.Entity upgrade);
```


## Methods

- `public Equals(Game.Prefabs.BuildingUpgradeElement other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Prefabs.BuildingUpgradeElement other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


