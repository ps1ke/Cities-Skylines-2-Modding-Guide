# Game.UI.GameUIResourceHandler

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Colossal.UI.DefaultResourceHandler`  
**Implements:** `cohtml.Net.IResourceHandler`, `System.IDisposable`, `Colossal.UI.IFontSourceHandler`  

## Fields

- `private System.Collections.Generic.Dictionary<System.String, UnityEngine.Camera> m_HostCameraCache`  
- `private static const System.String kScreencaptureScheme`  
- `public static const System.String kScreencaptureProtocol`  
- `public static const System.String kScreenshotOpString`  
- `private static const System.String kThumbnailScheme`  
- `public static const System.String kThumbnailProtocol`  
- `private static const System.String kUserAvatarScheme`  
- `public static const System.String kUserAvatarProtocol`  

## Constructors

- `public GameUIResourceHandler(UnityEngine.MonoBehaviour coroutineHost)`  

## Methods

- `private GetCameraFromHost(System.String host) : UnityEngine.Camera`  
- `public virtual OnResourceRequest(cohtml.Net.IResourceRequest request, cohtml.Net.IResourceResponse response) : System.Void`  
- `private RequestScreenshot(Game.UI.GameUIResourceHandler+GameResourceRequestData requestData) : System.Collections.IEnumerator`  
- `private RequestUserAvatarAsync(Game.UI.GameUIResourceHandler+GameResourceRequestData requestData) : System.Collections.IEnumerator`  
- `private SetupCameraTarget(System.String name, UnityEngine.Camera camera, System.Int32 width, System.Int32 height) : UnityEngine.RenderTexture`  
- `private TryGetResourceRequestAsync(Game.UI.GameUIResourceHandler+GameResourceRequestData requestData) : System.Collections.IEnumerator`  
- `private TryThumbnailRequestAsync(Game.UI.GameUIResourceHandler+GameResourceRequestData requestData) : System.Collections.IEnumerator`  
- `private UpdateTexture(UnityEngine.Texture& target, System.String name, System.ValueTuple<System.Int32, System.Int32, System.Byte[]> p) : System.Boolean`  

## Nested types

- `Game.UI.GameUIResourceHandler+GameResourceRequestData`  
- `Game.UI.GameUIResourceHandler+<>c__DisplayClass16_0`  
- `Game.UI.GameUIResourceHandler+<RequestScreenshot>d__13`  
- `Game.UI.GameUIResourceHandler+<RequestUserAvatarAsync>d__16`  
- `Game.UI.GameUIResourceHandler+<TryGetResourceRequestAsync>d__14`  
- `Game.UI.GameUIResourceHandler+<TryThumbnailRequestAsync>d__17`  

