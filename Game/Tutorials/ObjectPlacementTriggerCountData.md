# Game.Tutorials.ObjectPlacementTriggerCountData

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct ObjectPlacementTriggerCountData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public System.Int32 m_RequiredCount;
    public System.Int32 m_Count;

    public ObjectPlacementTriggerCountData(System.Int32 requiredCount);

}
```


## Fields

- `public System.Int32 m_RequiredCount`  

```csharp
public System.Int32 m_RequiredCount;
```

- `public System.Int32 m_Count`  

```csharp
public System.Int32 m_Count;
```


## Constructors

- `public ObjectPlacementTriggerCountData(System.Int32 requiredCount)`  

```csharp
public ObjectPlacementTriggerCountData(int requiredCount)
	{
		m_RequiredCount = requiredCount;
		m_Count = 0;
	}
```


