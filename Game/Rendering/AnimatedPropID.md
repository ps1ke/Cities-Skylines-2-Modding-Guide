# Game.Rendering.AnimatedPropID

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct AnimatedPropID
{
    private System.Int32 m_Index;

    public System.Boolean isValid { get; }

    public AnimatedPropID(System.Int32 index);

    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `private System.Int32 m_Index`  

```csharp
private System.Int32 m_Index;
```


## Properties

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```


## Constructors

- `public AnimatedPropID(System.Int32 index)`  

```csharp
public AnimatedPropID(int index)
	{
		m_Index = index;
	}
```


## Methods

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public override bool Equals(object obj)
	{
		if (obj is AnimatedPropID animatedPropID)
		{
			return this == animatedPropID;
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


