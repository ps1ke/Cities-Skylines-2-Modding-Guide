# Game.Prefabs.PathfindCostInfo

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct PathfindCostInfo
{
    public System.Single m_Time;
    public System.Single m_Behaviour;
    public System.Single m_Money;
    public System.Single m_Comfort;

    public PathfindCostInfo(System.Single time, System.Single behaviour, System.Single money, System.Single comfort);

    public Game.Pathfind.PathfindCosts ToPathfindCosts();
}
```


## Fields

- `public System.Single m_Time`  

```csharp
public System.Single m_Time;
```

- `public System.Single m_Behaviour`  

```csharp
public System.Single m_Behaviour;
```

- `public System.Single m_Money`  

```csharp
public System.Single m_Money;
```

- `public System.Single m_Comfort`  

```csharp
public System.Single m_Comfort;
```


## Constructors

- `public PathfindCostInfo(System.Single time, System.Single behaviour, System.Single money, System.Single comfort)`  

```csharp
public PathfindCostInfo(float time, float behaviour, float money, float comfort)
	{
		m_Time = time;
		m_Behaviour = behaviour;
		m_Money = money;
		m_Comfort = comfort;
	}
```


## Methods

- `public ToPathfindCosts() : Game.Pathfind.PathfindCosts`  

```csharp
public PathfindCosts ToPathfindCosts()
	{
		return new PathfindCosts(m_Time, m_Behaviour, m_Money, m_Comfort);
	}
```


