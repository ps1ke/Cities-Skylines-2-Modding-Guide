# Game.UI.InGame.GarbageSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GarbageSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <garbage>k__BackingField;
    private System.Int32 <garbageCapacity>k__BackingField;
    private System.Int32 <processingSpeed>k__BackingField;
    private System.Int32 <processingCapacity>k__BackingField;
    private Game.UI.InGame.GarbageSection+LoadKey <loadKey>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 garbage { private get; private set; }
    private System.Int32 garbageCapacity { private get; private set; }
    private System.Int32 processingSpeed { private get; private set; }
    private System.Int32 processingCapacity { private get; private set; }
    private Game.UI.InGame.GarbageSection+LoadKey loadKey { private get; private set; }

    public GarbageSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <garbage>k__BackingField`  

```csharp
private System.Int32 <garbage>k__BackingField;
```

- `private System.Int32 <garbageCapacity>k__BackingField`  

```csharp
private System.Int32 <garbageCapacity>k__BackingField;
```

- `private System.Int32 <processingSpeed>k__BackingField`  

```csharp
private System.Int32 <processingSpeed>k__BackingField;
```

- `private System.Int32 <processingCapacity>k__BackingField`  

```csharp
private System.Int32 <processingCapacity>k__BackingField;
```

- `private Game.UI.InGame.GarbageSection+LoadKey <loadKey>k__BackingField`  

```csharp
private Game.UI.InGame.GarbageSection+LoadKey <loadKey>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 garbage { private get; private set }`  

```csharp
private System.Int32 garbage { private get; private set; }
```

- `private System.Int32 garbageCapacity { private get; private set }`  

```csharp
private System.Int32 garbageCapacity { private get; private set; }
```

- `private System.Int32 processingSpeed { private get; private set }`  

```csharp
private System.Int32 processingSpeed { private get; private set; }
```

- `private System.Int32 processingCapacity { private get; private set }`  

```csharp
private System.Int32 processingCapacity { private get; private set; }
```

- `private Game.UI.InGame.GarbageSection+LoadKey loadKey { private get; private set }`  

```csharp
private Game.UI.InGame.GarbageSection+LoadKey loadKey { private get; private set; }
```


## Constructors

- `public GarbageSection()`  

```csharp
public GarbageSection();
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


## Nested types

- `Game.UI.InGame.GarbageSection+LoadKey`  

