# Colossal.IO.AssetDatabase.AssetDatabase

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetDatabase`, `System.IDisposable`  

## Code

```csharp
public class AssetDatabase : Colossal.IO.AssetDatabase.IAssetDatabase, System.IDisposable
{
    private Colossal.IO.AssetDatabase.HTTP.DBServer m_HttpServer;
    private Colossal.IO.AssetDatabase.AssetDatabaseResources m_Resources;
    private readonly Colossal.IO.AssetDatabase.AssetDatabase+SettingsConfiguration m_SettingsConfiguration;
    private Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode <autoReloadMode>k__BackingField;
    private readonly Colossal.EventBroadcaster<Colossal.IO.AssetDatabase.AssetChangedEventArgs> <onAssetDatabaseChanged>k__BackingField;
    private readonly System.Collections.Generic.Dictionary<System.Type, Colossal.IO.AssetDatabase.IAssetData> m_PendingChangeTypes;
    private System.Boolean m_NotificationsEnabled;
    private readonly System.Threading.SemaphoreSlim m_DatabasesLock;
    private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.IAssetDatabaseInternal> m_Databases;
    private Colossal.IO.AssetDatabase.AssetDatabase+Settings m_Settings;
    private static Colossal.Logging.ILog log;
    private static Colossal.IO.AssetDatabase.AssetDatabase s_Instance;
    private static Colossal.IO.AssetDatabase.Game s_GameDescriptor;
    public static const System.String kAssetDbScheme;
    public static const System.String kAssetDbProtocol;
    private static const System.String kCacheAssetTask;
    public static const System.String kSaveSettingsTask;
    public static const System.String kCacheAssetsTaskName;

