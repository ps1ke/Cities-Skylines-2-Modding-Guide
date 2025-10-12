# Colossal.IO.AssetDatabase.UIModuleAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`  

## Fields

- `private Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo m_ModuleInfo`  
- `private System.Action<Colossal.IO.AssetDatabase.UIModuleAsset, System.Boolean> onActivePlaysetChanged`  
- `private System.Boolean m_IsInActivePlayset`  
- `private Colossal.PSI.Common.Mod <mod>k__BackingField`  
- `public static const System.String kExtension`  
- `private static const System.String kModuleIdentifier`  

## Properties

- `public System.String name { get }`  
- `public Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo moduleInfo { get }`  
- `public System.Boolean isValidModule { get }`  
- `public System.Boolean isLocal { get }`  
- `public System.String couiPath { get }`  
- `public System.Boolean isInActivePlayset { get; set }`  
- `public System.Boolean isEnabled { get }`  
- `public Colossal.PSI.Common.Mod mod { get; private set }`  

## Constructors

- `public UIModuleAsset()`  

## Methods

- `private static ParseModuleInfo(System.IO.StreamReader reader) : Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo`  
- `public virtual PostCreate() : System.Void`  
- `private static ProcessLine(System.String line, Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo& moduleInfo) : System.Boolean`  

## Events

- `onActivePlaysetChanged` : `System.Action<Colossal.IO.AssetDatabase.UIModuleAsset, System.Boolean>`  

## Nested types

- `Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo`  
- `Colossal.IO.AssetDatabase.UIModuleAsset+<>c`  

