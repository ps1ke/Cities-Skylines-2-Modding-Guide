# Game.UI.InGame.FireSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FireSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Single <vehicleEfficiency>k__BackingField;
    private System.Boolean <disasterResponder>k__BackingField;

    protected System.String group { protected get; }
    private System.Single vehicleEfficiency { private get; private set; }
    private System.Boolean disasterResponder { private get; private set; }

    public FireSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Single <vehicleEfficiency>k__BackingField`  

```csharp
private System.Single <vehicleEfficiency>k__BackingField;
```

- `private System.Boolean <disasterResponder>k__BackingField`  

```csharp
private System.Boolean <disasterResponder>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Single vehicleEfficiency { private get; private set }`  

```csharp
private System.Single vehicleEfficiency { private get; private set; }
```

- `private System.Boolean disasterResponder { private get; private set }`  

```csharp
private System.Boolean disasterResponder { private get; private set; }
```


## Constructors

- `public FireSection()`  

```csharp
public FireSection();
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```

- `protected virtual Reset() : System.Void`  

```csharp
protected virtual System.Void Reset();
```

- `private Visible() : System.Boolean`  

```csharp
private System.Boolean Visible();
```


