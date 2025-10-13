# Colossal.AssetPipeline.PostProcessors.Context

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct Context
{
    public readonly System.String assetRootPath;
    public readonly System.Action<System.String, UnityEngine.Texture> onDebugOutputTexture;
    public readonly Colossal.AssetPipeline.MainThreadDispatcher mainThreadDispatcher;
    public readonly Colossal.AssetPipeline.Importers.ISettings settings;
    public readonly Colossal.AssetPipeline.Settings globalSettings;

    public Context(Colossal.AssetPipeline.MainThreadDispatcher mainThreadDispatcher, System.String assetRootPath, System.Action<System.String, UnityEngine.Texture> onDebugOutputTexture, Colossal.AssetPipeline.Importers.ISettings settings, Colossal.AssetPipeline.Settings globalSettings);

}
```


## Fields

- `public readonly System.String assetRootPath`  

```csharp
public readonly System.String assetRootPath;
```

- `public readonly System.Action<System.String, UnityEngine.Texture> onDebugOutputTexture`  

```csharp
public readonly System.Action<System.String, UnityEngine.Texture> onDebugOutputTexture;
```

- `public readonly Colossal.AssetPipeline.MainThreadDispatcher mainThreadDispatcher`  

```csharp
public readonly Colossal.AssetPipeline.MainThreadDispatcher mainThreadDispatcher;
```

- `public readonly Colossal.AssetPipeline.Importers.ISettings settings`  

```csharp
public readonly Colossal.AssetPipeline.Importers.ISettings settings;
```

- `public readonly Colossal.AssetPipeline.Settings globalSettings`  

```csharp
public readonly Colossal.AssetPipeline.Settings globalSettings;
```


## Constructors

- `public Context(Colossal.AssetPipeline.MainThreadDispatcher mainThreadDispatcher, System.String assetRootPath, System.Action<System.String, UnityEngine.Texture> onDebugOutputTexture, Colossal.AssetPipeline.Importers.ISettings settings, Colossal.AssetPipeline.Settings globalSettings)`  

```csharp
public Context(Colossal.AssetPipeline.MainThreadDispatcher mainThreadDispatcher, System.String assetRootPath, System.Action<System.String, UnityEngine.Texture> onDebugOutputTexture, Colossal.AssetPipeline.Importers.ISettings settings, Colossal.AssetPipeline.Settings globalSettings);
```


