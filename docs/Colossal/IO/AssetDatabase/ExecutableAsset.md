# Colossal.IO.AssetDatabase.ExecutableAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`  

## Fields

- `private System.Action<Colossal.IO.AssetDatabase.ExecutableAsset, System.Boolean> onActivePlaysetChanged`  
- `private System.Boolean m_IsInActivePlayset`  
- `private Colossal.PSI.Common.Mod <mod>k__BackingField`  
- `private Colossal.Mono.Cecil.AssemblyDefinition <definition>k__BackingField`  
- `private System.Reflection.Assembly <assembly>k__BackingField`  
- `private System.Boolean <isBursted>k__BackingField`  
- `private System.Boolean <isMod>k__BackingField`  
- `private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.ExecutableAsset> m_ReferenceOf`  
- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.ExecutableAsset> m_References`  
- `private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.ExecutableAsset> m_Duplicates`  
- `private System.Boolean m_IsLoading`  
- `private static readonly System.Collections.Generic.Dictionary<Colossal.Mono.Cecil.AssemblyDefinition, Colossal.IO.AssetDatabase.ExecutableAsset> sAssemblyMap`  
- `private static Colossal.Logging.ILog moddingLog`  
- `public static readonly System.String sManagedLocation`  
- `private static const System.String kBurstSuffix`  
- `public static const System.String kExtension`  

## Properties

- `public System.Boolean isInActivePlayset { get; set }`  
- `public System.Boolean isEnabled { get }`  
- `public Colossal.PSI.Common.Mod mod { get; private set }`  
- `public Colossal.Mono.Cecil.AssemblyDefinition definition { get; private set }`  
- `public System.Reflection.Assembly assembly { get; private set }`  
- `public System.Boolean isBursted { get; private set }`  
- `public System.Boolean isILAssembly { get }`  
- `public System.Version version { get }`  
- `public System.Boolean isLoaded { get }`  
- `public System.Boolean isLocal { get }`  
- `public System.Boolean isMod { get; private set }`  
- `public System.String name { get }`  
- `public System.String fullName { get }`  
- `public System.Boolean isReference { get }`  
- `public System.Boolean isRequired { get }`  
- `public System.Boolean canBeLoaded { get }`  
- `public System.Boolean isUnique { get }`  
- `public System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.IO.AssetDatabase.ExecutableAsset> references { get }`  

## Constructors

- `public ExecutableAsset()`  

## Methods

- `private <GetUniqueVersionAsset>b__59_0(Colossal.IO.AssetDatabase.ExecutableAsset d) : System.Boolean`  
- `private AddDuplicates(Colossal.IO.AssetDatabase.ExecutableAsset[] duplicates) : System.Void`  
- `private AddReference(Colossal.Mono.Cecil.AssemblyNameReference assemblyName, Colossal.IO.AssetDatabase.ExecutableAsset reference) : System.Void`  
- `public static GetModAssets(System.Type modInterfaceType) : Colossal.IO.AssetDatabase.ExecutableAsset[]`  
- `public GetUniqueVersionAsset() : Colossal.IO.AssetDatabase.ExecutableAsset`  
- `public LoadAssembly(System.Action<System.Reflection.Assembly> afterLoadAction, Colossal.IO.AssetDatabase.ExecutableAsset& uniqueAsset) : System.Void`  
- `private LoadAssemblyImpl(System.Action<System.Reflection.Assembly> afterLoadAction) : System.Void`  
- `public virtual PostCreate() : System.Void`  
- `public static TryGetAsset(Colossal.Mono.Cecil.AssemblyDefinition definition, Colossal.IO.AssetDatabase.ExecutableAsset& asset) : System.Boolean`  
- `public virtual Unload(System.Boolean force = False) : System.Void`  

## Events

- `onActivePlaysetChanged` : `System.Action<Colossal.IO.AssetDatabase.ExecutableAsset, System.Boolean>`  

## Nested types

- `Colossal.IO.AssetDatabase.ExecutableAsset+ExecutableResolver`  
- `Colossal.IO.AssetDatabase.ExecutableAsset+LoadExecutableException`  
- `Colossal.IO.AssetDatabase.ExecutableAsset+LoadExecutableReferenceException`  
- `Colossal.IO.AssetDatabase.ExecutableAsset+<>c`  
- `Colossal.IO.AssetDatabase.ExecutableAsset+<>c__DisplayClass68_0`  

