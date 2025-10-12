# Game.SceneFlow.UserInterface

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private Colossal.UI.UIView <view>k__BackingField`  
- `private Game.UI.Localization.LocalizationBindings <localizationBindings>k__BackingField`  
- `private Game.SceneFlow.OverlayBindings <overlayBindings>k__BackingField`  
- `private Game.UI.AppBindings <appBindings>k__BackingField`  
- `private Game.UI.InputHintBindings <inputHintBindings>k__BackingField`  
- `private Game.UI.Menu.ParadoxBindings <paradoxBindings>k__BackingField`  
- `private Game.PSI.VirtualKeyboard <virtualKeyboard>k__BackingField`  
- `private Game.UICursorCollection m_CursorCollection`  
- `private Colossal.UI.Binding.CompositeBinding m_Bindings`  
- `private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_BindingsReady`  
- `private static Colossal.Logging.ILog log`  

## Properties

- `public Colossal.UI.UIView view { get; private set }`  
- `public Game.UI.Localization.LocalizationBindings localizationBindings { get; private set }`  
- `public Game.SceneFlow.OverlayBindings overlayBindings { get; private set }`  
- `public Game.UI.AppBindings appBindings { get; private set }`  
- `public Game.UI.InputHintBindings inputHintBindings { get; private set }`  
- `public Game.UI.Menu.ParadoxBindings paradoxBindings { get; private set }`  
- `public Game.PSI.VirtualKeyboard virtualKeyboard { get; private set }`  
- `public Colossal.UI.Binding.IBindingRegistry bindings { get }`  

## Constructors

- `public UserInterface(System.String url, Colossal.Localization.LocalizationManager localizationManager, Colossal.UI.UISystem uiSystem)`  

## Methods

- `private <OnSettingsApplied>b__35_0() : System.Void`  
- `public Dispose() : System.Void`  
- `private OnCaretRectChanged(System.Int32 x, System.Int32 y, System.UInt32 width, System.UInt32 height) : System.Void`  
- `private OnCursorChanged(cohtml.Net.Cursors cursor, System.String url) : System.Void`  
- `private OnNavigateTo(System.String url) : System.Boolean`  
- `private OnNodeMouseEvent(cohtml.Net.INodeProxy node, cohtml.Net.IMouseEventData ev, System.IntPtr userData, cohtml.Net.PhaseType phaseType) : cohtml.Net.Actions`  
- `private OnReadyForBindings() : System.Void`  
- `private OnSettingsApplied(Game.Settings.Setting setting) : System.Void`  
- `private OnTextInputTypeChanged(cohtml.Net.ControlType type) : System.Void`  
- `public Update() : System.Void`  
- `public WaitForBindings() : System.Threading.Tasks.Task`  

