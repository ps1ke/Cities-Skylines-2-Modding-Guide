# Game.Tutorials.ObjectPlacementTriggerData

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

## Code

```csharp
public sealed struct ObjectPlacementTriggerData : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Object;
    public Game.Tutorials.ObjectPlacementTriggerFlags m_Flags;

    public ObjectPlacementTriggerData(Unity.Entities.Entity obj, Game.Tutorials.ObjectPlacementTriggerFlags flags);

}
```


## Fields

- `public Unity.Entities.Entity m_Object`  

```csharp
public Unity.Entities.Entity m_Object;
```

- `public Game.Tutorials.ObjectPlacementTriggerFlags m_Flags`  

```csharp
public Game.Tutorials.ObjectPlacementTriggerFlags m_Flags;
```


## Constructors

- `public ObjectPlacementTriggerData(Unity.Entities.Entity obj, Game.Tutorials.ObjectPlacementTriggerFlags flags)`  

```csharp
public ObjectPlacementTriggerData(Entity obj, ObjectPlacementTriggerFlags flags)
	{
		m_Object = obj;
		m_Flags = flags;
	}
```


