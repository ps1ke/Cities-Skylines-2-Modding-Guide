# Colossal.UI.Binding.RawEventBinding

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.RawEventBindingBase`  
**Implements:** `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IDebugBinding`  

## Code

```csharp
public class RawEventBinding : Colossal.UI.Binding.RawEventBindingBase, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IDebugBinding
{
    public RawEventBinding(System.String group, System.String name);

    public Colossal.UI.Binding.IJsonWriter EventBegin();
    public System.Void EventEnd();
}
```


## Constructors

- `public RawEventBinding(System.String group, System.String name)`  

```csharp
public RawEventBinding(System.String group, System.String name);
```


## Methods

- `public EventBegin() : Colossal.UI.Binding.IJsonWriter`  

```csharp
public Colossal.UI.Binding.IJsonWriter EventBegin();
```

- `public EventEnd() : System.Void`  

```csharp
public System.Void EventEnd();
```


