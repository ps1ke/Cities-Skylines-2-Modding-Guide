# Colossal.UI.UIManager

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class UIManager : System.IDisposable
{
    private Colossal.UI.TaskScheduler m_TaskScheduler;
    private cohtml.Net.ILibrary m_Library;
    private Colossal.UI.UIManager+UnityPluginListener <unityPluginListener>k__BackingField;
    private cohtml.UnityBackend m_Backend;
    private System.Boolean <shouldUseCSharpBackend>k__BackingField;
    private System.Boolean <enableMemoryTracking>k__BackingField;
    private System.Collections.Generic.List<Colossal.UI.UISystem> m_UISystems;
    private UnityEngine.GameObject m_RenderingResources;
    private Colossal.UI.UIManager+Settings m_Settings;
    public static Colossal.Logging.ILog log;
    private static Colossal.UI.UIManager s_Instance;
    private static const System.String kSectionName;

    public static Colossal.UI.UIManager instance { get; }
    public Colossal.UI.UIManager+UnityPluginListener unityPluginListener { get; private set; }
    public System.Boolean shouldUseCSharpBackend { get; private set; }
    public System.Boolean enableMemoryTracking { get; private set; }
    public cohtml.UnityBackend RenderingBackend { get; }
    public static Colossal.UI.UISystem defaultUISystem { get; }
    public static Colossal.UI.UIView defaultUIView { get; }
    public static System.Collections.Generic.IReadOnlyList<Colossal.UI.UISystem> UISystems { get; }
    public Colossal.UI.UIManager+Settings settings { get; }

    public UIManager(System.Boolean developerMode);

    private System.Void CreateLibrary();
    private System.Void CreateRenderingResources();
    public Colossal.UI.UISystem CreateUISystem(Colossal.UI.UISystem+Settings settings);
    public System.Void DestroyUISystem(Colossal.UI.UISystem system);
    public System.Void Dispose();
    public System.Void ExecuteWork(cohtml.Net.WorkType type);
    private static System.String GetPluginsFolderPath();
    private static System.Void RestoreProcessPath();
    public System.Void ScheduleWork(cohtml.Net.WorkType type);
    private static System.Void SetDependenciesPath();
    public System.Boolean TryGetViewForCamera(UnityEngine.Rendering.HighDefinition.HDCamera hdCamera, Colossal.UI.UIView& outUiView);
    public System.Void Update();
}
```


## Fields

- `private Colossal.UI.TaskScheduler m_TaskScheduler`  

```csharp
private Colossal.UI.TaskScheduler m_TaskScheduler;
```

- `private cohtml.Net.ILibrary m_Library`  

```csharp
private cohtml.Net.ILibrary m_Library;
```

- `private Colossal.UI.UIManager+UnityPluginListener <unityPluginListener>k__BackingField`  

```csharp
private Colossal.UI.UIManager+UnityPluginListener <unityPluginListener>k__BackingField;
```

- `private cohtml.UnityBackend m_Backend`  

```csharp
private cohtml.UnityBackend m_Backend;
```

- `private System.Boolean <shouldUseCSharpBackend>k__BackingField`  

```csharp
private System.Boolean <shouldUseCSharpBackend>k__BackingField;
```

- `private System.Boolean <enableMemoryTracking>k__BackingField`  

```csharp
private System.Boolean <enableMemoryTracking>k__BackingField;
```

- `private System.Collections.Generic.List<Colossal.UI.UISystem> m_UISystems`  

```csharp
private System.Collections.Generic.List<Colossal.UI.UISystem> m_UISystems;
```

- `private UnityEngine.GameObject m_RenderingResources`  

```csharp
private UnityEngine.GameObject m_RenderingResources;
```

- `private Colossal.UI.UIManager+Settings m_Settings`  

```csharp
private Colossal.UI.UIManager+Settings m_Settings;
```

- `public static Colossal.Logging.ILog log`  

```csharp
public static Colossal.Logging.ILog log;
```

- `private static Colossal.UI.UIManager s_Instance`  

```csharp
private static Colossal.UI.UIManager s_Instance;
```

- `private static const System.String kSectionName`  

```csharp
private static const System.String kSectionName;
```


## Properties

- `public static Colossal.UI.UIManager instance { get }`  

```csharp
public static Colossal.UI.UIManager instance { get; }
```

- `public Colossal.UI.UIManager+UnityPluginListener unityPluginListener { get; private set }`  

```csharp
public Colossal.UI.UIManager+UnityPluginListener unityPluginListener { get; private set; }
```

- `public System.Boolean shouldUseCSharpBackend { get; private set }`  

```csharp
public System.Boolean shouldUseCSharpBackend { get; private set; }
```

- `public System.Boolean enableMemoryTracking { get; private set }`  

```csharp
public System.Boolean enableMemoryTracking { get; private set; }
```

- `public cohtml.UnityBackend RenderingBackend { get }`  

```csharp
public cohtml.UnityBackend RenderingBackend { get; }
```

- `public static Colossal.UI.UISystem defaultUISystem { get }`  

```csharp
public static Colossal.UI.UISystem defaultUISystem { get; }
```

- `public static Colossal.UI.UIView defaultUIView { get }`  

```csharp
public static Colossal.UI.UIView defaultUIView { get; }
```

- `public static System.Collections.Generic.IReadOnlyList<Colossal.UI.UISystem> UISystems { get }`  

```csharp
public static System.Collections.Generic.IReadOnlyList<Colossal.UI.UISystem> UISystems { get; }
```

- `public Colossal.UI.UIManager+Settings settings { get }`  

```csharp
public Colossal.UI.UIManager+Settings settings { get; }
```


## Constructors

- `public UIManager(System.Boolean developerMode)`  

```csharp
public UIManager(System.Boolean developerMode);
```


## Methods

- `private CreateLibrary() : System.Void`  

```csharp
private System.Void CreateLibrary();
```

- `private CreateRenderingResources() : System.Void`  

```csharp
private System.Void CreateRenderingResources();
```

- `public CreateUISystem(Colossal.UI.UISystem+Settings settings) : Colossal.UI.UISystem`  

```csharp
public Colossal.UI.UISystem CreateUISystem(Colossal.UI.UISystem+Settings settings);
```

- `public DestroyUISystem(Colossal.UI.UISystem system) : System.Void`  

```csharp
public System.Void DestroyUISystem(Colossal.UI.UISystem system);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public ExecuteWork(cohtml.Net.WorkType type) : System.Void`  

```csharp
public System.Void ExecuteWork(cohtml.Net.WorkType type);
```

- `private static GetPluginsFolderPath() : System.String`  

```csharp
private static System.String GetPluginsFolderPath();
```

- `private static RestoreProcessPath() : System.Void`  

```csharp
private static System.Void RestoreProcessPath();
```

- `public ScheduleWork(cohtml.Net.WorkType type) : System.Void`  

```csharp
public System.Void ScheduleWork(cohtml.Net.WorkType type);
```

- `private static SetDependenciesPath() : System.Void`  

```csharp
private static System.Void SetDependenciesPath();
```

- `public TryGetViewForCamera(UnityEngine.Rendering.HighDefinition.HDCamera hdCamera, Colossal.UI.UIView& outUiView) : System.Boolean`  

```csharp
public System.Boolean TryGetViewForCamera(UnityEngine.Rendering.HighDefinition.HDCamera hdCamera, Colossal.UI.UIView& outUiView);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```


## Nested types

- `Colossal.UI.UIManager+UnityPluginListener`  
- `Colossal.UI.UIManager+Settings`  

