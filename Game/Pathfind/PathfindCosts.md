# Game.Pathfind.PathfindCosts

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct PathfindCosts
{
    public Unity.Mathematics.float4 m_Value;

    public PathfindCosts(System.Single time, System.Single behaviour, System.Single money, System.Single comfort);

}
```


## Fields

- `public Unity.Mathematics.float4 m_Value`  

```csharp
public Unity.Mathematics.float4 m_Value;
```


## Constructors

- `public PathfindCosts(System.Single time, System.Single behaviour, System.Single money, System.Single comfort)`  

```csharp
public PathfindCosts(float time, float behaviour, float money, float comfort)
	{
		m_Value = new float4(time, behaviour, money, comfort);
	}
```


