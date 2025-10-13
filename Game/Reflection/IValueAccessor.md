# Game.Reflection.IValueAccessor

**Assembly:** `Game`  
**Namespace:** `Game.Reflection`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IValueAccessor
{
    public System.Type valueType { get; }

    public abstract System.Object GetValue();
    public abstract System.Void SetValue(System.Object value);
}
```


## Properties

- `public System.Type valueType { get }`  

```csharp
public System.Type valueType { get; }
```


## Methods

- `public abstract GetValue() : System.Object`  

```csharp
public abstract System.Object GetValue();
```

- `public abstract SetValue(System.Object value) : System.Void`  

```csharp
public abstract System.Void SetValue(System.Object value);
```


