# Game.ArtPipeline.AssetMapper

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline`  

**Type:** class public  

**Base:** `UnityEngine.ScriptableObject`  

## Code

```csharp
public class AssetMapper : UnityEngine.ScriptableObject
{
    public System.String m_SourcePath;
    public System.Collections.Generic.List<Game.ArtPipeline.AssetMapper+AssetMap> m_AssetMap;

    public AssetMapper();

    public Game.ArtPipeline.AssetMapper+MappingState AddMapping(System.String relativePath, System.String path);
    public System.Void Clear();
    public System.Void RemoveMapping(System.String relativePath);
}
```


## Fields

- `public System.String m_SourcePath`  

```csharp
public System.String m_SourcePath;
```

- `public System.Collections.Generic.List<Game.ArtPipeline.AssetMapper+AssetMap> m_AssetMap`  

```csharp
public System.Collections.Generic.List<Game.ArtPipeline.AssetMapper+AssetMap> m_AssetMap;
```


## Constructors

- `public AssetMapper()`  

```csharp
public AssetMapper();
```


## Methods

- `public AddMapping(System.String relativePath, System.String path) : Game.ArtPipeline.AssetMapper+MappingState`  

```csharp
public Game.ArtPipeline.AssetMapper+MappingState AddMapping(System.String relativePath, System.String path);
```

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `public RemoveMapping(System.String relativePath) : System.Void`  

```csharp
public System.Void RemoveMapping(System.String relativePath);
```


## Nested types

- `Game.ArtPipeline.AssetMapper+MappingState`  
- `Game.ArtPipeline.AssetMapper+AssetMap`  
- `Game.ArtPipeline.AssetMapper+<>c__DisplayClass4_0`  
- `Game.ArtPipeline.AssetMapper+<>c__DisplayClass6_0`  

