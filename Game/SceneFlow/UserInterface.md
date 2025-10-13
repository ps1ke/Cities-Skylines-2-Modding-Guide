# Game.SceneFlow.UserInterface

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class UserInterface : System.IDisposable
{
    private Colossal.UI.UIView <view>k__BackingField;
    private Game.UI.Localization.LocalizationBindings <localizationBindings>k__BackingField;
    private Game.SceneFlow.OverlayBindings <overlayBindings>k__BackingField;
    private Game.UI.AppBindings <appBindings>k__BackingField;
    private Game.UI.InputHintBindings <inputHintBindings>k__BackingField;
    private Game.UI.Menu.ParadoxBindings <paradoxBindings>k__BackingField;
    private Game.PSI.VirtualKeyboard <virtualKeyboard>k__BackingField;
    private Game.UICursorCollection m_CursorCollection;
    private Colossal.UI.Binding.CompositeBinding m_Bindings;
    private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_BindingsReady;
    private static Colossal.Logging.ILog log;

    public Colossal.UI.UIView view { get; private set; }
    public Game.UI.Localization.LocalizationBindings localizationBindings { get; private set; }
    public Game.SceneFlow.OverlayBindings overlayBindings { get; private set; }
    public Game.UI.AppBindings appBindings { get; private set; }
    public Game.UI.InputHintBindings inputHintBindings { get; private set; }
    public Game.UI.Menu.ParadoxBindings paradoxBindings { get; private set; }
    public Game.PSI.VirtualKeyboard virtualKeyboard { get; private set; }
    public Colossal.UI.Binding.IBindingRegistry bindings { get; }

    public UserInterface(System.String url, Colossal.Localization.LocalizationManager localizationManager, Colossal.UI.UISystem uiSystem);

    private System.Void <OnSettingsApplied>b__35_0();
    public System.Void Dispose();
    private System.Void OnCaretRectChanged(System.Int32 x, System.Int32 y, System.UInt32 width, System.UInt32 height);
    private System.Void OnCursorChanged(cohtml.Net.Cursors cursor, System.String url);
    private System.Boolean OnNavigateTo(System.String url);
    private cohtml.Net.Actions OnNodeMouseEvent(cohtml.Net.INodeProxy node, cohtml.Net.IMouseEventData ev, System.IntPtr userData, cohtml.Net.PhaseType phaseType);
    private System.Void OnReadyForBindings();
    private System.Void OnSettingsApplied(Game.Settings.Setting setting);
    private System.Void OnTextInputTypeChanged(cohtml.Net.ControlType type);
    public System.Void Update();
    public System.Threading.Tasks.Task WaitForBindings();
}
```


## Fields

- `private Colossal.UI.UIView <view>k__BackingField`  

```csharp
private Colossal.UI.UIView <view>k__BackingField;
```

- `private Game.UI.Localization.LocalizationBindings <localizationBindings>k__BackingField`  

```csharp
private Game.UI.Localization.LocalizationBindings <localizationBindings>k__BackingField;
```

- `private Game.SceneFlow.OverlayBindings <overlayBindings>k__BackingField`  

```csharp
private Game.SceneFlow.OverlayBindings <overlayBindings>k__BackingField;
```

- `private Game.UI.AppBindings <appBindings>k__BackingField`  

```csharp
private Game.UI.AppBindings <appBindings>k__BackingField;
```

- `private Game.UI.InputHintBindings <inputHintBindings>k__BackingField`  

```csharp
private Game.UI.InputHintBindings <inputHintBindings>k__BackingField;
```

- `private Game.UI.Menu.ParadoxBindings <paradoxBindings>k__BackingField`  

```csharp
private Game.UI.Menu.ParadoxBindings <paradoxBindings>k__BackingField;
```

- `private Game.PSI.VirtualKeyboard <virtualKeyboard>k__BackingField`  

```csharp
private Game.PSI.VirtualKeyboard <virtualKeyboard>k__BackingField;
```

- `private Game.UICursorCollection m_CursorCollection`  

```csharp
private Game.UICursorCollection m_CursorCollection;
```

- `private Colossal.UI.Binding.CompositeBinding m_Bindings`  

```csharp
private Colossal.UI.Binding.CompositeBinding m_Bindings;
```

- `private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_BindingsReady`  

```csharp
private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_BindingsReady;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```


## Properties

- `public Colossal.UI.UIView view { get; private set }`  

```csharp
public Colossal.UI.UIView view { get; private set; }
```

- `public Game.UI.Localization.LocalizationBindings localizationBindings { get; private set }`  

```csharp
public Game.UI.Localization.LocalizationBindings localizationBindings { get; private set; }
```

- `public Game.SceneFlow.OverlayBindings overlayBindings { get; private set }`  

```csharp
public Game.SceneFlow.OverlayBindings overlayBindings { get; private set; }
```

- `public Game.UI.AppBindings appBindings { get; private set }`  

```csharp
public Game.UI.AppBindings appBindings { get; private set; }
```

- `public Game.UI.InputHintBindings inputHintBindings { get; private set }`  

```csharp
public Game.UI.InputHintBindings inputHintBindings { get; private set; }
```

- `public Game.UI.Menu.ParadoxBindings paradoxBindings { get; private set }`  

```csharp
public Game.UI.Menu.ParadoxBindings paradoxBindings { get; private set; }
```

- `public Game.PSI.VirtualKeyboard virtualKeyboard { get; private set }`  

```csharp
public Game.PSI.VirtualKeyboard virtualKeyboard { get; private set; }
```

- `public Colossal.UI.Binding.IBindingRegistry bindings { get }`  

```csharp
public Colossal.UI.Binding.IBindingRegistry bindings { get; }
```


## Constructors

- `public UserInterface(System.String url, Colossal.Localization.LocalizationManager localizationManager, Colossal.UI.UISystem uiSystem)`  

```csharp
public UserInterface(System.String url, Colossal.Localization.LocalizationManager localizationManager, Colossal.UI.UISystem uiSystem);
```


## Methods

- `private <OnSettingsApplied>b__35_0() : System.Void`  

```csharp
private System.Void <OnSettingsApplied>b__35_0();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private OnCaretRectChanged(System.Int32 x, System.Int32 y, System.UInt32 width, System.UInt32 height) : System.Void`  

```csharp
private System.Void OnCaretRectChanged(System.Int32 x, System.Int32 y, System.UInt32 width, System.UInt32 height);
```

- `private OnCursorChanged(cohtml.Net.Cursors cursor, System.String url) : System.Void`  

```csharp
private System.Void OnCursorChanged(cohtml.Net.Cursors cursor, System.String url);
```

- `private OnNavigateTo(System.String url) : System.Boolean`  

```csharp
private System.Boolean OnNavigateTo(System.String url);
```

- `private OnNodeMouseEvent(cohtml.Net.INodeProxy node, cohtml.Net.IMouseEventData ev, System.IntPtr userData, cohtml.Net.PhaseType phaseType) : cohtml.Net.Actions`  

```csharp
private cohtml.Net.Actions OnNodeMouseEvent(cohtml.Net.INodeProxy node, cohtml.Net.IMouseEventData ev, System.IntPtr userData, cohtml.Net.PhaseType phaseType);
```

- `private OnReadyForBindings() : System.Void`  

```csharp
private System.Void OnReadyForBindings();
```

- `private OnSettingsApplied(Game.Settings.Setting setting) : System.Void`  

```csharp
private System.Void OnSettingsApplied(Game.Settings.Setting setting);
```

- `private OnTextInputTypeChanged(cohtml.Net.ControlType type) : System.Void`  

```csharp
private System.Void OnTextInputTypeChanged(cohtml.Net.ControlType type);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```

- `public WaitForBindings() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task WaitForBindings();
```


