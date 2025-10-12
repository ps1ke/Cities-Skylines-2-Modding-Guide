# Colossal.AssetPipeline.Surface

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`, `Colossal.AssetPipeline.ISurface`  

## Fields

- `public readonly System.String name`  
- `public readonly System.Collections.Generic.Dictionary<System.String, Colossal.AssetPipeline.Importers.TextureImporter+Texture> bakingTextures`  
- `public readonly System.Collections.Generic.Dictionary<System.String, Colossal.AssetPipeline.Importers.TextureImporter+ITexture> textures`  
- `public readonly System.Collections.Generic.Dictionary<System.String, System.Single> floats`  
- `public readonly System.Collections.Generic.Dictionary<System.String, System.Int32> ints`  
- `public readonly System.Collections.Generic.Dictionary<System.String, UnityEngine.Vector4> vectors`  
- `public readonly System.Collections.Generic.Dictionary<System.String, UnityEngine.Color> colors`  
- `public readonly System.Collections.Generic.HashSet<System.String> keywords`  
- `public readonly System.Collections.Generic.List<Colossal.AssetPipeline.Surface+EmissiveLayer> emissiveLayers`  
- `private System.String m_Template`  
- `private UnityEngine.Material m_CachedObject`  

## Properties

- `public System.String template { get; set }`  
- `public System.Boolean isValid { get }`  
- `public System.Boolean isImpostor { get }`  

## Constructors

- `public Surface(System.String name, System.String template = null)`  

## Methods

- `public AddBakingTexture(System.String name, Colossal.AssetPipeline.Importers.TextureImporter+Texture texture) : System.Void`  
- `public AddKeyword(System.String keyword) : System.Void`  
- `public AddProperty(System.String name, System.Single value) : System.Void`  
- `public AddProperty(System.String name, System.Int32 value) : System.Void`  
- `public AddProperty(System.String name, UnityEngine.Color value) : System.Void`  
- `public AddProperty(System.String name, UnityEngine.Vector4 value) : System.Void`  
- `public AddProperty(System.String name, Colossal.AssetPipeline.Importers.TextureImporter+ITexture texture) : System.Void`  
- `public Dispose() : System.Void`  
- `public GetBakingTexture(System.String name) : Colossal.AssetPipeline.Importers.TextureImporter+Texture`  
- `public GetColorProperty(System.String name) : UnityEngine.Color`  
- `public GetFloatProperty(System.String name) : System.Single`  
- `public virtual GetHashCode() : System.Int32`  
- `public GetIntProperty(System.String name) : System.Int32`  
- `public GetTextureProperty(System.String name) : Colossal.AssetPipeline.Importers.TextureImporter+ITexture`  
- `public GetTextureProperty<T>(System.String name) : T`  
- `public GetVectorProperty(System.String name) : UnityEngine.Vector4`  
- `public HasAnyBakingTexture(System.String[] names) : System.Boolean`  
- `public HasAnyProperty(System.String[] names) : System.Boolean`  
- `public HasBakingTexture(System.String name) : System.Boolean`  
- `public HasProperty(System.String name) : System.Boolean`  
- `public RemoveBakingTexture(System.String name) : System.Void`  
- `public RemoveKeyword(System.String keyword) : System.Void`  
- `public RemoveProperty(System.String name) : System.Boolean`  
- `public ToUnityMaterial(System.Boolean hideAndDontSave = True) : UnityEngine.Material`  

## Nested types

- `Colossal.AssetPipeline.Surface+EmissiveLayer`  

