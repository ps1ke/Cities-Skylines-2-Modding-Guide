# Game.UI.InGame.TransformerSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TransformerSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <capacity>k__BackingField;
    private System.Int32 <flow>k__BackingField;
    private Game.UI.InGame.TransformerSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    private System.Int32 capacity { private get; private set; }
    private System.Int32 flow { private get; private set; }

    public TransformerSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <capacity>k__BackingField`  

```csharp
private System.Int32 <capacity>k__BackingField;
```

- `private System.Int32 <flow>k__BackingField`  

```csharp
private System.Int32 <flow>k__BackingField;
```

- `private Game.UI.InGame.TransformerSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.TransformerSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 capacity { private get; private set }`  

```csharp
private System.Int32 capacity { private get; private set; }
```

- `private System.Int32 flow { private get; private set }`  

```csharp
private System.Int32 flow { private get; private set; }
```


## Constructors

- `public TransformerSection()`  

```csharp
public TransformerSection();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
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


## Nested types

- `Game.UI.InGame.TransformerSection+TypeHandle`  

