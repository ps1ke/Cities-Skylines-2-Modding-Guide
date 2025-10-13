# Game.Simulation.HandleRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct HandleRequest : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Request;
    public Unity.Entities.Entity m_Handler;
    public System.Boolean m_Completed;
    public System.Boolean m_PathConsumed;

    public HandleRequest(Unity.Entities.Entity request, Unity.Entities.Entity handler, System.Boolean completed, System.Boolean pathConsumed);

}
```


## Fields

- `public Unity.Entities.Entity m_Request`  

```csharp
public Unity.Entities.Entity m_Request;
```

- `public Unity.Entities.Entity m_Handler`  

```csharp
public Unity.Entities.Entity m_Handler;
```

- `public System.Boolean m_Completed`  

```csharp
public System.Boolean m_Completed;
```

- `public System.Boolean m_PathConsumed`  

```csharp
public System.Boolean m_PathConsumed;
```


## Constructors

- `public HandleRequest(Unity.Entities.Entity request, Unity.Entities.Entity handler, System.Boolean completed, System.Boolean pathConsumed = False)`  

```csharp
public HandleRequest(Entity request, Entity handler, bool completed, bool pathConsumed = false)
	{
		m_Request = request;
		m_Handler = handler;
		m_Completed = completed;
		m_PathConsumed = pathConsumed;
	}
```


