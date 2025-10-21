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
public static Game.Economy.ResourceIterator GetIterator();
```

- `public Next() : System.Boolean`  

```csharp
public System.Boolean Next();
```


