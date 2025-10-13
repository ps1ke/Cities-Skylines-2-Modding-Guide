# Colossal.IO.AssetDatabase.IPathEscapePolicy

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IPathEscapePolicy
{
    public abstract System.String Escape(Colossal.IO.AssetDatabase.EscapeStrategy strategy, System.String input);
    public abstract System.String Unescape(System.String input);
}
```


## Methods

- `public abstract Escape(Colossal.IO.AssetDatabase.EscapeStrategy strategy, System.String input) : System.String`  

```csharp
public abstract System.String Escape(Colossal.IO.AssetDatabase.EscapeStrategy strategy, System.String input);
```

- `public abstract Unescape(System.String input) : System.String`  

```csharp
public abstract System.String Unescape(System.String input);
```


