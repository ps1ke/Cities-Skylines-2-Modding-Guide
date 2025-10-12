# Colossal.IO.AssetDatabase.AudioAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`  

## Fields

- `private UnityEngine.AudioClip m_Instance`  
- `private System.Int32 m_InstanceRefCount`  
- `private System.Double <durationMs>k__BackingField`  
- `private System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.AudioAsset+Metatag, System.String> m_Metatags`  
- `private System.Double <loopStart>k__BackingField`  
- `private System.Double <loopEnd>k__BackingField`  
- `private System.Double <alternativeStart>k__BackingField`  
- `private System.Single <fadeoutTime>k__BackingField`  
- `public static const System.String kExtension`  

## Properties

- `public System.Double durationMs { get; private set }`  
- `public System.Double loopStart { get; private set }`  
- `public System.Double loopEnd { get; private set }`  
- `public System.Double loopDuration { get }`  
- `public System.Double alternativeStart { get; private set }`  
- `public System.Boolean hasLoop { get }`  
- `public System.Boolean hasAlternativeStart { get }`  
- `public System.Single fadeoutTime { get; private set }`  
- `public Colossal.IO.AssetDatabase.LoadState state { get }`  
- `public System.Collections.Generic.IReadOnlyDictionary<Colossal.IO.AssetDatabase.AudioAsset+Metatag, System.String> metaTags { get }`  

## Constructors

- `public AudioAsset()`  

## Methods

- `private <LoadAsyncFile>b__44_0(System.TimeSpan t) : System.Void`  
- `private AddMetaTag(Colossal.IO.AssetDatabase.AudioAsset+Metatag tag, System.String value) : System.Void`  
- `private AddMetaTag(Colossal.IO.AssetDatabase.AudioAsset+Metatag tag, ATL.Track trackMeta, System.String oggTag) : System.Void`  
- `private static GetExtendedTag(ATL.Track trackMeta, System.String tag) : System.String`  
- `public GetMetaTag(Colossal.IO.AssetDatabase.AudioAsset+Metatag tag) : System.String`  
- `private static GetTimeTag(ATL.Track trackMeta, System.String tag, System.Double& time) : System.Boolean`  
- `private static GetTimeTag(ATL.Track trackMeta, System.String tag, System.Single& time) : System.Boolean`  
- `public LoadAsync(System.Boolean useCached = True, System.Boolean streamAudio = True, UnityEngine.AudioType audioType = OGGVORBIS) : System.Threading.Tasks.Task<UnityEngine.AudioClip>`  
- `public LoadAsyncFile(System.Boolean useCached = True, System.Boolean streamAudio = True, UnityEngine.AudioType audioType = OGGVORBIS) : System.Threading.Tasks.Task<UnityEngine.AudioClip>`  
- `public virtual PostCreate() : System.Void`  
- `public virtual Unload(System.Boolean force = False) : System.Void`  
- `private UpdateMetaTags() : System.Void`  

## Nested types

- `Colossal.IO.AssetDatabase.AudioAsset+Metatag`  
- `Colossal.IO.AssetDatabase.AudioAsset+<LoadAsync>d__43`  
- `Colossal.IO.AssetDatabase.AudioAsset+<LoadAsyncFile>d__44`  

