# Game.UI.InGame.LineSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LineSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Single <length>k__BackingField;
    private System.Int32 <stops>k__BackingField;
    private System.Int32 <cargo>k__BackingField;
    private System.Single <usage>k__BackingField;

    protected System.String group { protected get; }
    private System.Single length { private get; private set; }
    private System.Int32 stops { private get; private set; }
    private System.Int32 cargo { private get; private set; }
    private System.Single usage { private get; private set; }

    public LineSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private System.Single <length>k__BackingField`  

```csharp
private System.Single <length>k__BackingField;
```

- `private System.Int32 <stops>k__BackingField`  

```csharp
private System.Int32 <stops>k__BackingField;
```

- `private System.Int32 <cargo>k__BackingField`  

```csharp
private System.Int32 <cargo>k__BackingField;
```

- `private System.Single <usage>k__BackingField`  

```csharp
private System.Single <usage>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Single length { private get; private set }`  

```csharp
private System.Single length { private get; private set; }
```

- `private System.Int32 stops { private get; private set }`  

```csharp
private System.Int32 stops { private get; private set; }
```

- `private System.Int32 cargo { private get; private set }`  

```csharp
private System.Int32 cargo { private get; private set; }
```

- `private System.Single usage { private get; private set }`  

```csharp
private System.Single usage { private get; private set; }
```


## Constructors

- `public LineSection()`  

```csharp
public LineSection();
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


