# Game.UI.Menu.MenuHelpers

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class MenuHelpers
{
    private static Colossal.Logging.ILog log;
    public static const System.Int32 kPreviewWidth;
    public static const System.Int32 kPreviewHeight;

    public static Colossal.IO.AssetDatabase.TextureAsset defaultPreview { get; }
    public static Colossal.IO.AssetDatabase.TextureAsset defaultThumbnail { get; }
    public static System.Boolean hasPreviouslySavedGame { get; }

    public static System.Collections.Generic.List<System.String> GetAvailableCloudTargets();
    public static Game.Assets.SaveGameMetadata GetLastModifiedSave();
    public static System.ValueTuple<System.String, Colossal.IO.AssetDatabase.ILocalAssetDatabase> GetSanitizedCloudTarget(System.String cloudTarget);
    public static System.Void UpdateMeta<T>(Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<T>> binding, System.Func<Colossal.IO.AssetDatabase.Metadata<T>, System.Boolean> filter);
}
```


## Fields

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `public static const System.Int32 kPreviewWidth`  

```csharp
public static const System.Int32 kPreviewWidth;
```

- `public static const System.Int32 kPreviewHeight`  

```csharp
public static const System.Int32 kPreviewHeight;
```


## Properties

- `public static Colossal.IO.AssetDatabase.TextureAsset defaultPreview { get }`  

```csharp
public static Colossal.IO.AssetDatabase.TextureAsset defaultPreview { get; }
```

- `public static Colossal.IO.AssetDatabase.TextureAsset defaultThumbnail { get }`  

```csharp
public static Colossal.IO.AssetDatabase.TextureAsset defaultThumbnail { get; }
```

- `public static System.Boolean hasPreviouslySavedGame { get }`  

```csharp
public static System.Boolean hasPreviouslySavedGame { get; }
```


## Methods

- `public static GetAvailableCloudTargets() : System.Collections.Generic.List<System.String>`  

```csharp
public static List<string> GetAvailableCloudTargets()
	{
		return (from x in AssetDatabase.global.GetAvailableRemoteStorages()
			select x.name).ToList();
	}
```

- `public static GetLastModifiedSave() : Game.Assets.SaveGameMetadata`  

```csharp
public static SaveGameMetadata GetLastModifiedSave()
	{
		SaveGameMetadata result = null;
		DateTime dateTime = DateTime.MinValue;
		foreach (SaveGameMetadata asset in AssetDatabase.global.GetAssets(default(SearchFilter<SaveGameMetadata>)))
		{
			DateTime lastModified = asset.target.lastModified;
			if (lastModified > dateTime)
			{
				dateTime = lastModified;
				result = asset;
			}
		}
		return result;
	}
```

- `public static GetSanitizedCloudTarget(System.String cloudTarget) : System.ValueTuple<System.String, Colossal.IO.AssetDatabase.ILocalAssetDatabase>`  

```csharp
public static System.ValueTuple<System.String, Colossal.IO.AssetDatabase.ILocalAssetDatabase> GetSanitizedCloudTarget(System.String cloudTarget);
```

- `public static UpdateMeta<T>(Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<T>> binding, System.Func<Colossal.IO.AssetDatabase.Metadata<T>, System.Boolean> filter = null) : System.Void`  

```csharp
public static System.Void UpdateMeta<T>(Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<T>> binding, System.Func<Colossal.IO.AssetDatabase.Metadata<T>, System.Boolean> filter);
```


## Nested types

- `Game.UI.Menu.MenuHelpers+SaveGamePreviewSettings`  
- `Game.UI.Menu.MenuHelpers+<>c`  

