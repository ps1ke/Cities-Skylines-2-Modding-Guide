# Game.Assets.MapMetadata

**Assembly:** `Game`  
**Namespace:** `Game.Assets`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.Metadata<Game.Assets.MapInfo>`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`  

## Code

```csharp
public class MapMetadata : Colossal.IO.AssetDatabase.Metadata<Game.Assets.MapInfo>, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile
{
    public static readonly System.Func<System.String> kPersistentLocation;
    public static const System.String kExtension;

    public MapMetadata();

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


## Constructors

- `public MapMetadata()`  

```csharp
public MapMetadata();
```


## Methods

- `protected virtual OnPostLoad() : System.Void`  

```csharp
protected override void OnPostLoad()
	{
		if (state == LoadState.Full && base.database.dataSource.Contains(base.id))
		{
			base.target.id = base.identifier;
			SourceMeta meta = GetMeta();
			base.target.metaData = this;
			base.target.isReadonly = !meta.belongsToCurrentUser;
			base.target.cloudTarget = meta.remoteStorageSourceName;
		}
	}
```


## Nested types

- `Game.Assets.MapMetadata+<>c`  

