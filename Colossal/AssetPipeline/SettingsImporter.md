# Colossal.AssetPipeline.SettingsImporter

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Importers.JSONImporter<Colossal.AssetPipeline.Settings>`  
**Implements:** `Colossal.AssetPipeline.Importers.IAssetImporter`, `Colossal.AssetPipeline.Importers.ISettingable`  

**Attributes:** `Extension`  

## Code

```csharp
public class SettingsImporter : Colossal.AssetPipeline.Importers.JSONImporter<Colossal.AssetPipeline.Settings>, Colossal.AssetPipeline.Importers.IAssetImporter, Colossal.AssetPipeline.Importers.ISettingable
{
    private static const System.String kLODSettingsShortcut;
    private static const System.String kLODSettingShortcut;
    private static const System.String kSurfaceSettingShortcut;

    public SettingsImporter();

    protected virtual System.Boolean Expand(Colossal.Json.ProxyObject settingsProxy, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report);
    public static System.Boolean Expand(Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report);
    private static System.Boolean ExpandAssetMapping(System.String expression, System.Collections.Generic.List<System.String> importSettings, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report);
    private static System.Boolean ExpandImportSettings<T>(System.String expression, T setting, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report);
    private System.Boolean ExpandLODSettings(System.String key, System.Int32 index, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings setting, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report);
    private static System.Boolean ExpandSharedAsset(System.String name, System.String path, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report);
    private System.String GetAssetName(System.String name, Colossal.AssetPipeline.Module module, System.String moduleStr, System.String material);
    private static System.Boolean ParseName(System.String key, System.String& name, System.Int32& lod, Colossal.AssetPipeline.Module& module, System.String& moduleStr, System.String& material);
    private static System.Void ParseName(System.String[] entries, System.String& name, System.Int32& lod, Colossal.AssetPipeline.Module& module, System.String& moduleStr, System.String& material);
}
```


## Fields

- `private static const System.String kLODSettingsShortcut`  

```csharp
private static const System.String kLODSettingsShortcut;
```

- `private static const System.String kLODSettingShortcut`  

```csharp
private static const System.String kLODSettingShortcut;
```

- `private static const System.String kSurfaceSettingShortcut`  

```csharp
private static const System.String kSurfaceSettingShortcut;
```


## Constructors

- `public SettingsImporter()`  

```csharp
public SettingsImporter();
```


## Methods

- `protected virtual Expand(Colossal.Json.ProxyObject settingsProxy, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  

```csharp
protected virtual System.Boolean Expand(Colossal.Json.ProxyObject settingsProxy, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report);
```

- `public static Expand(Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  

```csharp
public static System.Boolean Expand(Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report);
```

- `private static ExpandAssetMapping(System.String expression, System.Collections.Generic.List<System.String> importSettings, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  

```csharp
private static System.Boolean ExpandAssetMapping(System.String expression, System.Collections.Generic.List<System.String> importSettings, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report);
```

- `private static ExpandImportSettings<T>(System.String expression, T setting, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  

```csharp
private static System.Boolean ExpandImportSettings<T>(System.String expression, T setting, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report);
```

- `private ExpandLODSettings(System.String key, System.Int32 index, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings setting, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  

```csharp
private System.Boolean ExpandLODSettings(System.String key, System.Int32 index, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings setting, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report);
```

- `private static ExpandSharedAsset(System.String name, System.String path, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  

```csharp
private static System.Boolean ExpandSharedAsset(System.String name, System.String path, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report);
```

- `private GetAssetName(System.String name, Colossal.AssetPipeline.Module module, System.String moduleStr, System.String material) : System.String`  

```csharp
private System.String GetAssetName(System.String name, Colossal.AssetPipeline.Module module, System.String moduleStr, System.String material);
```

- `private static ParseName(System.String key, System.String& name, System.Int32& lod, Colossal.AssetPipeline.Module& module, System.String& moduleStr, System.String& material) : System.Boolean`  

```csharp
private static System.Boolean ParseName(System.String key, System.String& name, System.Int32& lod, Colossal.AssetPipeline.Module& module, System.String& moduleStr, System.String& material);
```

- `private static ParseName(System.String[] entries, System.String& name, System.Int32& lod, Colossal.AssetPipeline.Module& module, System.String& moduleStr, System.String& material) : System.Void`  

```csharp
private static System.Void ParseName(System.String[] entries, System.String& name, System.Int32& lod, Colossal.AssetPipeline.Module& module, System.String& moduleStr, System.String& material);
```


## Nested types

- `Colossal.AssetPipeline.SettingsImporter+<>c__DisplayClass4_0`  

