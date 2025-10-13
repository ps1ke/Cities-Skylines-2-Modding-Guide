# Game.Simulation.RequestGroup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct RequestGroup : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public System.UInt32 m_GroupCount;

    public RequestGroup(System.UInt32 groupCount);

}
```


## Fields

- `public System.UInt32 m_GroupCount`  

```csharp
public System.UInt32 m_GroupCount;
```


## Constructors

- `public RequestGroup(System.UInt32 groupCount)`  

```csharp
public RequestGroup(uint groupCount)
	{
		m_GroupCount = groupCount;
	}
```


