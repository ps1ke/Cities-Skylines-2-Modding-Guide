# Game.UI.InGame.SewageSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SewageSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Single <capacity>k__BackingField;
    private System.Single <lastProcessed>k__BackingField;
    private System.Single <lastPurified>k__BackingField;
    private System.Single <purification>k__BackingField;

    protected System.String group { protected get; }
    private System.Single capacity { private get; private set; }
    private System.Single lastProcessed { private get; private set; }
    private System.Single lastPurified { private get; private set; }
    private System.Single purification { private get; private set; }

    public SewageSection();

    private System.Boolean HasWaterSource();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Single <capacity>k__BackingField`  

```csharp
private System.Single <capacity>k__BackingField;
```

- `private System.Single <lastProcessed>k__BackingField`  

```csharp
private System.Single <lastProcessed>k__BackingField;
```

- `private System.Single <lastPurified>k__BackingField`  

```csharp
private System.Single <lastPurified>k__BackingField;
```

- `private System.Single <purification>k__BackingField`  

```csharp
private System.Single <purification>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Single capacity { private get; private set }`  

```csharp
private System.Single capacity { private get; private set; }
```

- `private System.Single lastProcessed { private get; private set }`  

```csharp
private System.Single lastProcessed { private get; private set; }
```

- `private System.Single lastPurified { private get; private set }`  

```csharp
private System.Single lastPurified { private get; private set; }
```

- `private System.Single purification { private get; private set }`  

```csharp
private System.Single purification { private get; private set; }
```


## Constructors

- `public SewageSection()`  

```csharp
public SewageSection();
```


## Methods

- `private HasWaterSource() : System.Boolean`  

```csharp
private System.Boolean HasWaterSource();
```

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


