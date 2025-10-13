# Game.Common.GroupBuilder`1+Result

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Common.GroupBuilder<T>>`  

## Code

```csharp
public sealed struct Result<T> : System.IComparable<Game.Common.GroupBuilder<T>>
{
    public T m_Item;
    public System.Int32 m_Group;

    public Result(T item, System.Int32 group);

    public System.Int32 CompareTo(Game.Common.GroupBuilder<T> other);
}
```


## Fields

- `public T m_Item`  

```csharp
public T m_Item;
```

- `public System.Int32 m_Group`  

```csharp
public System.Int32 m_Group;
```


## Constructors

- `public Result(T item, System.Int32 group)`  

```csharp
public Result(T item, System.Int32 group);
```


## Methods

- `public CompareTo(Game.Common.GroupBuilder<T> other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Common.GroupBuilder<T> other);
```


