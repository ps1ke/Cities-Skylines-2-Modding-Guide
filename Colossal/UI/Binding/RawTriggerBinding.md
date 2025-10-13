# Colossal.UI.Binding.RawTriggerBinding

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.RawTriggerBindingBase`  
**Implements:** `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IDebugBinding`  

## Code

```csharp
public class RawTriggerBinding : Colossal.UI.Binding.RawTriggerBindingBase, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IDebugBinding
{
    private readonly System.Action<Colossal.UI.Binding.IJsonReader> m_Callback;

    public RawTriggerBinding(System.String group, System.String name, System.Action<Colossal.UI.Binding.IJsonReader> callback);

    protected virtual System.Void Callback();
}
```


## Fields

- `private readonly System.Action<Colossal.UI.Binding.IJsonReader> m_Callback`  

```csharp
private readonly System.Action<Colossal.UI.Binding.IJsonReader> m_Callback;
```


## Constructors

- `public RawTriggerBinding(System.String group, System.String name, System.Action<Colossal.UI.Binding.IJsonReader> callback)`  

```csharp
public RawTriggerBinding(System.String group, System.String name, System.Action<Colossal.UI.Binding.IJsonReader> callback);
```


## Methods

- `protected virtual Callback() : System.Void`  

```csharp
protected virtual System.Void Callback();
```


