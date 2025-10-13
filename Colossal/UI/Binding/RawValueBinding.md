# Colossal.UI.Binding.RawValueBinding

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.RawEventBindingBase`  
**Implements:** `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IDebugBinding`, `Colossal.UI.Binding.IUpdateBinding`  

## Code

```csharp
public class RawValueBinding : Colossal.UI.Binding.RawEventBindingBase, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IDebugBinding, Colossal.UI.Binding.IUpdateBinding
{
    private readonly System.String m_PatchEventName;
    private readonly System.Action<Colossal.UI.Binding.IJsonWriter> m_WriterDelegate;

    public Colossal.UI.Binding.DebugBindingType debugType { get; }

    public RawValueBinding(System.String group, System.String name, System.Action<Colossal.UI.Binding.IJsonWriter> writerDelegate);

    protected virtual System.Void OnSubscribe();
    public Colossal.UI.Binding.IJsonWriter PatchBegin();
    public System.Void PatchEnd();
    public System.Boolean Update();
}
```


## Fields

- `private readonly System.String m_PatchEventName`  

```csharp
private readonly System.String m_PatchEventName;
```

- `private readonly System.Action<Colossal.UI.Binding.IJsonWriter> m_WriterDelegate`  

```csharp
private readonly System.Action<Colossal.UI.Binding.IJsonWriter> m_WriterDelegate;
```


## Properties

- `public Colossal.UI.Binding.DebugBindingType debugType { get }`  

```csharp
public Colossal.UI.Binding.DebugBindingType debugType { get; }
```


## Constructors

- `public RawValueBinding(System.String group, System.String name, System.Action<Colossal.UI.Binding.IJsonWriter> writerDelegate)`  

```csharp
public RawValueBinding(System.String group, System.String name, System.Action<Colossal.UI.Binding.IJsonWriter> writerDelegate);
```


## Methods

- `protected virtual OnSubscribe() : System.Void`  

```csharp
protected virtual System.Void OnSubscribe();
```

- `public PatchBegin() : Colossal.UI.Binding.IJsonWriter`  

```csharp
public Colossal.UI.Binding.IJsonWriter PatchBegin();
```

- `public PatchEnd() : System.Void`  

```csharp
public System.Void PatchEnd();
```

- `public Update() : System.Boolean`  

```csharp
public System.Boolean Update();
```


