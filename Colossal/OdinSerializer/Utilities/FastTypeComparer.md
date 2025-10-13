# Colossal.OdinSerializer.Utilities.FastTypeComparer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEqualityComparer<System.Type>`  

## Code

```csharp
public class FastTypeComparer : System.Collections.Generic.IEqualityComparer<System.Type>
{
    public static readonly Colossal.OdinSerializer.Utilities.FastTypeComparer Instance;

    public FastTypeComparer();

    public System.Boolean Equals(System.Type x, System.Type y);
    public System.Int32 GetHashCode(System.Type obj);
}
```


## Fields

- `public static readonly Colossal.OdinSerializer.Utilities.FastTypeComparer Instance`  

```csharp
public static readonly Colossal.OdinSerializer.Utilities.FastTypeComparer Instance;
```


## Constructors

- `public FastTypeComparer()`  

```csharp
public FastTypeComparer();
```


## Methods

- `public Equals(System.Type x, System.Type y) : System.Boolean`  

```csharp
public System.Boolean Equals(System.Type x, System.Type y);
```

- `public GetHashCode(System.Type obj) : System.Int32`  

```csharp
public System.Int32 GetHashCode(System.Type obj);
```


