# Game.UI.InGame.HealthcareSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HealthcareSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <patientCount>k__BackingField;
    private System.Int32 <patientCapacity>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 patientCount { private get; private set; }
    private System.Int32 patientCapacity { private get; private set; }

    public HealthcareSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private System.Int32 <patientCount>k__BackingField`  

```csharp
private System.Int32 <patientCount>k__BackingField;
```

- `private System.Int32 <patientCapacity>k__BackingField`  

```csharp
private System.Int32 <patientCapacity>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 patientCount { private get; private set }`  

```csharp
private System.Int32 patientCount { private get; private set; }
```

- `private System.Int32 patientCapacity { private get; private set }`  

```csharp
private System.Int32 patientCapacity { private get; private set; }
```


## Constructors

- `public HealthcareSection()`  

```csharp
public HealthcareSection();
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


