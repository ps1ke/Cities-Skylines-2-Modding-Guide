# Colossal.ProgressTracker

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ProgressTracker
{
    private System.Boolean <shouldNotify>k__BackingField;
    private System.String <taskName>k__BackingField;
    private System.Single <progress>k__BackingField;
    private Colossal.ProgressTracker+Group <group>k__BackingField;

    public System.Boolean shouldNotify { get; private set; }
    public System.String taskName { get; set; }
    public System.Single progress { get; set; }
    public Colossal.ProgressTracker+Group group { get; set; }

    public ProgressTracker(System.String name, System.Boolean notify);
    public ProgressTracker(System.String name, Colossal.ProgressTracker+Group progressGroup, System.Boolean notify);

}
```


## Fields

- `private System.Boolean <shouldNotify>k__BackingField`  

```csharp
private System.Boolean <shouldNotify>k__BackingField;
```

- `private System.String <taskName>k__BackingField`  

```csharp
private System.String <taskName>k__BackingField;
```

- `private System.Single <progress>k__BackingField`  

```csharp
private System.Single <progress>k__BackingField;
```

- `private Colossal.ProgressTracker+Group <group>k__BackingField`  

```csharp
private Colossal.ProgressTracker+Group <group>k__BackingField;
```


## Properties

- `public System.Boolean shouldNotify { get; private set }`  

```csharp
public System.Boolean shouldNotify { get; private set; }
```

- `public System.String taskName { get; set }`  

```csharp
public System.String taskName { get; set; }
```

- `public System.Single progress { get; set }`  

```csharp
public System.Single progress { get; set; }
```

- `public Colossal.ProgressTracker+Group group { get; set }`  

```csharp
public Colossal.ProgressTracker+Group group { get; set; }
```


## Constructors

- `public ProgressTracker(System.String name, System.Boolean notify)`  

```csharp
public ProgressTracker(System.String name, System.Boolean notify);
```

- `public ProgressTracker(System.String name, Colossal.ProgressTracker+Group progressGroup = None, System.Boolean notify = False)`  

```csharp
public ProgressTracker(System.String name, Colossal.ProgressTracker+Group progressGroup, System.Boolean notify);
```


## Nested types

- `Colossal.ProgressTracker+Group`  

