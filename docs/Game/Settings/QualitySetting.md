# Game.Settings.QualitySetting

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class abstract public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

## Fields

- `private System.Boolean <disableSetting>k__BackingField`  

## Properties

- `public System.Boolean disableSetting { get; set }`  

## Constructors

- `protected QualitySetting()`  

## Methods

- `internal virtual AddToPageData(Game.UI.Menu.AutomaticSettings+SettingPageData pageData) : System.Void`  
- `public abstract EnumerateAvailableLevels() : System.Collections.Generic.IEnumerable<Game.Settings.QualitySetting+Level>`  
- `public abstract GetLevel() : Game.Settings.QualitySetting+Level`  
- `public abstract GetMockName(Game.Settings.QualitySetting+Level level) : System.String`  
- `public GetQualityValues() : Game.UI.Widgets.DropdownItem<System.Int32>[]`  
- `public virtual IsOptionFullyDisabled() : System.Boolean`  
- `public virtual IsOptionsDisabled() : System.Boolean`  
- `public virtual SetDefaults() : System.Void`  
- `public abstract SetLevel(Game.Settings.QualitySetting+Level quality, System.Boolean apply = True) : System.Void`  
- `public abstract TransferValuesFrom(Game.Settings.QualitySetting setting) : System.Void`  

## Nested types

- `Game.Settings.QualitySetting+Level`  

