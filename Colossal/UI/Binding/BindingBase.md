# Colossal.UI.Binding.BindingBase

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IDebugBinding`  

## Code

```csharp
public abstract class BindingBase : Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IDebugBinding
{
    private readonly System.String <group>k__BackingField;
    private readonly System.String <name>k__BackingField;
    private readonly System.String <path>k__BackingField;
    private cohtml.Net.View <view>k__BackingField;
    protected static Colossal.Logging.ILog log;

    public System.String group { get; }
    public System.String name { get; }
    public System.String path { get; }
    public Colossal.UI.Binding.DebugBindingType debugType { get; }
    protected cohtml.Net.View view { protected get; private set; }
    public System.Boolean attached { get; }

    protected BindingBase(System.String group, System.String name);

    public virtual System.Void Attach(cohtml.Net.View view);
    public virtual System.Void Detach();
    public virtual System.String ToString();
}
```


## Fields

- `private readonly System.String <group>k__BackingField`  

```csharp
private readonly System.String <group>k__BackingField;
```

- `private readonly System.String <name>k__BackingField`  

```csharp
private readonly System.String <name>k__BackingField;
```

- `private readonly System.String <path>k__BackingField`  

```csharp
private readonly System.String <path>k__BackingField;
```

- `private cohtml.Net.View <view>k__BackingField`  

```csharp
private cohtml.Net.View <view>k__BackingField;
```

- `protected static Colossal.Logging.ILog log`  

```csharp
protected static Colossal.Logging.ILog log;
```


## Properties

- `public System.String group { get }`  

```csharp
public System.String group { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.String path { get }`  

```csharp
public System.String path { get; }
```

- `public Colossal.UI.Binding.DebugBindingType debugType { get }`  

```csharp
public Colossal.UI.Binding.DebugBindingType debugType { get; }
```

- `protected cohtml.Net.View view { protected get; private set }`  

```csharp
protected cohtml.Net.View view { protected get; private set; }
```

- `public System.Boolean attached { get }`  

```csharp
public System.Boolean attached { get; }
```


## Constructors

- `protected BindingBase(System.String group, System.String name)`  

```csharp
protected BindingBase(System.String group, System.String name);
```


## Methods

- `public virtual Attach(cohtml.Net.View view) : System.Void`  

```csharp
public virtual System.Void Attach(cohtml.Net.View view);
```

- `public virtual Detach() : System.Void`  

```csharp
public virtual System.Void Detach();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


