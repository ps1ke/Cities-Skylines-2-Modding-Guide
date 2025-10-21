# Game.UI.Menu.OptionsUISystem+Page

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `DebuggerDisplay`  

## Code

```csharp
public class Page : Colossal.UI.Binding.IJsonWritable
{
    private System.Boolean <builtIn>k__BackingField;
    private System.Boolean <warning>k__BackingField;
    private System.String <id>k__BackingField;
    private System.Int32 <index>k__BackingField;
    private System.Boolean <beta>k__BackingField;
    private System.Func<System.Boolean> <warningGetter>k__BackingField;
    private readonly System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Section> <sections>k__BackingField;

    internal System.Boolean builtIn { internal get; internal set; }
    public System.Boolean warning { get; private set; }
    public System.String id { get; set; }
    public System.Int32 index { get; set; }
    public System.Boolean beta { get; set; }
    public System.Func<System.Boolean> warningGetter { get; set; }
    public System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Section> sections { get; }
    public System.Collections.ObjectModel.ReadOnlyCollection<Game.UI.Menu.OptionsUISystem+Section> visibleSections { get; }

    public Page();

    public System.Boolean UpdateNameAndDescription(System.Boolean isAdvanced);
    public System.Boolean UpdateVisibility(System.Boolean isAdvanced);
    public System.Boolean UpdateWarning(System.Boolean isAdvanced);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Boolean <builtIn>k__BackingField`  

```csharp
private System.Boolean <builtIn>k__BackingField;
```

- `private System.Boolean <warning>k__BackingField`  

```csharp
private System.Boolean <warning>k__BackingField;
```

- `private System.String <id>k__BackingField`  

```csharp
private System.String <id>k__BackingField;
```

- `private System.Int32 <index>k__BackingField`  

```csharp
private System.Int32 <index>k__BackingField;
```

- `private System.Boolean <beta>k__BackingField`  

```csharp
private System.Boolean <beta>k__BackingField;
```

- `private System.Func<System.Boolean> <warningGetter>k__BackingField`  

```csharp
private System.Func<System.Boolean> <warningGetter>k__BackingField;
```

- `private readonly System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Section> <sections>k__BackingField`  

```csharp
private readonly System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Section> <sections>k__BackingField;
```


## Properties

- `internal System.Boolean builtIn { internal get; internal set }`  

```csharp
internal System.Boolean builtIn { internal get; internal set; }
```

- `public System.Boolean warning { get; private set }`  

```csharp
public System.Boolean warning { get; private set; }
```

- `public System.String id { get; set }`  

```csharp
public System.String id { get; set; }
```

- `public System.Int32 index { get; set }`  

```csharp
public System.Int32 index { get; set; }
```

- `public System.Boolean beta { get; set }`  

```csharp
public System.Boolean beta { get; set; }
```

- `public System.Func<System.Boolean> warningGetter { get; set }`  

```csharp
public System.Func<System.Boolean> warningGetter { get; set; }
```

- `public System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Section> sections { get }`  

```csharp
public System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Section> sections { get; }
```

- `public System.Collections.ObjectModel.ReadOnlyCollection<Game.UI.Menu.OptionsUISystem+Section> visibleSections { get }`  

```csharp
public System.Collections.ObjectModel.ReadOnlyCollection<Game.UI.Menu.OptionsUISystem+Section> visibleSections { get; }
```


## Constructors

- `public Page()`  

```csharp
public Page();
```


## Methods

- `public UpdateNameAndDescription(System.Boolean isAdvanced) : System.Boolean`  

```csharp
public System.Boolean UpdateNameAndDescription(System.Boolean isAdvanced);
```

- `public UpdateVisibility(System.Boolean isAdvanced) : System.Boolean`  

```csharp
public System.Boolean UpdateVisibility(System.Boolean isAdvanced);
```

- `public UpdateWarning(System.Boolean isAdvanced) : System.Boolean`  

```csharp
public System.Boolean UpdateWarning(System.Boolean isAdvanced);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.UI.Menu.OptionsUISystem+Page+<>c`  

