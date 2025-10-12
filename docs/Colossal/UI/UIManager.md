# Colossal.UI.UIManager

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private Colossal.UI.TaskScheduler m_TaskScheduler`  
- `private cohtml.Net.ILibrary m_Library`  
- `private Colossal.UI.UIManager+UnityPluginListener <unityPluginListener>k__BackingField`  
- `private cohtml.UnityBackend m_Backend`  
- `private System.Boolean <shouldUseCSharpBackend>k__BackingField`  
- `private System.Boolean <enableMemoryTracking>k__BackingField`  
- `private System.Collections.Generic.List<Colossal.UI.UISystem> m_UISystems`  
- `private UnityEngine.GameObject m_RenderingResources`  
- `private Colossal.UI.UIManager+Settings m_Settings`  
- `public static Colossal.Logging.ILog log`  
- `private static Colossal.UI.UIManager s_Instance`  
- `private static const System.String kSectionName`  

## Properties

- `public static Colossal.UI.UIManager instance { get }`  
- `public Colossal.UI.UIManager+UnityPluginListener unityPluginListener { get; private set }`  
- `public System.Boolean shouldUseCSharpBackend { get; private set }`  
- `public System.Boolean enableMemoryTracking { get; private set }`  
- `public cohtml.UnityBackend RenderingBackend { get }`  
- `public static Colossal.UI.UISystem defaultUISystem { get }`  
- `public static Colossal.UI.UIView defaultUIView { get }`  
- `public static System.Collections.Generic.IReadOnlyList<Colossal.UI.UISystem> UISystems { get }`  
- `public Colossal.UI.UIManager+Settings settings { get }`  

## Constructors

- `public UIManager(System.Boolean developerMode)`  

## Methods

- `private CreateLibrary() : System.Void`  
- `private CreateRenderingResources() : System.Void`  
- `public CreateUISystem(Colossal.UI.UISystem+Settings settings) : Colossal.UI.UISystem`  
- `public DestroyUISystem(Colossal.UI.UISystem system) : System.Void`  
- `public Dispose() : System.Void`  
- `public ExecuteWork(cohtml.Net.WorkType type) : System.Void`  
- `private static GetPluginsFolderPath() : System.String`  
- `private static RestoreProcessPath() : System.Void`  
- `public ScheduleWork(cohtml.Net.WorkType type) : System.Void`  
- `private static SetDependenciesPath() : System.Void`  
- `public TryGetViewForCamera(UnityEngine.Rendering.HighDefinition.HDCamera hdCamera, Colossal.UI.UIView& outUiView) : System.Boolean`  
- `public Update() : System.Void`  

## Nested types

- `Colossal.UI.UIManager+UnityPluginListener`  
- `Colossal.UI.UIManager+Settings`  

