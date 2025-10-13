# Game.Objects.Damage

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct Damage : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Object;
    public Unity.Mathematics.float3 m_Delta;

    public Damage(Unity.Entities.Entity _object, Unity.Mathematics.float3 delta);

}
```


## Fields

- `public Unity.Entities.Entity m_Object`  

```csharp
public Unity.Entities.Entity m_Object;
```

- `public Unity.Mathematics.float3 m_Delta`  

```csharp
public Unity.Mathematics.float3 m_Delta;
```


## Constructors

- `public Damage(Unity.Entities.Entity _object, Unity.Mathematics.float3 delta)`  

```csharp
public Damage(Entity _object, float3 delta)
	{
		m_Object = _object;
		m_Delta = delta;
	}
```


