# Colossal.UI.IFontSourceHandler

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IFontSourceHandler
{
    public abstract System.Void AddFontRegistry(Colossal.UI.IFontRegistry registry);
    public abstract System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.UI.IFontStreamProvider>> EnumerateFonts();
}
```


## Methods

- `public abstract AddFontRegistry(Colossal.UI.IFontRegistry registry) : System.Void`  

```csharp
public abstract System.Void AddFontRegistry(Colossal.UI.IFontRegistry registry);
```

- `public abstract EnumerateFonts() : System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.UI.IFontStreamProvider>>`  

```csharp
public abstract System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.UI.IFontStreamProvider>> EnumerateFonts();
```


