# Colossal.IO.AssetDatabase.AssetDatabase

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetDatabase`, `System.IDisposable`  

## Fields

- `private Colossal.IO.AssetDatabase.HTTP.DBServer m_HttpServer`  
- `private Colossal.IO.AssetDatabase.AssetDatabaseResources m_Resources`  
- `private readonly Colossal.IO.AssetDatabase.AssetDatabase+SettingsConfiguration m_SettingsConfiguration`  
- `private Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode <autoReloadMode>k__BackingField`  
- `private readonly Colossal.EventBroadcaster<Colossal.IO.AssetDatabase.AssetChangedEventArgs> <onAssetDatabaseChanged>k__BackingField`  
- `private readonly System.Collections.Generic.Dictionary<System.Type, Colossal.IO.AssetDatabase.IAssetData> m_PendingChangeTypes`  
- `private System.Boolean m_NotificationsEnabled`  
- `private readonly System.Threading.SemaphoreSlim m_DatabasesLock`  
- `private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.IAssetDatabaseInternal> m_Databases`  
- `private Colossal.IO.AssetDatabase.AssetDatabase+Settings m_Settings`  
- `private static Colossal.Logging.ILog log`  
- `private static Colossal.IO.AssetDatabase.AssetDatabase s_Instance`  
- `private static Colossal.IO.AssetDatabase.Game s_GameDescriptor`  
- `public static const System.String kAssetDbScheme`  
- `public static const System.String kAssetDbProtocol`  
- `private static const System.String kCacheAssetTask`  
- `public static const System.String kSaveSettingsTask`  
- `public static const System.String kCacheAssetsTaskName`  

## Properties

- `public System.Int32 mipBias { get }`  
- `public System.Boolean isServingHttp { get }`  
- `public System.Int32 httpPort { get }`  
- `public Colossal.IO.AssetDatabase.AssetDatabaseResources resources { get }`  
- `public System.Boolean isCached { get }`  
- `public Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode autoReloadMode { get; set }`  
- `public Colossal.EventBroadcaster<Colossal.IO.AssetDatabase.AssetChangedEventArgs> onAssetDatabaseChanged { get }`  
- `public System.Boolean areNotificationsEnabled { get }`  
- `public static System.Boolean exists { get }`  
- `public static Colossal.IO.AssetDatabase.AssetDatabase global { get }`  
- `public static Colossal.IO.AssetDatabase.ILocalAssetDatabase game { get }`  
- `public static Colossal.IO.AssetDatabase.ILocalAssetDatabase user { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<Colossal.IO.AssetDatabase.IAssetDatabase> databases { get }`  
- `public System.String name { get }`  
- `public System.String hostname { get }`  
- `public System.String rootPath { get }`  
- `public System.Int32 count { get }`  

## Constructors

- `private AssetDatabase()`  

## Methods

- `private <GetAssets>b__92_0<T>(System.TimeSpan t) : System.Void`  
- `private <SaveSettings>b__95_0() : System.Threading.Tasks.Task`  
- `private <TryGetAsset>b__76_0<T>(System.TimeSpan t) : System.Void`  
- `public AllAssets() : System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.IAssetData>`  
- `public AreAssetsWarningsEnabled(Colossal.IO.AssetDatabase.AssetData asset) : System.Boolean`  
- `public CacheAssets(System.Threading.CancellationToken ct) : System.Threading.Tasks.Task`  
- `public CacheAssets(System.Boolean priorityAssets, System.Threading.CancellationToken ct) : System.Threading.Tasks.Task`  
- `public static ClearAsyncReadManagerCacheHack() : System.Void`  
- `public ClearCache() : System.Void`  
- `private static CreateAsyncReadManagerCacheHack() : System.Void`  
- `public DeleteAsset(Colossal.Hash128 guid) : System.Void`  
- `public DeleteAsset<T>(T asset) : System.Void`  
- `public DisableNotificationsScoped() : Colossal.IO.AssetDatabase.DisableNotificationsScoped`  
- `public Dispose() : System.Void`  
- `public EnableNotifications(System.Boolean enable) : System.Void`  
- `public GetAsset<TAssetData>(System.Uri uri) : TAssetData`  
- `public GetAsset<TAssetData>(System.String uri) : TAssetData`  
- `public GetAsset<TAssetData>(Colossal.Hash128 guid) : TAssetData`  
- `public GetAsset<T>(Colossal.IO.AssetDatabase.SearchFilter<T> filter) : T`  
- `public GetAsset(System.Uri uri) : Colossal.IO.AssetDatabase.IAssetData`  
- `public GetAsset(System.String uri) : Colossal.IO.AssetDatabase.IAssetData`  
- `public GetAsset(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.IAssetData`  
- `public GetAsset(Colossal.IO.AssetDatabase.SearchFilter<Colossal.IO.AssetDatabase.IAssetData> filter = null) : Colossal.IO.AssetDatabase.IAssetData`  
- `public GetAssets<T>(Colossal.IO.AssetDatabase.SearchFilter<T> filter = null) : System.Collections.Generic.IEnumerable<T>`  
- `public GetAvailableRemoteStorages() : System.Collections.Generic.IEnumerable<System.ValueTuple<System.String, Colossal.IO.AssetDatabase.ILocalAssetDatabase>>`  
- `public static GetTransient(System.Int64 maxChunkSize = 0, System.String rootPath = null) : Colossal.IO.AssetDatabase.ILocalAssetDatabase`  
- `public LoadSettings(System.String name, System.Object obj, System.Object defaultObj = null) : System.Void`  
- `public LoadSettings<T>(System.String name, System.Action<T, Colossal.IO.AssetDatabase.SourceMeta> obj) : System.Void`  
- `private NotifyChange(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  
- `private OnPriorityDataCached() : System.Void`  
- `public RegisterDatabase(Colossal.IO.AssetDatabase.IAssetDatabase database) : System.Threading.Tasks.Task`  
- `public ResaveCache() : System.Threading.Tasks.Task<System.String>`  
- `public SaveCache() : System.Void`  
- `public SaveSettings() : System.Threading.Tasks.Task`  
- `public SetSettingsConfiguration(System.Boolean saveAll = False, System.Boolean cleanupSettings = False) : System.Void`  
- `public virtual ToString() : System.String`  
- `public TryGetAsset<TAssetData>(System.Uri uri, TAssetData& asset) : System.Boolean`  
- `public TryGetAsset<TAssetData>(System.String uri, TAssetData& asset) : System.Boolean`  
- `public TryGetAsset<TAssetData>(Colossal.Hash128 guid, TAssetData& asset) : System.Boolean`  
- `public TryGetAsset<T>(Colossal.IO.AssetDatabase.SearchFilter<T> filter, T& asset) : System.Boolean`  
- `public TryGetAsset(System.Uri uri, Colossal.IO.AssetDatabase.IAssetData& asset) : System.Boolean`  
- `public TryGetAsset(System.String uri, Colossal.IO.AssetDatabase.IAssetData& asset) : System.Boolean`  
- `public TryGetAsset(Colossal.Hash128 guid, Colossal.IO.AssetDatabase.IAssetData& asset) : System.Boolean`  
- `public TryGetAsset(Colossal.IO.AssetDatabase.SearchFilter<Colossal.IO.AssetDatabase.IAssetData> filter, Colossal.IO.AssetDatabase.IAssetData& asset) : System.Boolean`  
- `private TryGetAssetInternal<TAssetData>(System.Uri uri, TAssetData& asset, System.Boolean throws) : System.Boolean`  
- `public TryGetDatabase(System.Uri uri, Colossal.IO.AssetDatabase.IAssetDatabase& database) : System.Boolean`  
- `public TryGetDatabase(System.String name, Colossal.IO.AssetDatabase.IAssetDatabase& database) : System.Boolean`  
- `public UnloadAllAssets() : System.Void`  
- `public UnregisterDatabase(Colossal.IO.AssetDatabase.IAssetDatabase database) : System.Threading.Tasks.Task<System.Boolean>`  

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

