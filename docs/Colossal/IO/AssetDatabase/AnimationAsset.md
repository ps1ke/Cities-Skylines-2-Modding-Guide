# Colossal.IO.AssetDatabase.AnimationAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.IAssetData<Colossal.Animations.AnimationClip>`  

## Fields

- `private Colossal.Animations.AnimationClip m_Data`  
- `private Unity.IO.LowLevel.Unsafe.ReadHandle m_AsyncReadHandle`  
- `private Unity.Collections.NativeArray<System.Byte> m_AsyncLoadBuffer`  
- `public static const System.String kExtension`  
- `public static const System.UInt16 kFormatVersion`  

## Properties

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  

## Constructors

- `public AnimationAsset()`  

## Methods

- `private <AsyncLoad>b__10_0(System.TimeSpan t) : System.Void`  
- `private <Load>b__8_0(System.TimeSpan t) : System.Void`  
- `private <Save>b__11_0(System.TimeSpan t) : System.Void`  
- `public AsyncLoad(Colossal.Animations.AnimationClip& clip) : System.Boolean`  
- `public Load(System.Int32 framerateBias = -1) : Colossal.Animations.AnimationClip`  
- `private Load(System.IO.Stream stream) : System.Void`  
- `public virtual Save(System.Boolean force = False) : System.Void`  
- `public SetData(Colossal.Animations.AnimationClip animation) : System.Void`  
- `public virtual Unload(System.Boolean force = False) : System.Void`  

