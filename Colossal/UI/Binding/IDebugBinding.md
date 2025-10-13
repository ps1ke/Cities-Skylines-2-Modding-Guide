# Colossal.UI.Binding.IDebugBinding

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** interface abstract public  

**Implements:** `Colossal.UI.Binding.IBinding`  

## Code

```csharp
public abstract interface IDebugBinding : Colossal.UI.Binding.IBinding
{
    public Colossal.UI.Binding.DebugBindingType debugType { get; }
    public System.String group { get; }
    public System.String name { get; }

}
```


## Properties

- `public Colossal.UI.Binding.DebugBindingType debugType { get }`  

```csharp
public Colossal.UI.Binding.DebugBindingType debugType { get; }
```

- `public System.String group { get }`  

```csharp
public System.String group { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```


