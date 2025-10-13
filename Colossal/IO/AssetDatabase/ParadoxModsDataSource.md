# Colossal.IO.AssetDatabase.ParadoxModsDataSource

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.FileSystemDataSource`  
**Implements:** `Colossal.IO.AssetDatabase.IDataSourceProvider`, `System.IDisposable`  

## Code

```csharp
public class ParadoxModsDataSource : Colossal.IO.AssetDatabase.FileSystemDataSource, Colossal.IO.AssetDatabase.IDataSourceProvider, System.IDisposable
{
    private System.Boolean m_DataCached;
    private readonly Colossal.PSI.PdxSdk.PdxSdkPlatform m_PlatformManager;
    private readonly System.String m_RootPath;
    private System.Collections.Generic.HashSet<Colossal.PSI.Common.Mod> m_ActiveMods;
    private System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.PSI.Common.Mod> m_PlatformInfoMap;
    private System.Action<Colossal.Hash128, System.Boolean> onEntryIsInActivePlaysetChanged;
    private System.Action onAfterActivePlaysetOrModStatusChanged;
    private static const System.String kScheme;

    public System.String remoteStorageSourceName { get; }

    public ParadoxModsDataSource(Colossal.IO.AssetDatabase.IAssetFactory assetFactory);

    private System.Void <Populate>b__17_0(System.TimeSpan t);
    public virtual System.Void DeleteEntry(Colossal.Hash128 guid);
    public virtual System.Void Dispose();
    public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.Mod> GetActiveMods();
    public virtual Colossal.IO.AssetDatabase.SourceMeta GetMeta(Colossal.Hash128 guid);
    private static System.String GetRootPath();
    private System.Threading.Tasks.Task OnActivePlaysetChanged();
    private System.Void OnActivePlaysetChangedAsync();
    private System.Threading.Tasks.Task OnModStatusChanged(Colossal.PSI.Common.Mod mod, System.Boolean enable);
    private System.Void OnModStatusChangedAsync(Colossal.PSI.Common.Mod changedMod, System.Boolean enable);
    public System.Threading.Tasks.Task Populate();
    public virtual System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>> PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress);
    public System.Threading.Tasks.Task PopulateMetadata(System.String modAbsolutePath);
    public System.Boolean TryGetMod(System.String path, Colossal.PSI.Common.Mod& mod);
}
```


## Fields

- `private System.Boolean m_DataCached`  

```csharp
private System.Boolean m_DataCached;
```

- `private readonly Colossal.PSI.PdxSdk.PdxSdkPlatform m_PlatformManager`  

```csharp
private readonly Colossal.PSI.PdxSdk.PdxSdkPlatform m_PlatformManager;
```

- `private readonly System.String m_RootPath`  

```csharp
private readonly System.String m_RootPath;
```

- `private System.Collections.Generic.HashSet<Colossal.PSI.Common.Mod> m_ActiveMods`  

```csharp
private System.Collections.Generic.HashSet<Colossal.PSI.Common.Mod> m_ActiveMods;
```

- `private System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.PSI.Common.Mod> m_PlatformInfoMap`  

```csharp
private System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.PSI.Common.Mod> m_PlatformInfoMap;
```

- `private System.Action<Colossal.Hash128, System.Boolean> onEntryIsInActivePlaysetChanged`  

```csharp
private System.Action<Colossal.Hash128, System.Boolean> onEntryIsInActivePlaysetChanged;
```

- `private System.Action onAfterActivePlaysetOrModStatusChanged`  

```csharp
private System.Action onAfterActivePlaysetOrModStatusChanged;
```

- `private static const System.String kScheme`  

```csharp
private static const System.String kScheme;
```


## Properties

- `public System.String remoteStorageSourceName { get }`  

```csharp
public System.String remoteStorageSourceName { get; }
```


## Constructors

- `public ParadoxModsDataSource(Colossal.IO.AssetDatabase.IAssetFactory assetFactory)`  

```csharp
public ParadoxModsDataSource(Colossal.IO.AssetDatabase.IAssetFactory assetFactory);
```


## Methods

- `private <Populate>b__17_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <Populate>b__17_0(System.TimeSpan t);
```

- `public virtual DeleteEntry(Colossal.Hash128 guid) : System.Void`  

```csharp
public virtual System.Void DeleteEntry(Colossal.Hash128 guid);
```

- `public virtual Dispose() : System.Void`  

```csharp
public virtual System.Void Dispose();
```

- `public GetActiveMods() : System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.Mod>`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.Mod> GetActiveMods();
```

