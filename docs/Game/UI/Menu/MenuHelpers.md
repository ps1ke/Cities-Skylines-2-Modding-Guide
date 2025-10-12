# Game.UI.Menu.MenuHelpers

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static Colossal.Logging.ILog log`  
- `public static const System.Int32 kPreviewWidth`  
- `public static const System.Int32 kPreviewHeight`  

## Properties

- `public static Colossal.IO.AssetDatabase.TextureAsset defaultPreview { get }`  
- `public static Colossal.IO.AssetDatabase.TextureAsset defaultThumbnail { get }`  
- `public static System.Boolean hasPreviouslySavedGame { get }`  

## Methods

- `public static GetAvailableCloudTargets() : System.Collections.Generic.List<System.String>`  
- `public static GetLastModifiedSave() : Game.Assets.SaveGameMetadata`  
- `public static GetSanitizedCloudTarget(System.String cloudTarget) : System.ValueTuple<System.String, Colossal.IO.AssetDatabase.ILocalAssetDatabase>`  
- `public static UpdateMeta<T>(Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<T>> binding, System.Func<Colossal.IO.AssetDatabase.Metadata<T>, System.Boolean> filter = null) : System.Void`  

## Nested types

- `Game.UI.Menu.MenuHelpers+SaveGamePreviewSettings`  
- `Game.UI.Menu.MenuHelpers+<>c`  

