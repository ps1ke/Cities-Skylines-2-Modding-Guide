# Colossal.IO.AssetDatabase.ParadoxModsDataSource

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.FileSystemDataSource`  
**Implements:** `Colossal.IO.AssetDatabase.IDataSourceProvider`, `System.IDisposable`  

## Fields

- `private System.Boolean m_DataCached`  
- `private readonly Colossal.PSI.PdxSdk.PdxSdkPlatform m_PlatformManager`  
- `private readonly System.String m_RootPath`  
- `private System.Collections.Generic.HashSet<Colossal.PSI.Common.Mod> m_ActiveMods`  
- `private System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.PSI.Common.Mod> m_PlatformInfoMap`  
- `private System.Action<Colossal.Hash128, System.Boolean> onEntryIsInActivePlaysetChanged`  
- `private System.Action onAfterActivePlaysetOrModStatusChanged`  
- `private static const System.String kScheme`  

## Properties

- `public System.String remoteStorageSourceName { get }`  

## Constructors

- `public ParadoxModsDataSource(Colossal.IO.AssetDatabase.IAssetFactory assetFactory)`  

## Methods

- `private <Populate>b__17_0(System.TimeSpan t) : System.Void`  
- `public virtual DeleteEntry(Colossal.Hash128 guid) : System.Void`  
- `public virtual Dispose() : System.Void`  
- `public GetActiveMods() : System.Collections.Generic.IReadOnlyCollection<Colossal.PSI.Common.Mod>`  
- `public virtual GetMeta(Colossal.Hash128 guid) : Colossal.IO.AssetDatabase.SourceMeta`  
- `private static GetRootPath() : System.String`  
- `private OnActivePlaysetChanged() : System.Threading.Tasks.Task`  
- `private OnActivePlaysetChangedAsync() : System.Void`  
- `private OnModStatusChanged(Colossal.PSI.Common.Mod mod, System.Boolean enable) : System.Threading.Tasks.Task`  
- `private OnModStatusChangedAsync(Colossal.PSI.Common.Mod changedMod, System.Boolean enable) : System.Void`  
- `public Populate() : System.Threading.Tasks.Task`  
- `public virtual PopulateDataSource(System.Boolean priorityData, System.Threading.CancellationToken ct, Colossal.TaskProgress progress) : System.Threading.Tasks.Task<System.Collections.Generic.IReadOnlyCollection<System.ValueTuple<System.Type, Colossal.IO.AssetDatabase.Identifier>>>`  
- `public PopulateMetadata(System.String modAbsolutePath) : System.Threading.Tasks.Task`  
- `public TryGetMod(System.String path, Colossal.PSI.Common.Mod& mod) : System.Boolean`  

## Events

- `onEntryIsInActivePlaysetChanged` : `System.Action<Colossal.Hash128, System.Boolean>`  
- `onAfterActivePlaysetOrModStatusChanged` : `System.Action`  

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

