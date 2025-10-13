# Colossal.UI.Fatal.IFileStreamProvider

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI.Fatal`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IFileStreamProvider
{
    public System.String name { get; }

    public abstract Colossal.UI.IFontStreamProvider GetFontStreamProvider();
    public abstract System.IO.Stream OpenRead();
}
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```


## Methods

- `public abstract GetFontStreamProvider() : Colossal.UI.IFontStreamProvider`  

```csharp
public abstract Colossal.UI.IFontStreamProvider GetFontStreamProvider();
```

- `public abstract OpenRead() : System.IO.Stream`  

```csharp
public abstract System.IO.Stream OpenRead();
```


