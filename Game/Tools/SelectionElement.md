# Game.Tools.SelectionElement

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct SelectionElement : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Entity;

    public SelectionElement(Unity.Entities.Entity entity);

}
```


## Fields

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```


## Constructors

- `public SelectionElement(Unity.Entities.Entity entity)`  

```csharp
public SelectionElement(Entity entity)
	{
		m_Entity = entity;
	}
```


