# Colossal.AssetPipeline.Collectors.SourceAssetCollector

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Collectors`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>>`, `System.Collections.IEnumerable`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct SourceAssetCollector : System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>>, System.Collections.IEnumerable
{
    private readonly System.Collections.Generic.HashSet<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>> m_AssetList;

    public System.Int32 count { get; }

    public SourceAssetCollector(System.String projectRootPath, System.String relativePath);
    public SourceAssetCollector(System.String projectRootPath, System.Collections.Generic.IEnumerable<System.String> relativePaths);

    private static System.Void GetDirectories(System.String path, System.String projectRootPath, System.Collections.Generic.HashSet`1[[Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup`1[[Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& assetList);
    public System.Collections.Generic.HashSet<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>> GetEnumerator();
    private static System.Collections.Generic.IEnumerable<System.String> Internal_GetDirectories(System.String path);
    private static System.Collections.Generic.IEnumerable<System.String> Internal_GetFiles(System.String path);
    private System.Collections.Generic.IEnumerator<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>> System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Collectors.SourceAssetCollector.AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector.Asset>>.GetEnumerator();
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
}
```


## Fields

- `private readonly System.Collections.Generic.HashSet<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>> m_AssetList`  

```csharp
private readonly System.Collections.Generic.HashSet<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>> m_AssetList;
```


## Properties

- `public System.Int32 count { get }`  

```csharp
public System.Int32 count { get; }
```


## Constructors

- `public SourceAssetCollector(System.String projectRootPath, System.String relativePath)`  

```csharp
public SourceAssetCollector(System.String projectRootPath, System.String relativePath);
```

- `public SourceAssetCollector(System.String projectRootPath, System.Collections.Generic.IEnumerable<System.String> relativePaths)`  

```csharp
public SourceAssetCollector(System.String projectRootPath, System.Collections.Generic.IEnumerable<System.String> relativePaths);
```


## Methods

- `private static GetDirectories(System.String path, System.String projectRootPath, System.Collections.Generic.HashSet`1[[Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup`1[[Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& assetList) : System.Void`  

```csharp
private static System.Void GetDirectories(System.String path, System.String projectRootPath, System.Collections.Generic.HashSet`1[[Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup`1[[Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& assetList);
```

- `public GetEnumerator() : System.Collections.Generic.HashSet<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>>`  

```csharp
public System.Collections.Generic.HashSet<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>> GetEnumerator();
```

- `private static Internal_GetDirectories(System.String path) : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
private static System.Collections.Generic.IEnumerable<System.String> Internal_GetDirectories(System.String path);
```

- `private static Internal_GetFiles(System.String path) : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
private static System.Collections.Generic.IEnumerable<System.String> Internal_GetFiles(System.String path);
```

- `private System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Collectors.SourceAssetCollector.AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector.Asset>>.GetEnumerator() : System.Collections.Generic.IEnumerator<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>>`  

```csharp
private System.Collections.Generic.IEnumerator<Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>> System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Collectors.SourceAssetCollector.AssetGroup<Colossal.AssetPipeline.Collectors.SourceAssetCollector.Asset>>.GetEnumerator();
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```


## Nested types

- `Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset`  
- `Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<T>`  
- `Colossal.AssetPipeline.Collectors.SourceAssetCollector+<>c`  

