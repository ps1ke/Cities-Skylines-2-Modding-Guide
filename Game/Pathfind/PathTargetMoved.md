# Game.Pathfind.PathTargetMoved

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct PathTargetMoved : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Target;
    public Unity.Mathematics.float3 m_OldLocation;
    public Unity.Mathematics.float3 m_NewLocation;

    public PathTargetMoved(Unity.Entities.Entity target, Unity.Mathematics.float3 oldLocation, Unity.Mathematics.float3 newLocation);

}
```


## Fields

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
```

- `public Unity.Mathematics.float3 m_OldLocation`  

```csharp
public Unity.Mathematics.float3 m_OldLocation;
```

- `public Unity.Mathematics.float3 m_NewLocation`  

```csharp
public Unity.Mathematics.float3 m_NewLocation;
```


## Constructors

- `public PathTargetMoved(Unity.Entities.Entity target, Unity.Mathematics.float3 oldLocation, Unity.Mathematics.float3 newLocation)`  

```csharp
public PathTargetMoved(Entity target, float3 oldLocation, float3 newLocation)
	{
		m_Target = target;
		m_OldLocation = oldLocation;
		m_NewLocation = newLocation;
	}
```


