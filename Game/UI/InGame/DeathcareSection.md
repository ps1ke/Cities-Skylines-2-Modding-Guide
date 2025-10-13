# Game.UI.InGame.DeathcareSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DeathcareSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <bodyCount>k__BackingField;
    private System.Int32 <bodyCapacity>k__BackingField;
    private System.Single <processingSpeed>k__BackingField;
    private System.Single <processingCapacity>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 bodyCount { private get; private set; }
    private System.Int32 bodyCapacity { private get; private set; }
    private System.Single processingSpeed { private get; private set; }
    private System.Single processingCapacity { private get; private set; }

    public DeathcareSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <bodyCount>k__BackingField`  

```csharp
private System.Int32 <bodyCount>k__BackingField;
```

- `private System.Int32 <bodyCapacity>k__BackingField`  

```csharp
private System.Int32 <bodyCapacity>k__BackingField;
```

- `private System.Single <processingSpeed>k__BackingField`  

```csharp
private System.Single <processingSpeed>k__BackingField;
```

- `private System.Single <processingCapacity>k__BackingField`  

```csharp
private System.Single <processingCapacity>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 bodyCount { private get; private set }`  

```csharp
private System.Int32 bodyCount { private get; private set; }
```

- `private System.Int32 bodyCapacity { private get; private set }`  

```csharp
private System.Int32 bodyCapacity { private get; private set; }
```

- `private System.Single processingSpeed { private get; private set }`  

```csharp
private System.Single processingSpeed { private get; private set; }
```

- `private System.Single processingCapacity { private get; private set }`  

```csharp
private System.Single processingCapacity { private get; private set; }
```


## Constructors

- `public DeathcareSection()`  

```csharp
public DeathcareSection();
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


