# Colossal.UI.UIView

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private Colossal.UI.UIView+Settings m_Settings`  
- `private cohtml.Net.View m_View`  
- `private Colossal.UI.UISystem m_UISystem`  
- `private System.IntPtr m_LastSetViewTexturePtr`  
- `private System.Boolean m_ShouldRedraw`  
- `private System.String m_Url`  
- `private UnityEngine.RenderTexture m_ViewTexture`  
- `private UnityEngine.Material m_RenderMaterial`  
- `private UnityEngine.Camera m_RenderingCamera`  
- `private Colossal.UI.AudioSubscriber m_AudioSubscriber`  
- `private Colossal.UI.ILiveReload m_LiveReload`  
- `private System.Int32 m_Width`  
- `private System.Int32 m_Height`  
- `private System.Boolean m_Enabled`  
- `private System.IntPtr m_UserBackgroundPtr`  
- `private UnityEngine.AudioSource m_AudioSource`  
- `private UnityEngine.AudioSource <AudioSource>k__BackingField`  
- `private System.UInt32 <id>k__BackingField`  
- `private static Colossal.Logging.ILog log`  

## Properties

- `public UnityEngine.RenderTexture viewTexture { get }`  
- `public cohtml.Net.View View { get }`  
- `public Colossal.UI.ViewListener Listener { get }`  
- `public UnityEngine.Material RenderMaterial { get }`  
- `public Colossal.UI.UISystem uiSystem { get }`  
- `public System.Boolean enableBackdropFilter { get }`  
- `public System.Boolean wideTextures { get }`  
- `public System.Boolean isUserBackgroundInitialized { get }`  
- `public System.Int32 width { get; set }`  
- `public System.Int32 height { get; set }`  
- `public UnityEngine.Texture ViewTexture { get }`  
- `public UnityEngine.Camera RenderingCamera { get }`  
- `public UnityEngine.AudioSource AudioSource { get; set }`  
- `public System.Boolean enabled { get; set }`  
- `public System.UInt32 id { get; private set }`  
- `public System.String liveReloadUrl { get }`  
- `public System.Int32 devServerPort { get }`  
- `public System.Boolean acceptsInput { get }`  
- `public Colossal.UI.TextInputHandler textInputHandler { get }`  
- `public System.String url { get; set }`  

## Constructors

- `private UIView()`  
- `internal UIView(Colossal.UI.UISystem uiSystem, cohtml.Net.View view, Colossal.UI.UIView+Settings settings, UnityEngine.Camera camera = null)`  

## Methods

- `private CreateRenderMaterial() : System.Void`  
- `public DebugImageList() : System.Void`  
- `public Dispose() : System.Void`  
- `public Draw() : System.Void`  
- `public GetCamSize(System.Int32& width, System.Int32& height) : System.Boolean`  
- `public IMECancelComposition() : System.Void`  
- `public IMEConfirmComposition(System.String composition) : System.Void`  
- `public IMESetComposition(System.String composition, System.UInt32 targetStart, System.UInt32 targetEnd) : System.Void`  
- `private PrintImageList(cohtml.Net.Options options) : System.String`  
- `private RecreateRenderTarget() : System.Void`  
- `private RecreateViewTexture(System.Int32 width, System.Int32 height) : System.Void`  
- `public Resize(System.Int32 width, System.Int32 height) : System.Void`  
- `private SetRenderMaterial(UnityEngine.Shader shader) : System.Void`  
- `private SetRenderTarget(System.IntPtr viewTexturePtr) : System.Void`  
- `public Update() : System.Void`  
- `internal UpdateUserBackground(UnityEngine.RenderTexture cameraTarget) : System.Void`  

## Nested types

- `Colossal.UI.UIView+Settings`  

