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
public UserInterface(string url, LocalizationManager localizationManager, Colossal.UI.UISystem uiSystem)
	{
		m_BindingsReady = new TaskCompletionSource<bool>();
		m_CursorCollection = Resources.Load<UICursorCollection>("Input/UI Cursors");
		m_Bindings = new CompositeBinding();
		virtualKeyboard = new VirtualKeyboard();
		UIView.Settings settings = UIView.Settings.New;
		settings.textInputHandler = virtualKeyboard;
		settings.acceptsInput = true;
		view = uiSystem.CreateView(url, settings);
		view.Listener.ReadyForBindings += OnReadyForBindings;
		view.Listener.NavigateTo += OnNavigateTo;
		view.Listener.NodeMouseEvent += OnNodeMouseEvent;
		view.Listener.CursorChanged += OnCursorChanged;
		view.Listener.TextInputTypeChanged += OnTextInputTypeChanged;
		view.Listener.CaretRectChanged += OnCaretRectChanged;
		view.enabled = true;
		m_Bindings.AddUpdateBinding(this.localizationBindings = new LocalizationBindings(localizationManager));
		m_Bindings.AddUpdateBinding(this.appBindings = new AppBindings());
		m_Bindings.AddUpdateBinding(this.overlayBindings = new OverlayBindings());
		m_Bindings.AddUpdateBinding(new AudioBindings());
		m_Bindings.AddUpdateBinding(new UserBindings());
		m_Bindings.AddUpdateBinding(new InputBindings());
		m_Bindings.AddUpdateBinding(new InputActionBindings());
		m_Bindings.AddUpdateBinding(this.inputHintBindings = new InputHintBindings());
		m_Bindings.AddUpdateBinding(this.paradoxBindings = new ParadoxBindings());
		this.overlayBindings.hintMessages = localizationManager.activeDictionary.GetIndexedLocaleIDs("Loading.HINTMESSAGE");
		if (view.View.IsReadyForBindings())
		{
			OnReadyForBindings();
		}
		SharedSettings.instance.userState.onSettingsApplied += OnSettingsApplied;
	}
```


## Methods

- `private <OnSettingsApplied>b__35_0() : System.Void`  

```csharp
private System.Void <OnSettingsApplied>b__35_0();
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		SharedSettings.instance.userState.onSettingsApplied -= OnSettingsApplied;
		overlayBindings.DeactivateAllScreens();
		appBindings.activeUI = null;
		m_Bindings.DisposeBindings();
		if (m_Bindings.attached)
		{
			m_Bindings.Detach();
		}
		if (view != null)
		{
			view.Listener.ReadyForBindings -= OnReadyForBindings;
			view.Listener.NavigateTo -= OnNavigateTo;
			view.Listener.NodeMouseEvent -= OnNodeMouseEvent;
			view.Listener.CursorChanged -= OnCursorChanged;
			view.Listener.TextInputTypeChanged -= OnTextInputTypeChanged;
			view.uiSystem.DestroyView(view);
			view = null;
		}
	}
```

- `private OnCaretRectChanged(System.Int32 x, System.Int32 y, System.UInt32 width, System.UInt32 height) : System.Void`  

```csharp
private void OnCaretRectChanged(int x, int y, uint width, uint height)
	{
		InputManager.instance.caretRect = (new Vector2(x, y), new Vector2(width, height));
	}
```

- `private OnCursorChanged(cohtml.Net.Cursors cursor, System.String url) : System.Void`  

```csharp
private void OnCursorChanged(Cursors cursor, string url)
	{
		if (m_CursorCollection == null)
		{
			UICursorCollection.ResetCursor();
		}
		else if (cursor == Cursors.URL && url != null)
		{
			m_CursorCollection.SetCursor(url);
		}
		else
		{
			m_CursorCollection.SetCursor(cursor);
		}
	}
```

- `private OnNavigateTo(System.String url) : System.Boolean`  

```csharp
private bool OnNavigateTo(string url)
	{
		m_Bindings.Detach();
		return true;
	}
```

- `private OnNodeMouseEvent(cohtml.Net.INodeProxy node, cohtml.Net.IMouseEventData ev, System.IntPtr userData, cohtml.Net.PhaseType phaseType) : cohtml.Net.Actions`  

```csharp
private Actions OnNodeMouseEvent(INodeProxy node, IMouseEventData ev, IntPtr userData, PhaseType phaseType)
	{
		if (InputManager.instance.activeControlScheme == InputManager.ControlScheme.KeyboardAndMouse && phaseType == PhaseType.AT_TARGET)
		{
			if (node.GetTag() == HTMLTag.BODY)
			{
				InputManager.instance.mouseOverUI = false;
			}
			else
			{
				InputManager.instance.mouseOverUI = true;
			}
		}
		return Actions.ContinueHandling;
	}
```

- `private OnReadyForBindings() : System.Void`  

```csharp
private void OnReadyForBindings()
	{
		log.Debug("Ready for bindings");
		m_Bindings.Attach(view.View);
		appBindings.ready = true;
		m_BindingsReady.TrySetResult(result: true);
	}
```

- `private OnSettingsApplied(Game.Settings.Setting setting) : System.Void`  

```csharp
private void OnSettingsApplied(Setting setting)
	{
		if (setting is UserState)
		{
			GameManager.instance.RunOnMainThread(delegate
			{
				appBindings.UpdateCanContinueBinding();
			});
		}
	}
```

- `private OnTextInputTypeChanged(cohtml.Net.ControlType type) : System.Void`  

```csharp
private void OnTextInputTypeChanged(ControlType type)
	{
		InputManager.instance.hasInputFieldFocus = type == ControlType.TextInput;
	}
```

- `public Update() : System.Void`  

```csharp
public void Update()
	{
		m_Bindings.Update();
	}
```

- `public WaitForBindings() : System.Threading.Tasks.Task`  

```csharp
public Task WaitForBindings()
	{
		return m_BindingsReady.Task;
	}
```