    public System.Int32 mipBias { get; }
    public System.Boolean isServingHttp { get; }
    public System.Int32 httpPort { get; }
    public Colossal.IO.AssetDatabase.AssetDatabaseResources resources { get; }
    public System.Boolean isCached { get; }
    public Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode autoReloadMode { get; set; }
    public Colossal.EventBroadcaster<Colossal.IO.AssetDatabase.AssetChangedEventArgs> onAssetDatabaseChanged { get; }
    public System.Boolean areNotificationsEnabled { get; }
    public static System.Boolean exists { get; }
    public static Colossal.IO.AssetDatabase.AssetDatabase global { get; }
    public static Colossal.IO.AssetDatabase.ILocalAssetDatabase game { get; }
    public static Colossal.IO.AssetDatabase.ILocalAssetDatabase user { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.IO.AssetDatabase.IAssetDatabase> databases { get; }
    public System.String name { get; }
    public System.String hostname { get; }
    public System.String rootPath { get; }
    public System.Int32 count { get; }

    private AssetDatabase();

    private System.Void <GetAssets>b__92_0<T>(System.TimeSpan t);
    private System.Threading.Tasks.Task <SaveSettings>b__95_0();
    private System.Void <TryGetAsset>b__76_0<T>(System.TimeSpan t);
    public System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.IAssetData> AllAssets();
    public System.Boolean AreAssetsWarningsEnabled(Colossal.IO.AssetDatabase.AssetData asset);
    public System.Threading.Tasks.Task CacheAssets(System.Threading.CancellationToken ct);
    public System.Threading.Tasks.Task CacheAssets(System.Boolean priorityAssets, System.Threading.CancellationToken ct);
    public static System.Void ClearAsyncReadManagerCacheHack();
    public System.Void ClearCache();
    private static System.Void CreateAsyncReadManagerCacheHack();
    public System.Void DeleteAsset(Colossal.Hash128 guid);
    public System.Void DeleteAsset<T>(T asset);
    public Colossal.IO.AssetDatabase.DisableNotificationsScoped DisableNotificationsScoped();
    public System.Void Dispose();
    public System.Void EnableNotifications(System.Boolean enable);
    public TAssetData GetAsset<TAssetData>(System.Uri uri);
    public TAssetData GetAsset<TAssetData>(System.String uri);
    public TAssetData GetAsset<TAssetData>(Colossal.Hash128 guid);
    public T GetAsset<T>(Colossal.IO.AssetDatabase.SearchFilter<T> filter);
    public Colossal.IO.AssetDatabase.IAssetData GetAsset(System.Uri uri);
    public Colossal.IO.AssetDatabase.IAssetData GetAsset(System.String uri);
    public Colossal.IO.AssetDatabase.IAssetData GetAsset(Colossal.Hash128 guid);
    public Colossal.IO.AssetDatabase.IAssetData GetAsset(Colossal.IO.AssetDatabase.SearchFilter<Colossal.IO.AssetDatabase.IAssetData> filter);
    public System.Collections.Generic.IEnumerable<T> GetAssets<T>(Colossal.IO.AssetDatabase.SearchFilter<T> filter);
    public System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.IO.AssetDatabase.ILocalAssetDatabase>> GetAvailableRemoteStorages();
    public static Colossal.IO.AssetDatabase.ILocalAssetDatabase GetTransient(System.Int64 maxChunkSize, System.String rootPath);
    public System.Void LoadSettings(System.String name, System.Object obj, System.Object defaultObj);
    public System.Void LoadSettings<T>(System.String name, System.Action<T, Colossal.IO.AssetDatabase.SourceMeta> obj);
    private System.Void NotifyChange(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
    private System.Void OnPriorityDataCached();
    public System.Threading.Tasks.Task RegisterDatabase(Colossal.IO.AssetDatabase.IAssetDatabase database);
    public System.Threading.Tasks.Task<System.String> ResaveCache();
    public System.Void SaveCache();
    public System.Threading.Tasks.Task SaveSettings();
    public System.Void SetSettingsConfiguration(System.Boolean saveAll, System.Boolean cleanupSettings);
    public virtual System.String ToString();
    public System.Boolean TryGetAsset<TAssetData>(System.Uri uri, TAssetData& asset);
    public System.Boolean TryGetAsset<TAssetData>(System.String uri, TAssetData& asset);
    public System.Boolean TryGetAsset<TAssetData>(Colossal.Hash128 guid, TAssetData& asset);
    public System.Boolean TryGetAsset<T>(Colossal.IO.AssetDatabase.SearchFilter<T> filter, T& asset);
    public System.Boolean TryGetAsset(System.Uri uri, Colossal.IO.AssetDatabase.IAssetData& asset);
    public System.Boolean TryGetAsset(System.String uri, Colossal.IO.AssetDatabase.IAssetData& asset);
    public System.Boolean TryGetAsset(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.IAssetData& asset);
    public System.Boolean TryGetAsset(Colossal.IO.AssetDatabase.SearchFilter<Colossal.IO.AssetDatabase.IAssetData> filter, Colossal.IO.AssetDatabase.IAssetData& asset);
    private System.Boolean TryGetAssetInternal<TAssetData>(System.Uri uri, TAssetData& asset, System.Boolean throws);
    public System.Boolean TryGetDatabase(System.Uri uri, Colossal.IO.AssetDatabase.IAssetDatabase& database);
    public System.Boolean TryGetDatabase(System.String name, Colossal.IO.AssetDatabase.IAssetDatabase& database);
    public System.Void UnloadAllAssets();
    public System.Threading.Tasks.Task<System.Boolean> UnregisterDatabase(Colossal.IO.AssetDatabase.IAssetDatabase database);
}
```


## Fields

- `private Colossal.IO.AssetDatabase.HTTP.DBServer m_HttpServer`  

```csharp
private Colossal.IO.AssetDatabase.HTTP.DBServer m_HttpServer;
```

- `private Colossal.IO.AssetDatabase.AssetDatabaseResources m_Resources`  

```csharp
private Colossal.IO.AssetDatabase.AssetDatabaseResources m_Resources;
```

- `private readonly Colossal.IO.AssetDatabase.AssetDatabase+SettingsConfiguration m_SettingsConfiguration`  

```csharp
private readonly Colossal.IO.AssetDatabase.AssetDatabase+SettingsConfiguration m_SettingsConfiguration;
```

- `private Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode <autoReloadMode>k__BackingField`  

```csharp
private Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode <autoReloadMode>k__BackingField;
```

- `private readonly Colossal.EventBroadcaster<Colossal.IO.AssetDatabase.AssetChangedEventArgs> <onAssetDatabaseChanged>k__BackingField`  

```csharp
private readonly Colossal.EventBroadcaster<Colossal.IO.AssetDatabase.AssetChangedEventArgs> <onAssetDatabaseChanged>k__BackingField;
```

- `private readonly System.Collections.Generic.Dictionary<System.Type, Colossal.IO.AssetDatabase.IAssetData> m_PendingChangeTypes`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.Type, Colossal.IO.AssetDatabase.IAssetData> m_PendingChangeTypes;
```

- `private System.Boolean m_NotificationsEnabled`  

```csharp
private System.Boolean m_NotificationsEnabled;
```

- `private readonly System.Threading.SemaphoreSlim m_DatabasesLock`  

```csharp
private readonly System.Threading.SemaphoreSlim m_DatabasesLock;
```

- `private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.IAssetDatabaseInternal> m_Databases`  

```csharp
private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.IAssetDatabaseInternal> m_Databases;
```

- `private Colossal.IO.AssetDatabase.AssetDatabase+Settings m_Settings`  

```csharp
private Colossal.IO.AssetDatabase.AssetDatabase+Settings m_Settings;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static Colossal.IO.AssetDatabase.AssetDatabase s_Instance`  

```csharp
private static Colossal.IO.AssetDatabase.AssetDatabase s_Instance;
```

- `private static Colossal.IO.AssetDatabase.Game s_GameDescriptor`  

```csharp
private static Colossal.IO.AssetDatabase.Game s_GameDescriptor;
```

- `public static const System.String kAssetDbScheme`  

```csharp
public static const System.String kAssetDbScheme;
```

- `public static const System.String kAssetDbProtocol`  

```csharp
public static const System.String kAssetDbProtocol;
```

- `private static const System.String kCacheAssetTask`  

```csharp
private static const System.String kCacheAssetTask;
```

- `public static const System.String kSaveSettingsTask`  

```csharp
public static const System.String kSaveSettingsTask;
```

- `public static const System.String kCacheAssetsTaskName`  

```csharp
public static const System.String kCacheAssetsTaskName;
```


## Properties

- `public System.Int32 mipBias { get }`  

```csharp
public System.Int32 mipBias { get; }
```

- `public System.Boolean isServingHttp { get }`  

```csharp
public System.Boolean isServingHttp { get; }
```

- `public System.Int32 httpPort { get }`  

```csharp
public System.Int32 httpPort { get; }
```

- `public Colossal.IO.AssetDatabase.AssetDatabaseResources resources { get }`  

```csharp
public Colossal.IO.AssetDatabase.AssetDatabaseResources resources { get; }
```

- `public System.Boolean isCached { get }`  

```csharp
public System.Boolean isCached { get; }
```

- `public Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode autoReloadMode { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode autoReloadMode { get; set; }
```

- `public Colossal.EventBroadcaster<Colossal.IO.AssetDatabase.AssetChangedEventArgs> onAssetDatabaseChanged { get }`  

```csharp
public Colossal.EventBroadcaster<Colossal.IO.AssetDatabase.AssetChangedEventArgs> onAssetDatabaseChanged { get; }
```

- `public System.Boolean areNotificationsEnabled { get }`  

```csharp
public System.Boolean areNotificationsEnabled { get; }
```

- `public static System.Boolean exists { get }`  

```csharp
public static System.Boolean exists { get; }
```

- `public static Colossal.IO.AssetDatabase.AssetDatabase global { get }`  

```csharp
public static Colossal.IO.AssetDatabase.AssetDatabase global { get; }
```

- `public static Colossal.IO.AssetDatabase.ILocalAssetDatabase game { get }`  

```csharp
public static Colossal.IO.AssetDatabase.ILocalAssetDatabase game { get; }
```

- `public static Colossal.IO.AssetDatabase.ILocalAssetDatabase user { get }`  

```csharp
public static Colossal.IO.AssetDatabase.ILocalAssetDatabase user { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.IO.AssetDatabase.IAssetDatabase> databases { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.IO.AssetDatabase.IAssetDatabase> databases { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.String hostname { get }`  

```csharp
public System.String hostname { get; }
```

- `public System.String rootPath { get }`  

```csharp
public System.String rootPath { get; }
```

- `public System.Int32 count { get }`  

```csharp
public System.Int32 count { get; }
```


## Constructors

- `private AssetDatabase()`  

```csharp
private AssetDatabase();
```


## Methods

- `private <GetAssets>b__92_0<T>(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <GetAssets>b__92_0<T>(System.TimeSpan t);
```

- `private <SaveSettings>b__95_0() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task <SaveSettings>b__95_0();
```

- `private <TryGetAsset>b__76_0<T>(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <TryGetAsset>b__76_0<T>(System.TimeSpan t);
```

- `public AllAssets() : System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.IAssetData>`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.IAssetData> AllAssets();
```

- `public AreAssetsWarningsEnabled(Colossal.IO.AssetDatabase.AssetData asset) : System.Boolean`  

```csharp
public System.Boolean AreAssetsWarningsEnabled(Colossal.IO.AssetDatabase.AssetData asset);
```

- `public CacheAssets(System.Threading.CancellationToken ct) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task CacheAssets(System.Threading.CancellationToken ct);
```

- `public CacheAssets(System.Boolean priorityAssets, System.Threading.CancellationToken ct) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task CacheAssets(System.Boolean priorityAssets, System.Threading.CancellationToken ct);
```

- `public static ClearAsyncReadManagerCacheHack() : System.Void`  

```csharp
public static System.Void ClearAsyncReadManagerCacheHack();
```

- `public ClearCache() : System.Void`  

```csharp
public System.Void ClearCache();
```

- `private static CreateAsyncReadManagerCacheHack() : System.Void`  

```csharp
private static System.Void CreateAsyncReadManagerCacheHack();
```

- `public DeleteAsset(Colossal.Hash128 guid) : System.Void`  

```csharp
public System.Void DeleteAsset(Colossal.Hash128 guid);
```

- `public DeleteAsset<T>(T asset) : System.Void`  

```csharp
public System.Void DeleteAsset<T>(T asset);
```

- `public DisableNotificationsScoped() : Colossal.IO.AssetDatabase.DisableNotificationsScoped`  

```csharp
public Colossal.IO.AssetDatabase.DisableNotificationsScoped DisableNotificationsScoped();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public EnableNotifications(System.Boolean enable) : System.Void`  

```csharp
public System.Void EnableNotifications(System.Boolean enable);
```

- `public GetAsset<TAssetData>(System.Uri uri) : TAssetData`  

```csharp
public TAssetData GetAsset<TAssetData>(System.Uri uri);
```

- `public GetAsset<TAssetData>(System.String uri) : TAssetData`  

```csharp
public TAssetData GetAsset<TAssetData>(System.String uri);
```

- `public GetAsset<TAssetData>(Colossal.Hash128 guid) : TAssetData`  

```csharp
public TAssetData GetAsset<TAssetData>(Colossal.Hash128 guid);
```

- `public GetAsset<T>(Colossal.IO.AssetDatabase.SearchFilter<T> filter) : T`  

```csharp
public T GetAsset<T>(Colossal.IO.AssetDatabase.SearchFilter<T> filter);
```

- `public GetAsset(System.Uri uri) : Colossal.IO.AssetDatabase.IAssetData`  

```csharp
public Colossal.IO.AssetDatabase.IAssetData GetAsset(System.Uri uri);
```

- `public GetAsset(System.String uri) : Colossal.IO.AssetDatabase.IAssetData`  

```csharp
public Colossal.IO.AssetDatabase.IAssetData GetAsset(System.String uri);
```

- `public GetAsset(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.IAssetData`  

```csharp
public Colossal.IO.AssetDatabase.IAssetData GetAsset(Colossal.Hash128 guid);
```

- `public GetAsset(Colossal.IO.AssetDatabase.SearchFilter<Colossal.IO.AssetDatabase.IAssetData> filter = null) : Colossal.IO.AssetDatabase.IAssetData`  

```csharp
public Colossal.IO.AssetDatabase.IAssetData GetAsset(Colossal.IO.AssetDatabase.SearchFilter<Colossal.IO.AssetDatabase.IAssetData> filter);
```

- `public GetAssets<T>(Colossal.IO.AssetDatabase.SearchFilter<T> filter = null) : System.Collections.Generic.IEnumerable<T>`  

```csharp
public System.Collections.Generic.IEnumerable<T> GetAssets<T>(Colossal.IO.AssetDatabase.SearchFilter<T> filter);
```

- `public GetAvailableRemoteStorages() : System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.IO.AssetDatabase.ILocalAssetDatabase>>`  

```csharp
public System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.IO.AssetDatabase.ILocalAssetDatabase>> GetAvailableRemoteStorages();
```

- `public static GetTransient(System.Int64 maxChunkSize = 0, System.String rootPath = null) : Colossal.IO.AssetDatabase.ILocalAssetDatabase`  

```csharp
public static Colossal.IO.AssetDatabase.ILocalAssetDatabase GetTransient(System.Int64 maxChunkSize, System.String rootPath);
```

- `public LoadSettings(System.String name, System.Object obj, System.Object defaultObj = null) : System.Void`  

```csharp
public System.Void LoadSettings(System.String name, System.Object obj, System.Object defaultObj);
```

- `public LoadSettings<T>(System.String name, System.Action<T, Colossal.IO.AssetDatabase.SourceMeta> obj) : System.Void`  

```csharp
public System.Void LoadSettings<T>(System.String name, System.Action<T, Colossal.IO.AssetDatabase.SourceMeta> obj);
```

- `private NotifyChange(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private System.Void NotifyChange(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
```

- `private OnPriorityDataCached() : System.Void`  

```csharp
private System.Void OnPriorityDataCached();
```

- `public RegisterDatabase(Colossal.IO.AssetDatabase.IAssetDatabase database) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task RegisterDatabase(Colossal.IO.AssetDatabase.IAssetDatabase database);
```

- `public ResaveCache() : System.Threading.Tasks.Task<System.String>`  

```csharp
public System.Threading.Tasks.Task<System.String> ResaveCache();
```

- `public SaveCache() : System.Void`  

```csharp
public System.Void SaveCache();
```

- `public SaveSettings() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task SaveSettings();
```

- `public SetSettingsConfiguration(System.Boolean saveAll = False, System.Boolean cleanupSettings = False) : System.Void`  

```csharp
public System.Void SetSettingsConfiguration(System.Boolean saveAll, System.Boolean cleanupSettings);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `public TryGetAsset<TAssetData>(System.Uri uri, TAssetData& asset) : System.Boolean`  

```csharp
public System.Boolean TryGetAsset<TAssetData>(System.Uri uri, TAssetData& asset);
```

- `public TryGetAsset<TAssetData>(System.String uri, TAssetData& asset) : System.Boolean`  

```csharp
public System.Boolean TryGetAsset<TAssetData>(System.String uri, TAssetData& asset);
```

- `public TryGetAsset<TAssetData>(Colossal.Hash128 guid, TAssetData& asset) : System.Boolean`  

```csharp
public System.Boolean TryGetAsset<TAssetData>(Colossal.Hash128 guid, TAssetData& asset);
```

- `public TryGetAsset<T>(Colossal.IO.AssetDatabase.SearchFilter<T> filter, T& asset) : System.Boolean`  

```csharp
public System.Boolean TryGetAsset<T>(Colossal.IO.AssetDatabase.SearchFilter<T> filter, T& asset);
```

- `public TryGetAsset(System.Uri uri, Colossal.IO.AssetDatabase.IAssetData& asset) : System.Boolean`  

```csharp
public System.Boolean TryGetAsset(System.Uri uri, Colossal.IO.AssetDatabase.IAssetData& asset);
```

- `public TryGetAsset(System.String uri, Colossal.IO.AssetDatabase.IAssetData& asset) : System.Boolean`  

```csharp
public System.Boolean TryGetAsset(System.String uri, Colossal.IO.AssetDatabase.IAssetData& asset);
```

- `public TryGetAsset(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.IAssetData& asset) : System.Boolean`  

```csharp
public System.Boolean TryGetAsset(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.IAssetData& asset);
```

- `public TryGetAsset(Colossal.IO.AssetDatabase.SearchFilter<Colossal.IO.AssetDatabase.IAssetData> filter, Colossal.IO.AssetDatabase.IAssetData& asset) : System.Boolean`  

```csharp
public System.Boolean TryGetAsset(Colossal.IO.AssetDatabase.SearchFilter<Colossal.IO.AssetDatabase.IAssetData> filter, Colossal.IO.AssetDatabase.IAssetData& asset);
```

- `private TryGetAssetInternal<TAssetData>(System.Uri uri, TAssetData& asset, System.Boolean throws) : System.Boolean`  

```csharp
private System.Boolean TryGetAssetInternal<TAssetData>(System.Uri uri, TAssetData& asset, System.Boolean throws);
```

- `public TryGetDatabase(System.Uri uri, Colossal.IO.AssetDatabase.IAssetDatabase& database) : System.Boolean`  

```csharp
public System.Boolean TryGetDatabase(System.Uri uri, Colossal.IO.AssetDatabase.IAssetDatabase& database);
```

- `public TryGetDatabase(System.String name, Colossal.IO.AssetDatabase.IAssetDatabase& database) : System.Boolean`  

```csharp
public System.Boolean TryGetDatabase(System.String name, Colossal.IO.AssetDatabase.IAssetDatabase& database);
```

- `public UnloadAllAssets() : System.Void`  

```csharp
public System.Void UnloadAllAssets();
```

- `public UnregisterDatabase(Colossal.IO.AssetDatabase.IAssetDatabase database) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> UnregisterDatabase(Colossal.IO.AssetDatabase.IAssetDatabase database);
```


## Nested types

- `Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode`  
- `Colossal.IO.AssetDatabase.AssetDatabase+SettingsConfiguration`  
- `Colossal.IO.AssetDatabase.AssetDatabase+Settings`  
- `Colossal.IO.AssetDatabase.AssetDatabase+LogSettingsProvider`  
- `Colossal.IO.AssetDatabase.AssetDatabase+<<SaveSettings>b__95_0>d`  
- `Colossal.IO.AssetDatabase.AssetDatabase+<>c`  
- `Colossal.IO.AssetDatabase.AssetDatabase+<>c__DisplayClass100_0`  
- `Colossal.IO.AssetDatabase.AssetDatabase+<AllAssets>d__91`  
- `Colossal.IO.AssetDatabase.AssetDatabase+<CacheAssets>d__100`  
- `Colossal.IO.AssetDatabase.AssetDatabase+<CacheAssets>d__98`  
- `Colossal.IO.AssetDatabase.AssetDatabase+<GetAssets>d__92<T>`  
- `Colossal.IO.AssetDatabase.AssetDatabase+<GetAvailableRemoteStorages>d__103`  
- `Colossal.IO.AssetDatabase.AssetDatabase+<RegisterDatabase>d__60`  
- `Colossal.IO.AssetDatabase.AssetDatabase+<ResaveCache>d__19`  
- `Colossal.IO.AssetDatabase.AssetDatabase+<SaveSettings>d__95`  
- `Colossal.IO.AssetDatabase.AssetDatabase+<UnregisterDatabase>d__61`  

