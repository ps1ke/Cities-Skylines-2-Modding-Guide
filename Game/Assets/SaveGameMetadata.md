# Game.Assets.SaveGameMetadata

**Assembly:** `Game`  
**Namespace:** `Game.Assets`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.Metadata<Game.Assets.SaveInfo>`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`  

## Code

```csharp
public class SaveGameMetadata : Colossal.IO.AssetDatabase.Metadata<Game.Assets.SaveInfo>, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile
{
    public static readonly System.Func<System.String> kPersistentLocation;
    public static const System.String kExtension;

    public System.Boolean isValidSaveGame { get; }
    public System.Collections.Generic.IEnumerable<System.String> modTags { get; }

    public SaveGameMetadata();

    private System.Collections.Generic.IEnumerable<System.String> <>n__0();
    protected virtual System.Void OnPostLoad();
}
```


## Fields

- `public static readonly System.Func<System.String> kPersistentLocation`  

```csharp
public static readonly System.Func<System.String> kPersistentLocation;
```

- `public static const System.String kExtension`  

```csharp
public static const System.String kExtension;
```


## Properties

- `public System.Boolean isValidSaveGame { get }`  

```csharp
public System.Boolean isValidSaveGame { get; }
```

- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> modTags { get; }
```


## Constructors

- `public SaveGameMetadata()`  

```csharp
public SaveGameMetadata();
```


## Methods

- `private <>n__0() : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
private System.Collections.Generic.IEnumerable<System.String> <>n__0();
```

- `protected virtual OnPostLoad() : System.Void`  

```csharp
protected override void OnPostLoad()
	{
		if (state != LoadState.Full)
		{
			return;
		}
		if (!base.database.dataSource.Contains(base.id))
		{
			return;
		}
		base.target.id = base.identifier;
		SourceMeta meta = GetMeta();
		base.target.metaData = this;
		if (meta.packaged && base.database.TryGetAsset(meta.package, out PackageAsset assetData))
		{
			base.target.displayName = assetData.GetMeta().displayName;
		}
		else
		{
			base.target.displayName = meta.displayName;
		}
		base.target.path = base.id.uri;
		base.target.isReadonly = !meta.belongsToCurrentUser;
		base.target.lastModified = meta.lastWriteTime.ToLocalTime();
		base.target.cloudTarget = meta.remoteStorageSourceName;
		if (!(base.target.saveGameData == null))
		{
			return;
		}
		if (base.database.TryGetAsset(Hash128.CreateGuid(Path.ChangeExtension(meta.path, SaveGameData.kExtensions[1])), out SaveGameData assetData2))
		{
			base.target.saveGameData = assetData2;
		}
		else if (meta.packaged)
		{
			base.target.saveGameData = base.database.GetAsset(SearchFilter<SaveGameData>.ByCondition((SaveGameData a) => a.GetMeta().package == meta.package));
		}
	}
```


## Nested types

- `Game.Assets.SaveGameMetadata+<>c`  
- `Game.Assets.SaveGameMetadata+<>c__DisplayClass2_0`  
- `Game.Assets.SaveGameMetadata+<get_modTags>d__6`  

