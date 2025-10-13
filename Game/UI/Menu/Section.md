# Game.UI.Menu.OptionsUISystem+Section

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `DebuggerDisplay`  

## Code

```csharp
public class Section : Colossal.UI.Binding.IJsonWritable
{
    private readonly Game.UI.Menu.OptionsUISystem+Page <page>k__BackingField;
    private System.String <id>k__BackingField;
    private System.Int32 <index>k__BackingField;
    private System.Boolean <warning>k__BackingField;
    private System.Func<System.Boolean> <warningGetter>k__BackingField;
    private readonly System.String[] <groupNames>k__BackingField;
    private readonly System.Collections.Generic.HashSet<System.String> <groupToShowName>k__BackingField;
    private System.Collections.Generic.Dictionary<System.Int32, System.Boolean> <groupVisible>k__BackingField;
    private System.Collections.Generic.Dictionary<System.Int32, System.Boolean> <prevGroupVisible>k__BackingField;
    private readonly System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Option> <options>k__BackingField;
    private System.Boolean <isVisible>k__BackingField;

    public Game.UI.Menu.OptionsUISystem+Page page { get; }
    public System.String id { get; set; }
    public System.Int32 index { get; set; }
    public System.Boolean warning { get; private set; }
    public System.Func<System.Boolean> warningGetter { get; set; }
    public System.String[] groupNames { get; }
    public System.Collections.Generic.HashSet<System.String> groupToShowName { get; }
    private System.Collections.Generic.Dictionary<System.Int32, System.Boolean> groupVisible { private get; private set; }
    private System.Collections.Generic.Dictionary<System.Int32, System.Boolean> prevGroupVisible { private get; private set; }
    public System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Option> options { get; }
    public System.Boolean isVisible { get; private set; }

    public Section(System.String id, Game.UI.Menu.OptionsUISystem+Page page, Game.UI.Menu.AutomaticSettings+SettingPageData pageData);

    public System.Collections.Generic.List<Game.UI.Widgets.IWidget> GetItems(System.Boolean isAdvanced);
    public System.Boolean UpdateNameAndDescription(System.Boolean isAdvanced);
    public System.Boolean UpdateVisibility(System.Boolean isAdvanced);
    public System.Boolean UpdateWarning(System.Boolean isAdvanced);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly Game.UI.Menu.OptionsUISystem+Page <page>k__BackingField`  

```csharp
private readonly Game.UI.Menu.OptionsUISystem+Page <page>k__BackingField;
```

- `private System.String <id>k__BackingField`  

```csharp
private System.String <id>k__BackingField;
```

- `private System.Int32 <index>k__BackingField`  

```csharp
private System.Int32 <index>k__BackingField;
```

- `private System.Boolean <warning>k__BackingField`  

```csharp
private System.Boolean <warning>k__BackingField;
```

- `private System.Func<System.Boolean> <warningGetter>k__BackingField`  

```csharp
private System.Func<System.Boolean> <warningGetter>k__BackingField;
```

- `private readonly System.String[] <groupNames>k__BackingField`  

```csharp
private readonly System.String[] <groupNames>k__BackingField;
```

- `private readonly System.Collections.Generic.HashSet<System.String> <groupToShowName>k__BackingField`  

```csharp
private readonly System.Collections.Generic.HashSet<System.String> <groupToShowName>k__BackingField;
```

- `private System.Collections.Generic.Dictionary<System.Int32, System.Boolean> <groupVisible>k__BackingField`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, System.Boolean> <groupVisible>k__BackingField;
```

- `private System.Collections.Generic.Dictionary<System.Int32, System.Boolean> <prevGroupVisible>k__BackingField`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, System.Boolean> <prevGroupVisible>k__BackingField;
```

- `private readonly System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Option> <options>k__BackingField`  

```csharp
private readonly System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Option> <options>k__BackingField;
```

- `private System.Boolean <isVisible>k__BackingField`  

```csharp
private System.Boolean <isVisible>k__BackingField;
```


## Properties

- `public Game.UI.Menu.OptionsUISystem+Page page { get }`  

```csharp
public Game.UI.Menu.OptionsUISystem+Page page { get; }
```

- `public System.String id { get; set }`  

```csharp
public System.String id { get; set; }
```

- `public System.Int32 index { get; set }`  

```csharp
public System.Int32 index { get; set; }
```

- `public System.Boolean warning { get; private set }`  

```csharp
public System.Boolean warning { get; private set; }
```

- `public System.Func<System.Boolean> warningGetter { get; set }`  

```csharp
public System.Func<System.Boolean> warningGetter { get; set; }
```

- `public System.String[] groupNames { get }`  

```csharp
public System.String[] groupNames { get; }
```

- `public System.Collections.Generic.HashSet<System.String> groupToShowName { get }`  

```csharp
public System.Collections.Generic.HashSet<System.String> groupToShowName { get; }
```

- `private System.Collections.Generic.Dictionary<System.Int32, System.Boolean> groupVisible { private get; private set }`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, System.Boolean> groupVisible { private get; private set; }
```

- `private System.Collections.Generic.Dictionary<System.Int32, System.Boolean> prevGroupVisible { private get; private set }`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, System.Boolean> prevGroupVisible { private get; private set; }
```

- `public System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Option> options { get }`  

```csharp
public System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Option> options { get; }
```

- `public System.Boolean isVisible { get; private set }`  

```csharp
public System.Boolean isVisible { get; private set; }
```


## Constructors

- `public Section(System.String id, Game.UI.Menu.OptionsUISystem+Page page, Game.UI.Menu.AutomaticSettings+SettingPageData pageData)`  

```csharp
public Section(System.String id, Game.UI.Menu.OptionsUISystem+Page page, Game.UI.Menu.AutomaticSettings+SettingPageData pageData);
```


## Methods

- `public GetItems(System.Boolean isAdvanced) : System.Collections.Generic.List<Game.UI.Widgets.IWidget>`  

```csharp
public System.Collections.Generic.List<Game.UI.Widgets.IWidget> GetItems(System.Boolean isAdvanced);
```

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

- `Game.UI.Menu.OptionsUISystem+Section+<>c`  
- `Game.UI.Menu.OptionsUISystem+Section+<>c__DisplayClass43_0`  
- `Game.UI.Menu.OptionsUISystem+Section+<>c__DisplayClass44_0`  

