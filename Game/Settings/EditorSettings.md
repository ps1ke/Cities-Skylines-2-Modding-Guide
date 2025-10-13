# Game.Settings.EditorSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`  

## Code

```csharp
public class EditorSettings : Game.Settings.Setting, System.IEquatable<Game.Settings.Setting>
{
    private System.Int32 <prefabPickerColumnCount>k__BackingField;
    private System.String[] <prefabPickerFavorites>k__BackingField;
    private System.String[] <prefabPickerSearchHistory>k__BackingField;
    private System.String[] <prefabPickerSearchFavorites>k__BackingField;
    private System.Int32 <assetPickerColumnCount>k__BackingField;
    private System.String[] <assetPickerFavorites>k__BackingField;
    private System.String[] <directoryPickerFavorites>k__BackingField;
    private System.Int32 <inspectorWidth>k__BackingField;
    private System.Int32 <hierarchyWidth>k__BackingField;
    private System.Boolean <useParallelImport>k__BackingField;
    private System.Boolean <lowQualityTextureCompression>k__BackingField;
    private System.String <lastSelectedProjectRootDirectory>k__BackingField;
    private System.String <lastSelectedImportDirectory>k__BackingField;
    private System.Boolean <showTutorials>k__BackingField;
    private System.Collections.Generic.Dictionary<System.String, System.Boolean> <shownTutorials>k__BackingField;

    public System.Int32 prefabPickerColumnCount { get; set; }
    public System.String[] prefabPickerFavorites { get; set; }
    public System.String[] prefabPickerSearchHistory { get; set; }
    public System.String[] prefabPickerSearchFavorites { get; set; }
    public System.Int32 assetPickerColumnCount { get; set; }
    public System.String[] assetPickerFavorites { get; set; }
    public System.String[] directoryPickerFavorites { get; set; }
    public System.Int32 inspectorWidth { get; set; }
    public System.Int32 hierarchyWidth { get; set; }
    public System.Boolean useParallelImport { get; set; }
    public System.Boolean lowQualityTextureCompression { get; set; }
    public System.String lastSelectedProjectRootDirectory { get; set; }
    public System.String lastSelectedImportDirectory { get; set; }
    public System.Boolean showTutorials { get; set; }
    public System.Collections.Generic.Dictionary<System.String, System.Boolean> shownTutorials { get; set; }
    public System.Boolean resetTutorials { set; }

    public EditorSettings();

    public System.Void ResetTutorials();
    public virtual System.Void SetDefaults();
}
```


## Fields

- `private System.Int32 <prefabPickerColumnCount>k__BackingField`  

```csharp
private System.Int32 <prefabPickerColumnCount>k__BackingField;
```

- `private System.String[] <prefabPickerFavorites>k__BackingField`  

```csharp
private System.String[] <prefabPickerFavorites>k__BackingField;
```

- `private System.String[] <prefabPickerSearchHistory>k__BackingField`  

```csharp
private System.String[] <prefabPickerSearchHistory>k__BackingField;
```

- `private System.String[] <prefabPickerSearchFavorites>k__BackingField`  

```csharp
private System.String[] <prefabPickerSearchFavorites>k__BackingField;
```

- `private System.Int32 <assetPickerColumnCount>k__BackingField`  

```csharp
private System.Int32 <assetPickerColumnCount>k__BackingField;
```

- `private System.String[] <assetPickerFavorites>k__BackingField`  

```csharp
private System.String[] <assetPickerFavorites>k__BackingField;
```

- `private System.String[] <directoryPickerFavorites>k__BackingField`  

```csharp
private System.String[] <directoryPickerFavorites>k__BackingField;
```

- `private System.Int32 <inspectorWidth>k__BackingField`  

```csharp
private System.Int32 <inspectorWidth>k__BackingField;
```

- `private System.Int32 <hierarchyWidth>k__BackingField`  

```csharp
private System.Int32 <hierarchyWidth>k__BackingField;
```

- `private System.Boolean <useParallelImport>k__BackingField`  

```csharp
private System.Boolean <useParallelImport>k__BackingField;
```

- `private System.Boolean <lowQualityTextureCompression>k__BackingField`  

```csharp
private System.Boolean <lowQualityTextureCompression>k__BackingField;
```

