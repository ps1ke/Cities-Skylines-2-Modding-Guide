# Game.UI.Widgets.FlexLayout

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct FlexLayout : Colossal.UI.Binding.IJsonWritable
{
    private System.Single <grow>k__BackingField;
    private System.Single <shrink>k__BackingField;
    private System.Int32 <basis>k__BackingField;

    public static Game.UI.Widgets.FlexLayout Default { get; }
    public static Game.UI.Widgets.FlexLayout Fill { get; }
    public System.Single grow { get; set; }
    public System.Single shrink { get; set; }
    public System.Int32 basis { get; set; }

    public FlexLayout(System.Single grow, System.Single shrink, System.Int32 basis);

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Single <grow>k__BackingField`  

```csharp
private System.Single <grow>k__BackingField;
```

- `private System.Single <shrink>k__BackingField`  

```csharp
private System.Single <shrink>k__BackingField;
```

- `private System.Int32 <basis>k__BackingField`  

```csharp
private System.Int32 <basis>k__BackingField;
```


## Properties

- `public static Game.UI.Widgets.FlexLayout Default { get }`  

```csharp
public static Game.UI.Widgets.FlexLayout Default { get; }
```

- `public static Game.UI.Widgets.FlexLayout Fill { get }`  

```csharp
public static Game.UI.Widgets.FlexLayout Fill { get; }
```

- `public System.Single grow { get; set }`  

```csharp
public System.Single grow { get; set; }
```

- `public System.Single shrink { get; set }`  

```csharp
public System.Single shrink { get; set; }
```

- `public System.Int32 basis { get; set }`  

```csharp
public System.Int32 basis { get; set; }
```


## Constructors

- `public FlexLayout(System.Single grow, System.Single shrink, System.Int32 basis)`  

```csharp
public FlexLayout(System.Single grow, System.Single shrink, System.Int32 basis);
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


