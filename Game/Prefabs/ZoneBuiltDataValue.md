# Game.Prefabs.ZoneBuiltDataValue

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ZoneBuiltDataValue
{
    public System.Int32 m_Squares;
    public System.Int32 m_Count;

    public ZoneBuiltDataValue(System.Int32 count, System.Int32 squares);

}
```


## Fields

- `public System.Int32 m_Squares`  

```csharp
public System.Int32 m_Squares;
```

- `public System.Int32 m_Count`  

```csharp
public System.Int32 m_Count;
```


## Constructors

- `public ZoneBuiltDataValue(System.Int32 count, System.Int32 squares)`  

```csharp
public ZoneBuiltDataValue(int count, int squares)
	{
		m_Count = count;
		m_Squares = squares;
	}
```


