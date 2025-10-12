# Game.Modding.ModManager

**Assembly:** `Game`  
**Namespace:** `Game.Modding`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerable<Game.Modding.ModManager+ModInfo>`, `System.Collections.IEnumerable`, `System.IDisposable`  

## Fields

- `private readonly System.Collections.Generic.List<Game.Modding.ModManager+ModInfo> m_ModsInfos`  
- `private System.Boolean m_Disabled`  
- `private System.Boolean m_Initialized`  
- `private System.Boolean m_IsInProgress`  
- `private System.Boolean <restartRequired>k__BackingField`  
- `private static Colossal.Logging.ILog log`  
- `private static const System.String kBurstSuffix`  

## Properties

- `public System.Boolean isInitialized { get }`  
- `public System.Boolean restartRequired { get; private set }`  

## Constructors

- `private ModManager()`  
- `public ModManager(System.Boolean disabled)`  

## Methods

- `private <RequireRestart>b__27_0() : System.Void`  
- `private <RequireRestart>b__27_1(System.Int32 msg) : System.Void`  
- `public AddUIModule(Colossal.IO.AssetDatabase.UIModuleAsset uiModule) : System.Void`  
- `public static AreModsEnabled() : System.Boolean`  
- `public Dispose() : System.Void`  
- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Game.Modding.ModManager+ModInfo>`  
- `public static GetModsEnabled() : System.String[]`  
- `public Initialize(Game.UpdateSystem updateSystem) : System.Void`  
- `private InitializeMods(Game.UpdateSystem updateSystem) : System.Void`  
- `private InitializeUIModules() : System.Void`  
- `public ListModsEnabled() : System.String[]`  
- `private RegisterMods() : System.Void`  
- `public RemoveUIModule(Colossal.IO.AssetDatabase.UIModuleAsset uiModule) : System.Void`  
- `public RequireRestart() : System.Void`  
- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  
- `public TryGetExecutableAsset(Game.Modding.IMod mod, Colossal.IO.AssetDatabase.ExecutableAsset& asset) : System.Boolean`  
- `public TryGetExecutableAsset(System.Reflection.Assembly assembly, Colossal.IO.AssetDatabase.ExecutableAsset& asset) : System.Boolean`  

## Nested types

- `Game.Modding.ModManager+ModInfo`  
- `Game.Modding.ModManager+<>c`  
- `Game.Modding.ModManager+<>c__DisplayClass16_0`  
- `Game.Modding.ModManager+<>c__DisplayClass18_0`  
- `Game.Modding.ModManager+<>c__DisplayClass22_0`  

