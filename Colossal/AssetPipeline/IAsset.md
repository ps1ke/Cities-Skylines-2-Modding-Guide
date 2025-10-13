# Colossal.AssetPipeline.IAsset

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** interface abstract public  

**Implements:** `System.IEquatable<Colossal.AssetPipeline.IAsset>`  

## Code

```csharp
public abstract interface IAsset : System.IEquatable<Colossal.AssetPipeline.IAsset>
{
    public System.String name { get; }
    public System.String fileName { get; }
    public System.String path { get; }
    public System.String hashPath { get; }
    public Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset collectedAsset { get; }

    public static Colossal.AssetPipeline.IAsset Create(Colossal.AssetPipeline.Settings settings, System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset);
}
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.String fileName { get }`  

```csharp
public System.String fileName { get; }
```

- `public System.String path { get }`  

```csharp
public System.String path { get; }
```

- `public System.String hashPath { get }`  

```csharp
public System.String hashPath { get; }
```

- `public Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset collectedAsset { get }`  

```csharp
public Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset collectedAsset { get; }
```


## Methods

- `public static Create(Colossal.AssetPipeline.Settings settings, System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset) : Colossal.AssetPipeline.IAsset`  

```csharp
public static Colossal.AssetPipeline.IAsset Create(Colossal.AssetPipeline.Settings settings, System.String name, Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset sourceAsset);
```


