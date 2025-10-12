# Colossal.IO.AssetDatabase.SettingAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SettingAsset+Fragment>`, `System.Collections.IEnumerable`  

## Fields

- `private readonly System.String <name>k__BackingField`  
- `private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.SettingAsset+Fragment> m_SettingFragments`  
- `public static const System.String kExtension`  
- `public static const System.String kExtensionBackup`  

## Properties

- `public System.String name { get }`  

## Constructors

- `public SettingAsset(System.String name)`  

## Methods

- `private <Save>b__20_0(System.TimeSpan t) : System.Void`  
- `public AddFragment(Colossal.Hash128 guid, System.String fragmentStr) : System.Void`  
- `public AddFragment(Colossal.IO.AssetDatabase.SettingAsset+Fragment fragment) : System.Void`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public Equals(Colossal.IO.AssetDatabase.SettingAsset other) : System.Boolean`  
- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Colossal.IO.AssetDatabase.SettingAsset+Fragment>`  
- `public virtual GetHashCode() : System.Int32`  
- `private IsEmptyJSON(System.String jsonString) : System.Boolean`  
- `public virtual Save(System.Boolean force = False) : System.Void`  
- `internal Save(System.Boolean saveAll, System.Boolean cleanupSettings, Colossal.IO.AssetDatabase.Internal.SaveSettingsHelper helper) : System.Threading.Tasks.Task`  
- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  
- `private TrimJSON(System.String input) : System.String`  

## Nested types

- `Colossal.IO.AssetDatabase.SettingAsset+Fragment`  
- `Colossal.IO.AssetDatabase.SettingAsset+<Save>d__17`  
- `Colossal.IO.AssetDatabase.SettingAsset+<Save>d__20`  

