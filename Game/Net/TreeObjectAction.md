# Game.Net.TreeObjectAction

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct TreeObjectAction
{
    public Unity.Entities.Entity m_Remove;
    public Unity.Entities.Entity m_Add;
    public Colossal.Mathematics.Bounds3 m_Bounds;

    public TreeObjectAction(Unity.Entities.Entity remove);
    public TreeObjectAction(Unity.Entities.Entity add, Colossal.Mathematics.Bounds3 bounds);
    public TreeObjectAction(Unity.Entities.Entity remove, Unity.Entities.Entity add, Colossal.Mathematics.Bounds3 bounds);

}
```


## Fields

- `public Unity.Entities.Entity m_Remove`  

```csharp
public Unity.Entities.Entity m_Remove;
```

- `public Unity.Entities.Entity m_Add`  

```csharp
public Unity.Entities.Entity m_Add;
```

- `public Colossal.Mathematics.Bounds3 m_Bounds`  

```csharp
public Colossal.Mathematics.Bounds3 m_Bounds;
```


## Constructors

- `public TreeObjectAction(Unity.Entities.Entity remove)`  

```csharp
public TreeObjectAction(Entity remove, Entity add, Bounds3 bounds)
	{
		m_Remove = remove;
		m_Add = add;
		m_Bounds = bounds;
	}
```

- `public TreeObjectAction(Unity.Entities.Entity add, Colossal.Mathematics.Bounds3 bounds)`  

```csharp
public TreeObjectAction(Entity remove, Entity add, Bounds3 bounds)
	{
		m_Remove = remove;
		m_Add = add;
		m_Bounds = bounds;
	}
```

- `public TreeObjectAction(Unity.Entities.Entity remove, Unity.Entities.Entity add, Colossal.Mathematics.Bounds3 bounds)`  

```csharp
public TreeObjectAction(Entity remove, Entity add, Bounds3 bounds)
	{
		m_Remove = remove;
		m_Add = add;
		m_Bounds = bounds;
	}
```


