# Colossal.UI.UserImagesManager

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class UserImagesManager : System.IDisposable
{
    private Colossal.UI.UISystem <uiSystem>k__BackingField;
    private System.Collections.Generic.Dictionary<System.IntPtr, Colossal.UI.UserImagesManager+TextureInfo> m_TexturePtrMap;
    private System.Collections.Generic.Dictionary<System.IntPtr, System.Int32> m_TexturePtrMapRequestCount;
    private Colossal.UI.UserImagesManager+TextureMap m_TextureMap;
    private System.UInt32[] m_ImageChangedList;
    private System.Func<System.String, System.Int32, System.Int32, cohtml.Net.ResourceResponse+UserImageData> AllocateUserImageData;
    private static Colossal.Logging.ILog log;
    private static System.UInt32 sImageHandle;
    private static const System.Int32 kOriginTopLeft;
    private static const System.Int32 kOriginBottomLeft;

    public Colossal.UI.UISystem uiSystem { get; private set; }
    public System.Int32 staticUserImageCount { get; }
    public System.Int32 dynamicUserImageCount { get; }

    private UserImagesManager();
    public UserImagesManager(Colossal.UI.UISystem uiSystem);

    private cohtml.Net.ResourceResponse+UserImageData CreateUserImageData(UnityEngine.Texture texture, System.IntPtr texturePtr, System.UInt32 imageHandle, UnityEngine.Rect region, cohtml.Net.ResourceResponse+UserImageData+AlphaPremultiplicationMode premultiplicationMode);
    public System.Void Dispose();
    public cohtml.Net.ResourceResponse+UserImageData GetCustomUserImageData(System.String name, System.Int32 width, System.Int32 height);
    public cohtml.Net.ResourceResponse+UserImageData GetUserImageData(UnityEngine.Texture texture, Colossal.UI.UserImagesManager+ResourceType resourceType, System.Boolean isDynamic, UnityEngine.Rect region, cohtml.Net.ResourceResponse+UserImageData+AlphaPremultiplicationMode premultiplicationMode);
    public cohtml.Net.ResourceResponse+UserImageData GetUserImageData(Colossal.IO.AssetDatabase.ITextureAsset asset, System.Int32 mipBias, System.Boolean isDynamic, UnityEngine.Rect region, cohtml.Net.ResourceResponse+UserImageData+AlphaPremultiplicationMode premultiplicationMode);
    public UnityEngine.Texture GetUserImageTarget(System.String name, System.Int32 width, System.Int32 height, UnityEngine.Rect region);
    private System.Void OnPreloadedTextureReleased(System.IntPtr texturePtr);
    public System.Void RemoveUserImageData(UnityEngine.Texture texture);
    public System.Void Update();
    public System.Void UpdateNativePtr(UnityEngine.Texture oldTexture, UnityEngine.Texture newTexture);
    public System.Void UpdateNativePtr(System.IntPtr oldPtr);
}
```


## Fields

- `private Colossal.UI.UISystem <uiSystem>k__BackingField`  

```csharp
private Colossal.UI.UISystem <uiSystem>k__BackingField;
```

- `private System.Collections.Generic.Dictionary<System.IntPtr, Colossal.UI.UserImagesManager+TextureInfo> m_TexturePtrMap`  

```csharp
private System.Collections.Generic.Dictionary<System.IntPtr, Colossal.UI.UserImagesManager+TextureInfo> m_TexturePtrMap;
```

- `private System.Collections.Generic.Dictionary<System.IntPtr, System.Int32> m_TexturePtrMapRequestCount`  

```csharp
private System.Collections.Generic.Dictionary<System.IntPtr, System.Int32> m_TexturePtrMapRequestCount;
```

- `private Colossal.UI.UserImagesManager+TextureMap m_TextureMap`  

```csharp
private Colossal.UI.UserImagesManager+TextureMap m_TextureMap;
```

- `private System.UInt32[] m_ImageChangedList`  

```csharp
private System.UInt32[] m_ImageChangedList;
```

- `private System.Func<System.String, System.Int32, System.Int32, cohtml.Net.ResourceResponse+UserImageData> AllocateUserImageData`  

```csharp
private System.Func<System.String, System.Int32, System.Int32, cohtml.Net.ResourceResponse+UserImageData> AllocateUserImageData;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static System.UInt32 sImageHandle`  

```csharp
private static System.UInt32 sImageHandle;
```

- `private static const System.Int32 kOriginTopLeft`  

```csharp
private static const System.Int32 kOriginTopLeft;
```

- `private static const System.Int32 kOriginBottomLeft`  

```csharp
private static const System.Int32 kOriginBottomLeft;
```


## Properties

- `public Colossal.UI.UISystem uiSystem { get; private set }`  

```csharp
public Colossal.UI.UISystem uiSystem { get; private set; }
```

- `public System.Int32 staticUserImageCount { get }`  

```csharp
public System.Int32 staticUserImageCount { get; }
```

- `public System.Int32 dynamicUserImageCount { get }`  

```csharp
public System.Int32 dynamicUserImageCount { get; }
```


## Constructors

- `private UserImagesManager()`  

```csharp
private UserImagesManager();
```

- `public UserImagesManager(Colossal.UI.UISystem uiSystem)`  

```csharp
public UserImagesManager(Colossal.UI.UISystem uiSystem);
```


## Methods

- `private CreateUserImageData(UnityEngine.Texture texture, System.IntPtr texturePtr, System.UInt32 imageHandle = 0, UnityEngine.Rect region = null, cohtml.Net.ResourceResponse+UserImageData+AlphaPremultiplicationMode premultiplicationMode = Premultiplied) : cohtml.Net.ResourceResponse+UserImageData`  

```csharp
private cohtml.Net.ResourceResponse+UserImageData CreateUserImageData(UnityEngine.Texture texture, System.IntPtr texturePtr, System.UInt32 imageHandle, UnityEngine.Rect region, cohtml.Net.ResourceResponse+UserImageData+AlphaPremultiplicationMode premultiplicationMode);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetCustomUserImageData(System.String name, System.Int32 width, System.Int32 height) : cohtml.Net.ResourceResponse+UserImageData`  

```csharp
public cohtml.Net.ResourceResponse+UserImageData GetCustomUserImageData(System.String name, System.Int32 width, System.Int32 height);
```

- `public GetUserImageData(UnityEngine.Texture texture, Colossal.UI.UserImagesManager+ResourceType resourceType, System.Boolean isDynamic, UnityEngine.Rect region = null, cohtml.Net.ResourceResponse+UserImageData+AlphaPremultiplicationMode premultiplicationMode = Premultiplied) : cohtml.Net.ResourceResponse+UserImageData`  

```csharp
public cohtml.Net.ResourceResponse+UserImageData GetUserImageData(UnityEngine.Texture texture, Colossal.UI.UserImagesManager+ResourceType resourceType, System.Boolean isDynamic, UnityEngine.Rect region, cohtml.Net.ResourceResponse+UserImageData+AlphaPremultiplicationMode premultiplicationMode);
```

- `public GetUserImageData(Colossal.IO.AssetDatabase.ITextureAsset asset, System.Int32 mipBias, System.Boolean isDynamic, UnityEngine.Rect region = null, cohtml.Net.ResourceResponse+UserImageData+AlphaPremultiplicationMode premultiplicationMode = Premultiplied) : cohtml.Net.ResourceResponse+UserImageData`  

```csharp
public cohtml.Net.ResourceResponse+UserImageData GetUserImageData(Colossal.IO.AssetDatabase.ITextureAsset asset, System.Int32 mipBias, System.Boolean isDynamic, UnityEngine.Rect region, cohtml.Net.ResourceResponse+UserImageData+AlphaPremultiplicationMode premultiplicationMode);
```

- `public GetUserImageTarget(System.String name, System.Int32 width, System.Int32 height, UnityEngine.Rect region = null) : UnityEngine.Texture`  

```csharp
public UnityEngine.Texture GetUserImageTarget(System.String name, System.Int32 width, System.Int32 height, UnityEngine.Rect region);
```

- `private OnPreloadedTextureReleased(System.IntPtr texturePtr) : System.Void`  

```csharp
private System.Void OnPreloadedTextureReleased(System.IntPtr texturePtr);
```

- `public RemoveUserImageData(UnityEngine.Texture texture) : System.Void`  

```csharp
public System.Void RemoveUserImageData(UnityEngine.Texture texture);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```

- `public UpdateNativePtr(UnityEngine.Texture oldTexture, UnityEngine.Texture newTexture) : System.Void`  

```csharp
public System.Void UpdateNativePtr(UnityEngine.Texture oldTexture, UnityEngine.Texture newTexture);
```

- `public UpdateNativePtr(System.IntPtr oldPtr) : System.Void`  

```csharp
public System.Void UpdateNativePtr(System.IntPtr oldPtr);
```


## Events

- `AllocateUserImageData` : `System.Func<System.String, System.Int32, System.Int32, cohtml.Net.ResourceResponse+UserImageData>`  

```csharp
public event System.Func<System.String, System.Int32, System.Int32, cohtml.Net.ResourceResponse+UserImageData> AllocateUserImageData;
```


## Nested types

- `Colossal.UI.UserImagesManager+ResourceType`  
- `Colossal.UI.UserImagesManager+UserImageKey`  
- `Colossal.UI.UserImagesManager+RegionInfo`  
- `Colossal.UI.UserImagesManager+TextureInfo`  
- `Colossal.UI.UserImagesManager+TextureMap`  

