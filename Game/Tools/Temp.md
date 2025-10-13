# Game.Tools.Temp

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct Temp : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Original;
    public System.Single m_CurvePosition;
    public System.Int32 m_Value;
    public System.Int32 m_Cost;
    public Game.Tools.TempFlags m_Flags;

    public Temp(Unity.Entities.Entity original, Game.Tools.TempFlags flags);

}
```


## Fields

- `public Unity.Entities.Entity m_Original`  

```csharp
public Unity.Entities.Entity m_Original;
```

- `public System.Single m_CurvePosition`  

```csharp
public System.Single m_CurvePosition;
```

- `public System.Int32 m_Value`  

```csharp
public System.Int32 m_Value;
```

- `public System.Int32 m_Cost`  

```csharp
public System.Int32 m_Cost;
```

- `public Game.Tools.TempFlags m_Flags`  

```csharp
public Game.Tools.TempFlags m_Flags;
```


## Constructors

- `public Temp(Unity.Entities.Entity original, Game.Tools.TempFlags flags)`  

```csharp
public Temp(Entity original, TempFlags flags)
	{
		m_Original = original;
		m_CurvePosition = 0f;
		m_Value = 0;
		m_Cost = 0;
		m_Flags = flags;
	}
```


