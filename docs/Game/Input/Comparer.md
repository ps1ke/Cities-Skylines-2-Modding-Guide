# Game.Input.Usages+Comparer

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEqualityComparer<Game.Input.Usages>`  

## Code

```csharp
public class Comparer : System.Collections.Generic.IEqualityComparer<Game.Input.Usages>
{
    public static readonly Game.Input.Usages+Comparer defaultComparer;

    public Comparer();

    public System.Boolean Equals(Game.Input.Usages x, Game.Input.Usages y);
    public System.Int32 GetHashCode(Game.Input.Usages usages);
}
```


## Fields

- `public static readonly Game.Input.Usages+Comparer defaultComparer`  

```csharp
public static readonly Game.Input.Usages+Comparer defaultComparer;
```


## Constructors

- `public Comparer()`  

```csharp
public Comparer();
```


## Methods

- `public Equals(Game.Input.Usages x, Game.Input.Usages y) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Input.Usages x, Game.Input.Usages y);
```

- `public GetHashCode(Game.Input.Usages usages) : System.Int32`  

```csharp
public System.Int32 GetHashCode(Game.Input.Usages usages);
```


