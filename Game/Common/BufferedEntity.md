# Game.Common.BufferedEntity

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct BufferedEntity
{
    public Unity.Entities.Entity m_Value;
    public System.Boolean m_Stored;

    public BufferedEntity(Unity.Entities.Entity value, System.Boolean stored);

    public virtual System.String ToString();
}
```


## Fields

- `public Unity.Entities.Entity m_Value`  

```csharp
public Unity.Entities.Entity m_Value;
```

- `public System.Boolean m_Stored`  

```csharp
public System.Boolean m_Stored;
```


## Constructors

- `public BufferedEntity(Unity.Entities.Entity value, System.Boolean stored)`  

```csharp
public BufferedEntity(Entity value, bool stored)
	{
		m_Value = value;
		m_Stored = stored;
	}
```


## Methods

- `public virtual ToString() : System.String`  

```csharp
public override string ToString()
	{
		return string.Format("{0}: {1}, {2}: {3}", "m_Value", m_Value, "m_Stored", m_Stored);
	}
```


