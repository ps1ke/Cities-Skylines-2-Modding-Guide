# Colossal.UI.Binding.IBinding

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IBinding
{
    public System.Boolean attached { get; }

    public abstract System.Void Attach(cohtml.Net.View view);
    public abstract System.Void Detach();
}
```


## Properties

- `public System.Boolean attached { get }`  

```csharp
public System.Boolean attached { get; }
```


## Methods

- `public abstract Attach(cohtml.Net.View view) : System.Void`  

```csharp
public abstract System.Void Attach(cohtml.Net.View view);
```

- `public abstract Detach() : System.Void`  

```csharp
public abstract System.Void Detach();
```


