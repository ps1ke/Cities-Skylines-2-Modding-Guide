# Game.UI.GameUIResourceHandler

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Colossal.UI.DefaultResourceHandler`  
**Implements:** `cohtml.Net.IResourceHandler`, `System.IDisposable`, `Colossal.UI.IFontSourceHandler`  

## Code

```csharp
public class GameUIResourceHandler : Colossal.UI.DefaultResourceHandler, cohtml.Net.IResourceHandler, System.IDisposable, Colossal.UI.IFontSourceHandler
{
    private System.Collections.Generic.Dictionary<System.String, UnityEngine.Camera> m_HostCameraCache;
    private static const System.String kScreencaptureScheme;
    public static const System.String kScreencaptureProtocol;
    public static const System.String kScreenshotOpString;
    private static const System.String kThumbnailScheme;
    public static const System.String kThumbnailProtocol;
    private static const System.String kUserAvatarScheme;
    public static const System.String kUserAvatarProtocol;

    public GameUIResourceHandler(UnityEngine.MonoBehaviour coroutineHost);

    private UnityEngine.Camera GetCameraFromHost(System.String host);
    public virtual System.Void OnResourceRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceResponse response);
    private System.Collections.IEnumerator RequestScreenshot(Game.UI.GameUIResourceHandler+GameResourceRequestData requestData);
    private System.Collections.IEnumerator RequestUserAvatarAsync(Game.UI.GameUIResourceHandler+GameResourceRequestData requestData);
    private UnityEngine.RenderTexture SetupCameraTarget(System.String name, UnityEngine.Camera camera, System.Int32 width, System.Int32 height);
    private System.Collections.IEnumerator TryGetResourceRequestAsync(Game.UI.GameUIResourceHandler+GameResourceRequestData requestData);
    private System.Collections.IEnumerator TryThumbnailRequestAsync(Game.UI.GameUIResourceHandler+GameResourceRequestData requestData);
    private System.Boolean UpdateTexture(UnityEngine.Texture& target, System.String name, System.ValueTuple<System.Int32, System.Int32, System.Byte[]> p);
}
```


## Fields

- `private System.Collections.Generic.Dictionary<System.String, UnityEngine.Camera> m_HostCameraCache`  

```csharp
private System.Collections.Generic.Dictionary<System.String, UnityEngine.Camera> m_HostCameraCache;
```

- `private static const System.String kScreencaptureScheme`  

```csharp
private static const System.String kScreencaptureScheme;
```

- `public static const System.String kScreencaptureProtocol`  

```csharp
public static const System.String kScreencaptureProtocol;
```

- `public static const System.String kScreenshotOpString`  

```csharp
public static const System.String kScreenshotOpString;
```

- `private static const System.String kThumbnailScheme`  

```csharp
private static const System.String kThumbnailScheme;
```

- `public static const System.String kThumbnailProtocol`  

```csharp
public static const System.String kThumbnailProtocol;
```

- `private static const System.String kUserAvatarScheme`  

```csharp
private static const System.String kUserAvatarScheme;
```

- `public static const System.String kUserAvatarProtocol`  

```csharp
public static const System.String kUserAvatarProtocol;
```


## Constructors

- `public GameUIResourceHandler(UnityEngine.MonoBehaviour coroutineHost)`  

```csharp
public GameUIResourceHandler(UnityEngine.MonoBehaviour coroutineHost);
```


## Methods

- `private GetCameraFromHost(System.String host) : UnityEngine.Camera`  

```csharp
private UnityEngine.Camera GetCameraFromHost(System.String host);
```

- `public virtual OnResourceRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceResponse response) : System.Void`  

```csharp
public virtual System.Void OnResourceRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceResponse response);
```

- `private RequestScreenshot(Game.UI.GameUIResourceHandler+GameResourceRequestData requestData) : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator RequestScreenshot(Game.UI.GameUIResourceHandler+GameResourceRequestData requestData);
```

- `private RequestUserAvatarAsync(Game.UI.GameUIResourceHandler+GameResourceRequestData requestData) : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator RequestUserAvatarAsync(Game.UI.GameUIResourceHandler+GameResourceRequestData requestData);
```

- `private SetupCameraTarget(System.String name, UnityEngine.Camera camera, System.Int32 width, System.Int32 height) : UnityEngine.RenderTexture`  

```csharp
private UnityEngine.RenderTexture SetupCameraTarget(System.String name, UnityEngine.Camera camera, System.Int32 width, System.Int32 height);
```

- `private TryGetResourceRequestAsync(Game.UI.GameUIResourceHandler+GameResourceRequestData requestData) : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator TryGetResourceRequestAsync(Game.UI.GameUIResourceHandler+GameResourceRequestData requestData);
```

- `private TryThumbnailRequestAsync(Game.UI.GameUIResourceHandler+GameResourceRequestData requestData) : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator TryThumbnailRequestAsync(Game.UI.GameUIResourceHandler+GameResourceRequestData requestData);
```

- `private UpdateTexture(UnityEngine.Texture& target, System.String name, System.ValueTuple<System.Int32, System.Int32, System.Byte[]> p) : System.Boolean`  

```csharp
private System.Boolean UpdateTexture(UnityEngine.Texture& target, System.String name, System.ValueTuple<System.Int32, System.Int32, System.Byte[]> p);
```


## Nested types

- `Game.UI.GameUIResourceHandler+GameResourceRequestData`  
- `Game.UI.GameUIResourceHandler+<>c__DisplayClass16_0`  
- `Game.UI.GameUIResourceHandler+<RequestScreenshot>d__13`  
- `Game.UI.GameUIResourceHandler+<RequestUserAvatarAsync>d__16`  
- `Game.UI.GameUIResourceHandler+<TryGetResourceRequestAsync>d__14`  
- `Game.UI.GameUIResourceHandler+<TryThumbnailRequestAsync>d__17`  

