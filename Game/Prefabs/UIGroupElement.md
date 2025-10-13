# Game.Prefabs.UIGroupElement

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct UIGroupElement : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Prefab;

    public UIGroupElement(Unity.Entities.Entity prefab);

}
```


## Fields

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```


## Constructors

- `public UIGroupElement(Unity.Entities.Entity prefab)`  

```csharp
public UIGroupElement(Entity prefab)
	{
		m_Prefab = prefab;
	}
```


