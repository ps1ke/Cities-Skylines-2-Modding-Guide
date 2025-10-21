# Game.UI.InGame.RoadSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RoadSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Single <length>k__BackingField;
    private System.Single <bestCondition>k__BackingField;
    private System.Single <worstCondition>k__BackingField;
    private System.Single <condition>k__BackingField;
    private System.Single <upkeep>k__BackingField;
    private System.Single[] m_Volume;
    private System.Single[] m_Flow;

    protected System.String group { protected get; }
    private System.Single length { private get; private set; }
    private System.Single bestCondition { private get; private set; }
    private System.Single worstCondition { private get; private set; }
    private System.Single condition { private get; private set; }
    private System.Single upkeep { private get; private set; }

    public RoadSection();

    protected virtual System.Void OnCreate();
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

- `private System.Single <bestCondition>k__BackingField`  

```csharp
private System.Single <bestCondition>k__BackingField;
```

- `private System.Single <worstCondition>k__BackingField`  

```csharp
private System.Single <worstCondition>k__BackingField;
```

- `private System.Single <condition>k__BackingField`  

```csharp
private System.Single <condition>k__BackingField;
```

- `private System.Single <upkeep>k__BackingField`  

```csharp
private System.Single <upkeep>k__BackingField;
```

- `private System.Single[] m_Volume`  

```csharp
private System.Single[] m_Volume;
```

- `private System.Single[] m_Flow`  

```csharp
private System.Single[] m_Flow;
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

- `private System.Single bestCondition { private get; private set }`  

```csharp
private System.Single bestCondition { private get; private set; }
```

- `private System.Single worstCondition { private get; private set }`  

```csharp
private System.Single worstCondition { private get; private set; }
```

- `private System.Single condition { private get; private set }`  

```csharp
private System.Single condition { private get; private set; }
```

- `private System.Single upkeep { private get; private set }`  

```csharp
private System.Single upkeep { private get; private set; }
```


## Constructors

- `public RoadSection()`  

```csharp
public RoadSection();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
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


