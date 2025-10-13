# Colossal.UI.UIView

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class UIView : System.IDisposable
{
    private Colossal.UI.UIView+Settings m_Settings;
    private cohtml.Net.View m_View;
    private Colossal.UI.UISystem m_UISystem;
    private System.IntPtr m_LastSetViewTexturePtr;
    private System.Boolean m_ShouldRedraw;
    private System.String m_Url;
    private UnityEngine.RenderTexture m_ViewTexture;
    private UnityEngine.Material m_RenderMaterial;
    private UnityEngine.Camera m_RenderingCamera;
    private Colossal.UI.AudioSubscriber m_AudioSubscriber;
    private Colossal.UI.ILiveReload m_LiveReload;
    private System.Int32 m_Width;
    private System.Int32 m_Height;
    private System.Boolean m_Enabled;
    private System.IntPtr m_UserBackgroundPtr;
    private UnityEngine.AudioSource m_AudioSource;
    private UnityEngine.AudioSource <AudioSource>k__BackingField;
    private System.UInt32 <id>k__BackingField;
    private static Colossal.Logging.ILog log;

    public UnityEngine.RenderTexture viewTexture { get; }
    public cohtml.Net.View View { get; }
    public Colossal.UI.ViewListener Listener { get; }
    public UnityEngine.Material RenderMaterial { get; }
    public Colossal.UI.UISystem uiSystem { get; }
    public System.Boolean enableBackdropFilter { get; }
    public System.Boolean wideTextures { get; }
    public System.Boolean isUserBackgroundInitialized { get; }
    public System.Int32 width { get; set; }
    public System.Int32 height { get; set; }
    public UnityEngine.Texture ViewTexture { get; }
    public UnityEngine.Camera RenderingCamera { get; }
    public UnityEngine.AudioSource AudioSource { get; set; }
    public System.Boolean enabled { get; set; }
    public System.UInt32 id { get; private set; }
    public System.String liveReloadUrl { get; }
    public System.Int32 devServerPort { get; }
    public System.Boolean acceptsInput { get; }
    public Colossal.UI.TextInputHandler textInputHandler { get; }
    public System.String url { get; set; }

    private UIView();
    internal UIView(Colossal.UI.UISystem uiSystem, cohtml.Net.View view, Colossal.UI.UIView+Settings settings, UnityEngine.Camera camera);

    private System.Void CreateRenderMaterial();
    public System.Void DebugImageList();
    public System.Void Dispose();
    public System.Void Draw();
    public System.Boolean GetCamSize(System.Int32& width, System.Int32& height);
    public System.Void IMECancelComposition();
    public System.Void IMEConfirmComposition(System.String composition);
    public System.Void IMESetComposition(System.String composition, System.UInt32 targetStart, System.UInt32 targetEnd);
    private System.String PrintImageList(cohtml.Net.Options options);
    private System.Void RecreateRenderTarget();
    private System.Void RecreateViewTexture(System.Int32 width, System.Int32 height);
    public System.Void Resize(System.Int32 width, System.Int32 height);
    private System.Void SetRenderMaterial(UnityEngine.Shader shader);
    private System.Void SetRenderTarget(System.IntPtr viewTexturePtr);
    public System.Void Update();
    internal System.Void UpdateUserBackground(UnityEngine.RenderTexture cameraTarget);
}
```


## Fields

- `private Colossal.UI.UIView+Settings m_Settings`  

```csharp
private Colossal.UI.UIView+Settings m_Settings;
```

- `private cohtml.Net.View m_View`  

```csharp
private cohtml.Net.View m_View;
```

- `private Colossal.UI.UISystem m_UISystem`  

```csharp
private Colossal.UI.UISystem m_UISystem;
```

- `private System.IntPtr m_LastSetViewTexturePtr`  

```csharp
private System.IntPtr m_LastSetViewTexturePtr;
```

- `private System.Boolean m_ShouldRedraw`  

```csharp
private System.Boolean m_ShouldRedraw;
```

- `private System.String m_Url`  

```csharp
private System.String m_Url;
```

- `private UnityEngine.RenderTexture m_ViewTexture`  

```csharp
private UnityEngine.RenderTexture m_ViewTexture;
```

- `private UnityEngine.Material m_RenderMaterial`  

```csharp
private UnityEngine.Material m_RenderMaterial;
```

- `private UnityEngine.Camera m_RenderingCamera`  

```csharp
private UnityEngine.Camera m_RenderingCamera;
```

- `private Colossal.UI.AudioSubscriber m_AudioSubscriber`  

```csharp
private Colossal.UI.AudioSubscriber m_AudioSubscriber;
```

- `private Colossal.UI.ILiveReload m_LiveReload`  

```csharp
private Colossal.UI.ILiveReload m_LiveReload;
```

- `private System.Int32 m_Width`  

```csharp
private System.Int32 m_Width;
```

- `private System.Int32 m_Height`  

```csharp
private System.Int32 m_Height;
```

- `private System.Boolean m_Enabled`  

```csharp
private System.Boolean m_Enabled;
```

- `private System.IntPtr m_UserBackgroundPtr`  

```csharp
private System.IntPtr m_UserBackgroundPtr;
```

- `private UnityEngine.AudioSource m_AudioSource`  

```csharp
private UnityEngine.AudioSource m_AudioSource;
```

- `private UnityEngine.AudioSource <AudioSource>k__BackingField`  

```csharp
private UnityEngine.AudioSource <AudioSource>k__BackingField;
```

- `private System.UInt32 <id>k__BackingField`  

```csharp
private System.UInt32 <id>k__BackingField;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```


## Properties

- `public UnityEngine.RenderTexture viewTexture { get }`  

```csharp
public UnityEngine.RenderTexture viewTexture { get; }
```

- `public cohtml.Net.View View { get }`  

```csharp
public cohtml.Net.View View { get; }
```

- `public Colossal.UI.ViewListener Listener { get }`  

```csharp
public Colossal.UI.ViewListener Listener { get; }
```

- `public UnityEngine.Material RenderMaterial { get }`  

```csharp
public UnityEngine.Material RenderMaterial { get; }
```

- `public Colossal.UI.UISystem uiSystem { get }`  

```csharp
public Colossal.UI.UISystem uiSystem { get; }
```

- `public System.Boolean enableBackdropFilter { get }`  

```csharp
public System.Boolean enableBackdropFilter { get; }
```

- `public System.Boolean wideTextures { get }`  

```csharp
public System.Boolean wideTextures { get; }
```

- `public System.Boolean isUserBackgroundInitialized { get }`  

```csharp
public System.Boolean isUserBackgroundInitialized { get; }
```

- `public System.Int32 width { get; set }`  

```csharp
public System.Int32 width { get; set; }
```

- `public System.Int32 height { get; set }`  

```csharp
public System.Int32 height { get; set; }
```

- `public UnityEngine.Texture ViewTexture { get }`  

```csharp
public UnityEngine.Texture ViewTexture { get; }
```

- `public UnityEngine.Camera RenderingCamera { get }`  

```csharp
public UnityEngine.Camera RenderingCamera { get; }
```

- `public UnityEngine.AudioSource AudioSource { get; set }`  

```csharp
public UnityEngine.AudioSource AudioSource { get; set; }
```

- `public System.Boolean enabled { get; set }`  

```csharp
public System.Boolean enabled { get; set; }
```

- `public System.UInt32 id { get; private set }`  

```csharp
public System.UInt32 id { get; private set; }
```

- `public System.String liveReloadUrl { get }`  

```csharp
public System.String liveReloadUrl { get; }
```

- `public System.Int32 devServerPort { get }`  

```csharp
public System.Int32 devServerPort { get; }
```

- `public System.Boolean acceptsInput { get }`  

```csharp
public System.Boolean acceptsInput { get; }
```

- `public Colossal.UI.TextInputHandler textInputHandler { get }`  

```csharp
public Colossal.UI.TextInputHandler textInputHandler { get; }
```

- `public System.String url { get; set }`  

```csharp
public System.String url { get; set; }
```


## Constructors

- `private UIView()`  

```csharp
private UIView();
```

- `internal UIView(Colossal.UI.UISystem uiSystem, cohtml.Net.View view, Colossal.UI.UIView+Settings settings, UnityEngine.Camera camera = null)`  

```csharp
internal UIView(Colossal.UI.UISystem uiSystem, cohtml.Net.View view, Colossal.UI.UIView+Settings settings, UnityEngine.Camera camera);
```


## Methods

- `private CreateRenderMaterial() : System.Void`  

```csharp
private System.Void CreateRenderMaterial();
```

- `public DebugImageList() : System.Void`  

```csharp
public System.Void DebugImageList();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Draw() : System.Void`  

```csharp
public System.Void Draw();
```

- `public GetCamSize(System.Int32& width, System.Int32& height) : System.Boolean`  

```csharp
public System.Boolean GetCamSize(System.Int32& width, System.Int32& height);
```

- `public IMECancelComposition() : System.Void`  

```csharp
public System.Void IMECancelComposition();
```

- `public IMEConfirmComposition(System.String composition) : System.Void`  

```csharp
public System.Void IMEConfirmComposition(System.String composition);
```

- `public IMESetComposition(System.String composition, System.UInt32 targetStart, System.UInt32 targetEnd) : System.Void`  

```csharp
public System.Void IMESetComposition(System.String composition, System.UInt32 targetStart, System.UInt32 targetEnd);
```

- `private PrintImageList(cohtml.Net.Options options) : System.String`  

```csharp
private System.String PrintImageList(cohtml.Net.Options options);
```

- `private RecreateRenderTarget() : System.Void`  

```csharp
private System.Void RecreateRenderTarget();
```

- `private RecreateViewTexture(System.Int32 width, System.Int32 height) : System.Void`  

```csharp
private System.Void RecreateViewTexture(System.Int32 width, System.Int32 height);
```

- `public Resize(System.Int32 width, System.Int32 height) : System.Void`  

```csharp
public System.Void Resize(System.Int32 width, System.Int32 height);
```

- `private SetRenderMaterial(UnityEngine.Shader shader) : System.Void`  

```csharp
private System.Void SetRenderMaterial(UnityEngine.Shader shader);
```

- `private SetRenderTarget(System.IntPtr viewTexturePtr) : System.Void`  

```csharp
private System.Void SetRenderTarget(System.IntPtr viewTexturePtr);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```

- `internal UpdateUserBackground(UnityEngine.RenderTexture cameraTarget) : System.Void`  

```csharp
internal System.Void UpdateUserBackground(UnityEngine.RenderTexture cameraTarget);
```


## Nested types

- `Colossal.UI.UIView+Settings`  

