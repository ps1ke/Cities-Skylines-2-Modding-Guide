# Game.UI.InGame.PoliceSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PoliceSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <prisonerCount>k__BackingField;
    private System.Int32 <prisonerCapacity>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 prisonerCount { private get; private set; }
    private System.Int32 prisonerCapacity { private get; private set; }

    public PoliceSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <prisonerCount>k__BackingField`  

```csharp
private System.Int32 <prisonerCount>k__BackingField;
```

- `private System.Int32 <prisonerCapacity>k__BackingField`  

```csharp
private System.Int32 <prisonerCapacity>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 prisonerCount { private get; private set }`  

```csharp
private System.Int32 prisonerCount { private get; private set; }
```

- `private System.Int32 prisonerCapacity { private get; private set }`  

```csharp
private System.Int32 prisonerCapacity { private get; private set; }
```


## Constructors

- `public PoliceSection()`  

```csharp
public PoliceSection();
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


