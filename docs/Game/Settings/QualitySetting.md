# Game.Settings.QualitySetting

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class abstract public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

## Code

```csharp
public abstract class QualitySetting : Game.Settings.Setting, System.IEquatable<Game.Settings.Setting>
{
    private System.Boolean <disableSetting>k__BackingField;

    public System.Boolean disableSetting { get; set; }

    protected QualitySetting();

    internal virtual System.Void AddToPageData(Game.UI.Menu.AutomaticSettings+SettingPageData pageData);
    public abstract System.Collections.Generic.IEnumerable<Game.Settings.QualitySetting+Level> EnumerateAvailableLevels();
    public abstract Game.Settings.QualitySetting+Level GetLevel();
    public abstract System.String GetMockName(Game.Settings.QualitySetting+Level level);
    public Game.UI.Widgets.DropdownItem<System.Int32>[] GetQualityValues();
    public virtual System.Boolean IsOptionFullyDisabled();
    public virtual System.Boolean IsOptionsDisabled();
    public virtual System.Void SetDefaults();
    public abstract System.Void SetLevel(Game.Settings.QualitySetting+Level quality, System.Boolean apply);
    public abstract System.Void TransferValuesFrom(Game.Settings.QualitySetting setting);
}
```


## Fields

- `private System.Boolean <disableSetting>k__BackingField`  

```csharp
private System.Boolean <disableSetting>k__BackingField;
```


## Properties

- `public System.Boolean disableSetting { get; set }`  

```csharp
public System.Boolean disableSetting { get; set; }
```


## Constructors

- `protected QualitySetting()`  

```csharp
protected QualitySetting();
```


## Methods

- `internal virtual AddToPageData(Game.UI.Menu.AutomaticSettings+SettingPageData pageData) : System.Void`  

```csharp
internal virtual System.Void AddToPageData(Game.UI.Menu.AutomaticSettings+SettingPageData pageData);
```

- `public abstract EnumerateAvailableLevels() : System.Collections.Generic.IEnumerable<Game.Settings.QualitySetting+Level>`  

```csharp
public abstract System.Collections.Generic.IEnumerable<Game.Settings.QualitySetting+Level> EnumerateAvailableLevels();
```

- `public abstract GetLevel() : Game.Settings.QualitySetting+Level`  

```csharp
public abstract Game.Settings.QualitySetting+Level GetLevel();
```

- `public abstract GetMockName(Game.Settings.QualitySetting+Level level) : System.String`  

```csharp
public abstract System.String GetMockName(Game.Settings.QualitySetting+Level level);
```

- `public GetQualityValues() : Game.UI.Widgets.DropdownItem<System.Int32>[]`  

```csharp
public Game.UI.Widgets.DropdownItem<System.Int32>[] GetQualityValues();
```

- `public virtual IsOptionFullyDisabled() : System.Boolean`  

```csharp
public virtual System.Boolean IsOptionFullyDisabled();
```

- `public virtual IsOptionsDisabled() : System.Boolean`  

```csharp
public virtual System.Boolean IsOptionsDisabled();
```

- `public virtual SetDefaults() : System.Void`  

```csharp
public virtual System.Void SetDefaults();
```

- `public abstract SetLevel(Game.Settings.QualitySetting+Level quality, System.Boolean apply = True) : System.Void`  

```csharp
public abstract System.Void SetLevel(Game.Settings.QualitySetting+Level quality, System.Boolean apply);
```

- `public abstract TransferValuesFrom(Game.Settings.QualitySetting setting) : System.Void`  

```csharp
public abstract System.Void TransferValuesFrom(Game.Settings.QualitySetting setting);
```


## Nested types

- `Game.Settings.QualitySetting+Level`  

