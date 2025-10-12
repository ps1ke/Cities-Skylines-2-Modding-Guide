# Colossal.UI.UserImagesManager

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private Colossal.UI.UISystem <uiSystem>k__BackingField`  
- `private System.Collections.Generic.Dictionary<System.IntPtr, Colossal.UI.UserImagesManager+TextureInfo> m_TexturePtrMap`  
- `private System.Collections.Generic.Dictionary<System.IntPtr, System.Int32> m_TexturePtrMapRequestCount`  
- `private Colossal.UI.UserImagesManager+TextureMap m_TextureMap`  
- `private System.UInt32[] m_ImageChangedList`  
- `private System.Func<System.String, System.Int32, System.Int32, cohtml.Net.ResourceResponse+UserImageData> AllocateUserImageData`  
- `private static Colossal.Logging.ILog log`  
- `private static System.UInt32 sImageHandle`  
- `private static const System.Int32 kOriginTopLeft`  
- `private static const System.Int32 kOriginBottomLeft`  

## Properties

- `public Colossal.UI.UISystem uiSystem { get; private set }`  
- `public System.Int32 staticUserImageCount { get }`  
- `public System.Int32 dynamicUserImageCount { get }`  

## Constructors

- `private UserImagesManager()`  
- `public UserImagesManager(Colossal.UI.UISystem uiSystem)`  

## Methods

- `private CreateUserImageData(UnityEngine.Texture texture, System.IntPtr texturePtr, System.UInt32 imageHandle = 0, UnityEngine.Rect region = null, cohtml.Net.ResourceResponse+UserImageData+AlphaPremultiplicationMode premultiplicationMode = Premultiplied) : cohtml.Net.ResourceResponse+UserImageData`  
- `public Dispose() : System.Void`  
- `public GetCustomUserImageData(System.String name, System.Int32 width, System.Int32 height) : cohtml.Net.ResourceResponse+UserImageData`  
- `public GetUserImageData(UnityEngine.Texture texture, Colossal.UI.UserImagesManager+ResourceType resourceType, System.Boolean isDynamic, UnityEngine.Rect region = null, cohtml.Net.ResourceResponse+UserImageData+AlphaPremultiplicationMode premultiplicationMode = Premultiplied) : cohtml.Net.ResourceResponse+UserImageData`  
- `public GetUserImageData(Colossal.IO.AssetDatabase.ITextureAsset asset, System.Int32 mipBias, System.Boolean isDynamic, UnityEngine.Rect region = null, cohtml.Net.ResourceResponse+UserImageData+AlphaPremultiplicationMode premultiplicationMode = Premultiplied) : cohtml.Net.ResourceResponse+UserImageData`  
- `public GetUserImageTarget(System.String name, System.Int32 width, System.Int32 height, UnityEngine.Rect region = null) : UnityEngine.Texture`  
- `private OnPreloadedTextureReleased(System.IntPtr texturePtr) : System.Void`  
- `public RemoveUserImageData(UnityEngine.Texture texture) : System.Void`  
- `public Update() : System.Void`  
- `public UpdateNativePtr(UnityEngine.Texture oldTexture, UnityEngine.Texture newTexture) : System.Void`  
- `public UpdateNativePtr(System.IntPtr oldPtr) : System.Void`  

## Events

- `AllocateUserImageData` : `System.Func<System.String, System.Int32, System.Int32, cohtml.Net.ResourceResponse+UserImageData>`  

## Nested types

- `Colossal.UI.UserImagesManager+ResourceType`  
- `Colossal.UI.UserImagesManager+UserImageKey`  
- `Colossal.UI.UserImagesManager+RegionInfo`  
- `Colossal.UI.UserImagesManager+TextureInfo`  
- `Colossal.UI.UserImagesManager+TextureMap`  

