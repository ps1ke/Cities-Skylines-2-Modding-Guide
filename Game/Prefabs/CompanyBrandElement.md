# Game.Prefabs.CompanyBrandElement

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct CompanyBrandElement : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Brand;

    public CompanyBrandElement(Unity.Entities.Entity brand);

}
```


## Fields

- `public Unity.Entities.Entity m_Brand`  

```csharp
public Unity.Entities.Entity m_Brand;
```


## Constructors

- `public CompanyBrandElement(Unity.Entities.Entity brand)`  

```csharp
public CompanyBrandElement(Entity brand)
	{
		m_Brand = brand;
	}
```


