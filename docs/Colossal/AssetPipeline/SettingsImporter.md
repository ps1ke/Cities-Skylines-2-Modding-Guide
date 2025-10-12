# Colossal.AssetPipeline.SettingsImporter

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class public  

**Base:** `Colossal.AssetPipeline.Importers.JSONImporter<Colossal.AssetPipeline.Settings>`  
**Implements:** `Colossal.AssetPipeline.Importers.IAssetImporter`, `Colossal.AssetPipeline.Importers.ISettingable`  

**Attributes:** `Extension`  

## Fields

- `private static const System.String kLODSettingsShortcut`  
- `private static const System.String kLODSettingShortcut`  
- `private static const System.String kSurfaceSettingShortcut`  

## Constructors

- `public SettingsImporter()`  

## Methods

- `protected virtual Expand(Colossal.Json.ProxyObject settingsProxy, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  
- `public static Expand(Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  
- `private static ExpandAssetMapping(System.String expression, System.Collections.Generic.List<System.String> importSettings, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  
- `private static ExpandImportSettings<T>(System.String expression, T setting, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  
- `private ExpandLODSettings(System.String key, System.Int32 index, Colossal.AssetPipeline.PostProcessors.LODPostProcessor+PostProcessSettings+LODLevelSettings setting, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  
- `private static ExpandSharedAsset(System.String name, System.String path, Colossal.AssetPipeline.Settings& settings, Colossal.AssetPipeline.Diagnostic.ReportBase report) : System.Boolean`  
- `private GetAssetName(System.String name, Colossal.AssetPipeline.Module module, System.String moduleStr, System.String material) : System.String`  
- `private static ParseName(System.String key, System.String& name, System.Int32& lod, Colossal.AssetPipeline.Module& module, System.String& moduleStr, System.String& material) : System.Boolean`  
- `private static ParseName(System.String[] entries, System.String& name, System.Int32& lod, Colossal.AssetPipeline.Module& module, System.String& moduleStr, System.String& material) : System.Void`  

## Nested types

- `Colossal.AssetPipeline.SettingsImporter+<>c__DisplayClass4_0`  

