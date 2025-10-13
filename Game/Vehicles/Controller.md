# Game.Vehicles.Controller

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IEmptySerializable`  

## Code

```csharp
public sealed struct Controller : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Controller;

    public Controller(Unity.Entities.Entity controller);

}
```


## Fields

- `public Unity.Entities.Entity m_Controller`  

```csharp
public Unity.Entities.Entity m_Controller;
```


## Constructors

- `public Controller(Unity.Entities.Entity controller)`  

```csharp
public Controller(Entity controller)
	{
		m_Controller = controller;
	}
```


