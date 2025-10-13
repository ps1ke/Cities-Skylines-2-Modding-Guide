# Game.Economy.ResourceIterator

**Assembly:** `Game`  
**Namespace:** `Game.Economy`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ResourceIterator
{
    public Game.Economy.Resource resource;

    public static Game.Economy.ResourceIterator GetIterator();
    public System.Boolean Next();
}
```


## Fields

- `public Game.Economy.Resource resource`  

```csharp
public Game.Economy.Resource resource;
```


## Methods

- `public static GetIterator() : Game.Economy.ResourceIterator`  

```csharp
public static ResourceIterator GetIterator()
	{
		return new ResourceIterator
		{
			resource = Resource.NoResource
		};
	}
```

- `public Next() : System.Boolean`  

```csharp
public bool Next()
	{
		resource = (Resource)Math.Max(1uL, (ulong)resource << 1);
		return resource != Resource.Last;
	}
```


