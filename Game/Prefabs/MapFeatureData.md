# Game.Prefabs.MapFeatureData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct MapFeatureData : Unity.Entities.IBufferElementData
{
    public System.Single m_Cost;

    public MapFeatureData(System.Single cost);

}
```


## Fields

- `public System.Single m_Cost`  

```csharp
public System.Single m_Cost;
```


## Constructors

- `public MapFeatureData(System.Single cost)`  

```csharp
public MapFeatureData(float cost)
	{
		m_Cost = cost;
	}
```