- `public virtual GetMeta(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.SourceMeta`  

```csharp
public virtual Colossal.IO.AssetDatabase.SourceMeta GetMeta(Colossal.Hash128 guid);
```

- `private static GetRootPath() : System.String`  

```csharp
private static System.String GetRootPath();
```

- `private OnActivePlaysetChanged() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task OnActivePlaysetChanged();
```

- `private OnActivePlaysetChangedAsync() : System.Void`  

```csharp
private System.Void OnActivePlaysetChangedAsync();
```

- `private OnModStatusChanged(Colossal.PSI.Common.Mod mod, System.Boolean enable) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task OnModStatusChanged(Colossal.PSI.Common.Mod mod, System.Boolean enable);
```

- `private OnModStatusChangedAsync(Colossal.PSI.Common.Mod changedMod, System.Boolean enable) : System.Void`  

```csharp
private System.Void OnModStatusChangedAsync(Colossal.PSI.Common.Mod changedMod, System.Boolean enable);
```

- `public Populate() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Populate();
```

- `public virtual PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress) : System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>>`  

```csharp
public virtual System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>> PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress);
```

- `public PopulateMetadata(System.String modAbsolutePath) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task PopulateMetadata(System.String modAbsolutePath);
```

- `public TryGetMod(System.String path, Colossal.PSI.Common.Mod& mod) : System.Boolean`  

```csharp
public System.Boolean TryGetMod(System.String path, Colossal.PSI.Common.Mod& mod);
```


## Events

- `onEntryIsInActivePlaysetChanged` : `System.Action<Colossal.Hash128, System.Boolean>`  

```csharp
public event System.Action<Colossal.Hash128, System.Boolean> onEntryIsInActivePlaysetChanged;
```

- `onAfterActivePlaysetOrModStatusChanged` : `System.Action`  

```csharp
public event System.Action onAfterActivePlaysetOrModStatusChanged;
```


## Nested types

- `Colossal.IO.AssetDatabase.ParadoxModsDataSource+<>c__DisplayClass23_0`  
- `Colossal.IO.AssetDatabase.ParadoxModsDataSource+<>c__DisplayClass25_0`  
- `Colossal.IO.AssetDatabase.ParadoxModsDataSource+<>c__DisplayClass25_1`  
- `Colossal.IO.AssetDatabase.ParadoxModsDataSource+<>c__DisplayClass25_2`  
- `Colossal.IO.AssetDatabase.ParadoxModsDataSource+<OnActivePlaysetChanged>d__25`  
- `Colossal.IO.AssetDatabase.ParadoxModsDataSource+<OnActivePlaysetChangedAsync>d__24`  
- `Colossal.IO.AssetDatabase.ParadoxModsDataSource+<OnModStatusChanged>d__23`  
- `Colossal.IO.AssetDatabase.ParadoxModsDataSource+<OnModStatusChangedAsync>d__22`  
- `Colossal.IO.AssetDatabase.ParadoxModsDataSource+<Populate>d__17`  
- `Colossal.IO.AssetDatabase.ParadoxModsDataSource+<PopulateDataSource>d__19`  
- `Colossal.IO.AssetDatabase.ParadoxModsDataSource+<PopulateMetadata>d__18`  

