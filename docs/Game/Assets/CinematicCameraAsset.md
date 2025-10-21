# Game.Assets.CinematicCameraAsset

**Assembly:** `Game`  
**Namespace:** `Game.Assets`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.Metadata<Game.CinematicCamera.CinematicCameraSequence>`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class CinematicCameraAsset : Colossal.IO.AssetDatabase.Metadata<Game.CinematicCamera.CinematicCameraSequence>, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile, Colossal.UI.Binding.IJsonWritable
{
    public static readonly System.Func<System.String> kPersistentLocation;
    private static readonly System.String kCloudTargetProperty;
    private static readonly System.String kReadOnlyProperty;
    public static const System.String kExtension;

    public CinematicCameraAsset();

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public static readonly System.Func<System.String> kPersistentLocation`  

```csharp
public static readonly System.Func<System.String> kPersistentLocation;
```

- `private static readonly System.String kCloudTargetProperty`  

```csharp
private static readonly System.String kCloudTargetProperty;
```

- `private static readonly System.String kReadOnlyProperty`  

```csharp
private static readonly System.String kReadOnlyProperty;
```

- `public static const System.String kExtension`  

```csharp
public static const System.String kExtension;
```


## Constructors

- `public CinematicCameraAsset()`  

```csharp
public CinematicCameraAsset();
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.Assets.CinematicCameraAsset+<>c`  

