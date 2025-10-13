# Game.Prefabs.AffiliatedBrandElement

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IComparable<Game.Prefabs.AffiliatedBrandElement>`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct AffiliatedBrandElement : Unity.Entities.IBufferElementData, System.IComparable<Game.Prefabs.AffiliatedBrandElement>
{
    public Unity.Entities.Entity m_Brand;

    public System.Int32 CompareTo(Game.Prefabs.AffiliatedBrandElement other);
}
```


## Fields

- `public Unity.Entities.Entity m_Brand`  

```csharp
public Unity.Entities.Entity m_Brand;
```


## Methods

- `public CompareTo(Game.Prefabs.AffiliatedBrandElement other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Prefabs.AffiliatedBrandElement other);
```


