# Game.Debug.Tests.TestAsset

**Assembly:** `Game.TestScenarios`  
**Namespace:** `Game.Debug.Tests`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.IAssetData<Game.Debug.Tests.TestAsset+Data>`  

## Code

```csharp
public class TestAsset : Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile, Colossal.IO.AssetDatabase.IAssetData<Game.Debug.Tests.TestAsset+Data>
{
    private Game.Debug.Tests.TestAsset+Data m_Data;
    public static const System.String kExtension;

    public Game.Debug.Tests.TestAsset+Data data { get; }
    public Colossal.IO.AssetDatabase.LoadState state { get; }

    public TestAsset();

    public System.Void SetData(Game.Debug.Tests.TestAsset+Data data);
    public virtual System.Void Unload(System.Boolean force);
}
```


## Fields

- `private Game.Debug.Tests.TestAsset+Data m_Data`  

```csharp
private Game.Debug.Tests.TestAsset+Data m_Data;
```

- `public static const System.String kExtension`  

```csharp
public static const System.String kExtension;
```


## Properties

- `public Game.Debug.Tests.TestAsset+Data data { get }`  

```csharp
public Game.Debug.Tests.TestAsset+Data data { get; }
```

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  

```csharp
public Colossal.IO.AssetDatabase.LoadState state { get; }
```


## Constructors

- `public TestAsset()`  

```csharp
public TestAsset();
```


## Methods

- `public SetData(Game.Debug.Tests.TestAsset+Data data) : System.Void`  

```csharp
public System.Void SetData(Game.Debug.Tests.TestAsset+Data data);
```

- `public virtual Unload(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Unload(System.Boolean force);
```


## Nested types

- `Game.Debug.Tests.TestAsset+Data`  

