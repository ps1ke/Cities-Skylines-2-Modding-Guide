# Game.Rendering.ColorGroupID

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ColorGroupID
{
    private System.Int32 m_Index;

    public ColorGroupID(System.Int32 index);

    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `private System.Int32 m_Index`  

```csharp
private System.Int32 m_Index;
```


## Constructors

- `public ColorGroupID(System.Int32 index)`  

```csharp
public ColorGroupID(int index)
	{
		m_Index = index;
	}
```


## Methods

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (obj is ColorGroupID colorGroupID)
		{
			return this == colorGroupID;
		}
		return false;
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_Index.GetHashCode();
	}
```