- `private System.String <lastSelectedProjectRootDirectory>k__BackingField`  

```csharp
private System.String <lastSelectedProjectRootDirectory>k__BackingField;
```

- `private System.String <lastSelectedImportDirectory>k__BackingField`  

```csharp
private System.String <lastSelectedImportDirectory>k__BackingField;
```

- `private System.Boolean <showTutorials>k__BackingField`  

```csharp
private System.Boolean <showTutorials>k__BackingField;
```

- `private System.Collections.Generic.Dictionary<System.String, System.Boolean> <shownTutorials>k__BackingField`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Boolean> <shownTutorials>k__BackingField;
```


## Properties

- `public System.Int32 prefabPickerColumnCount { get; set }`  

```csharp
public System.Int32 prefabPickerColumnCount { get; set; }
```

- `public System.String[] prefabPickerFavorites { get; set }`  

```csharp
public System.String[] prefabPickerFavorites { get; set; }
```

- `public System.String[] prefabPickerSearchHistory { get; set }`  

```csharp
public System.String[] prefabPickerSearchHistory { get; set; }
```

- `public System.String[] prefabPickerSearchFavorites { get; set }`  

```csharp
public System.String[] prefabPickerSearchFavorites { get; set; }
```

- `public System.Int32 assetPickerColumnCount { get; set }`  

```csharp
public System.Int32 assetPickerColumnCount { get; set; }
```

- `public System.String[] assetPickerFavorites { get; set }`  

```csharp
public System.String[] assetPickerFavorites { get; set; }
```

- `public System.String[] directoryPickerFavorites { get; set }`  

```csharp
public System.String[] directoryPickerFavorites { get; set; }
```

- `public System.Int32 inspectorWidth { get; set }`  

```csharp
public System.Int32 inspectorWidth { get; set; }
```

- `public System.Int32 hierarchyWidth { get; set }`  

```csharp
public System.Int32 hierarchyWidth { get; set; }
```

- `public System.Boolean useParallelImport { get; set }`  

```csharp
public System.Boolean useParallelImport { get; set; }
```

- `public System.Boolean lowQualityTextureCompression { get; set }`  

```csharp
public System.Boolean lowQualityTextureCompression { get; set; }
```

- `public System.String lastSelectedProjectRootDirectory { get; set }`  

```csharp
public System.String lastSelectedProjectRootDirectory { get; set; }
```

- `public System.String lastSelectedImportDirectory { get; set }`  

```csharp
public System.String lastSelectedImportDirectory { get; set; }
```

- `public System.Boolean showTutorials { get; set }`  

```csharp
public System.Boolean showTutorials { get; set; }
```

- `public System.Collections.Generic.Dictionary<System.String, System.Boolean> shownTutorials { get; set }`  

```csharp
public System.Collections.Generic.Dictionary<System.String, System.Boolean> shownTutorials { get; set; }
```

- `public System.Boolean resetTutorials { set }`  

```csharp
public System.Boolean resetTutorials { set; }
```


## Constructors

- `public EditorSettings()`  

```csharp
public EditorSettings()
	{
		SetDefaults();
	}
```


## Methods

- `public ResetTutorials() : System.Void`  

```csharp
public void ResetTutorials()
	{
		shownTutorials.Clear();
		ApplyAndSave();
		World.DefaultGameObjectInjectionWorld.GetExistingSystemManaged<EditorTutorialSystem>().OnResetTutorials();
	}
```

- `public virtual SetDefaults() : System.Void`  

```csharp
public override void SetDefaults()
	{
		prefabPickerColumnCount = 1;
		prefabPickerFavorites = new string[0];
		prefabPickerSearchHistory = new string[0];
		prefabPickerSearchFavorites = new string[0];
		assetPickerColumnCount = 4;
		assetPickerFavorites = new string[0];
		directoryPickerFavorites = new string[0];
		inspectorWidth = 450;
		hierarchyWidth = 350;
		lastSelectedProjectRootDirectory = null;
		lastSelectedImportDirectory = null;
		useParallelImport = true;
		lowQualityTextureCompression = false;
		showTutorials = false;
		shownTutorials = new Dictionary<string, bool>();
	}
```


