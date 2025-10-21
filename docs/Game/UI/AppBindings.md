# Game.UI.AppBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `System.IDisposable`  

## Code

```csharp
public class AppBindings : Colossal.UI.Binding.CompositeBinding, Colossal.UI.Binding.IUpdateBinding, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IBindingRegistry, Colossal.UI.Binding.IBindingGroup, System.IDisposable
{
    private Colossal.UI.Binding.ValueBinding<System.String> m_BackgroundProcessMessageBinding;
    private Colossal.UI.Binding.EventBinding<Game.UI.ConfirmationDialogBase> m_ConfirmationDialogBinding;
    private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.HashSet<System.String>> m_ActiveUIModsLocation;
    private Colossal.UI.Binding.GetterValueBinding<Game.Assets.SaveInfo> m_CanContinueBinding;
    private Colossal.UI.Binding.ValueBinding<System.String[]> m_OwnedPrerequisites;
    private Colossal.UI.Binding.EventBinding m_CheckContinueGamePrerequisites;
    private System.Action<System.Int32> m_ConfirmationDialogCallback;
    private System.Action<System.Int32, System.Boolean> m_DismissibleConfirmationDialogCallback;
    private Game.UI.Debug.DebugUISystem m_DebugUISystem;
    private System.Boolean <ready>k__BackingField;
    private System.String <activeUI>k__BackingField;
    private static Game.UI.AppBindings+FrameTiming m_FrameTiming;
    private static const System.String kGroup;
    public static const System.String kBodyClassNames;

    public System.Boolean ready { get; set; }
    public System.String activeUI { get; set; }

    public AppBindings();

    private System.Boolean <.ctor>b__30_0();
    private System.String <.ctor>b__30_1();
    public System.Void AddActiveUIModLocation(System.Collections.Generic.IList<System.String> locations);
    private System.Void DismissCurrentError();
    public System.Void Dispose();
    private System.Void ExitApplication();
    private System.Single GetCPUMainThreadTime();
    private System.Single GetCPURenderThreadTime();
    private System.Single GetFPS();
    private System.Single GetFullFrameTime();
    private System.Single GetGPUTime();
    private Game.Assets.SaveInfo GetLastSaveInfo();
    internal System.Threading.Tasks.Task<System.Boolean> LauncherContinueGame();
    private System.Void OnConfirmationDialogCallback(System.Int32 msg);
    private System.Void OnDismissibleConfirmationDialogCallback(System.Int32 msg, System.Boolean dontShowAgain);
    public System.Void RemoveActiveUIModLocation(System.Collections.Generic.IList<System.String> locations);
    private System.Void SaveBackup();
    private System.Void SaveBackupAndExitApplication();
    private System.Threading.Tasks.Task SaveBackupImpl();
    private System.Void SetClipboard(System.String text);
    public System.Void SetEditorActive();
    public System.Void SetGameActive();
    public System.Void SetMainMenuActive();
    public System.Void SetNoneActive();
    public System.Void ShowConfirmationDialog(Game.UI.ConfirmationDialog dialog, System.Action<System.Int32> callback);
    public System.Void ShowConfirmationDialog(Game.UI.DismissibleConfirmationDialog dialog, System.Action<System.Int32, System.Boolean> callback);
    public System.Void ShowMessageDialog(Game.UI.MessageDialog dialog, System.Action<System.Int32> callback);
    public virtual System.Boolean Update();
    public System.Void UpdateActiveUIModsLocation(System.Collections.Generic.IList<System.String> locations);
    public System.Void UpdateCanContinueBinding();
    public System.Void UpdateOwnedPrerequisiteBinding();
}
```


## Fields

- `private Colossal.UI.Binding.ValueBinding<System.String> m_BackgroundProcessMessageBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_BackgroundProcessMessageBinding;
```

- `private Colossal.UI.Binding.EventBinding<Game.UI.ConfirmationDialogBase> m_ConfirmationDialogBinding`  

```csharp
private Colossal.UI.Binding.EventBinding<Game.UI.ConfirmationDialogBase> m_ConfirmationDialogBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.HashSet<System.String>> m_ActiveUIModsLocation`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.HashSet<System.String>> m_ActiveUIModsLocation;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.Assets.SaveInfo> m_CanContinueBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.Assets.SaveInfo> m_CanContinueBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.String[]> m_OwnedPrerequisites`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String[]> m_OwnedPrerequisites;
```

- `private Colossal.UI.Binding.EventBinding m_CheckContinueGamePrerequisites`  

```csharp
private Colossal.UI.Binding.EventBinding m_CheckContinueGamePrerequisites;
```

- `private System.Action<System.Int32> m_ConfirmationDialogCallback`  

```csharp
private System.Action<System.Int32> m_ConfirmationDialogCallback;
```

- `private System.Action<System.Int32, System.Boolean> m_DismissibleConfirmationDialogCallback`  

```csharp
private System.Action<System.Int32, System.Boolean> m_DismissibleConfirmationDialogCallback;
```

- `private Game.UI.Debug.DebugUISystem m_DebugUISystem`  

```csharp
private Game.UI.Debug.DebugUISystem m_DebugUISystem;
```

- `private System.Boolean <ready>k__BackingField`  

```csharp
private System.Boolean <ready>k__BackingField;
```

- `private System.String <activeUI>k__BackingField`  

```csharp
private System.String <activeUI>k__BackingField;
```

- `private static Game.UI.AppBindings+FrameTiming m_FrameTiming`  

```csharp
private static Game.UI.AppBindings+FrameTiming m_FrameTiming;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```

- `public static const System.String kBodyClassNames`  

```csharp
public static const System.String kBodyClassNames;
```


## Properties

- `public System.Boolean ready { get; set }`  

```csharp
public System.Boolean ready { get; set; }
```

- `public System.String activeUI { get; set }`  

```csharp
public System.String activeUI { get; set; }
```


## Constructors

- `public AppBindings()`  

```csharp
public AppBindings();
```


## Methods

- `private <.ctor>b__30_0() : System.Boolean`  

```csharp
private System.Boolean <.ctor>b__30_0();
```

- `private <.ctor>b__30_1() : System.String`  

```csharp
private System.String <.ctor>b__30_1();
```

- `public AddActiveUIModLocation(System.Collections.Generic.IList<System.String> locations) : System.Void`  

```csharp
public System.Void AddActiveUIModLocation(System.Collections.Generic.IList<System.String> locations);
```

- `private DismissCurrentError() : System.Void`  

```csharp
private System.Void DismissCurrentError();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private ExitApplication() : System.Void`  

```csharp
private System.Void ExitApplication();
```

- `private GetCPUMainThreadTime() : System.Single`  

```csharp
private System.Single GetCPUMainThreadTime();
```

- `private GetCPURenderThreadTime() : System.Single`  

```csharp
private System.Single GetCPURenderThreadTime();
```

- `private GetFPS() : System.Single`  

```csharp
private System.Single GetFPS();
```

- `private GetFullFrameTime() : System.Single`  

```csharp
private System.Single GetFullFrameTime();
```

- `private GetGPUTime() : System.Single`  

```csharp
private System.Single GetGPUTime();
```

- `private GetLastSaveInfo() : Game.Assets.SaveInfo`  

```csharp
private Game.Assets.SaveInfo GetLastSaveInfo();
```

- `internal LauncherContinueGame() : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
internal System.Threading.Tasks.Task<System.Boolean> LauncherContinueGame();
```

- `private OnConfirmationDialogCallback(System.Int32 msg) : System.Void`  

```csharp
private System.Void OnConfirmationDialogCallback(System.Int32 msg);
```

- `private OnDismissibleConfirmationDialogCallback(System.Int32 msg, System.Boolean dontShowAgain) : System.Void`  

```csharp
private System.Void OnDismissibleConfirmationDialogCallback(System.Int32 msg, System.Boolean dontShowAgain);
```

- `public RemoveActiveUIModLocation(System.Collections.Generic.IList<System.String> locations) : System.Void`  

```csharp
public System.Void RemoveActiveUIModLocation(System.Collections.Generic.IList<System.String> locations);
```

- `private SaveBackup() : System.Void`  

```csharp
private System.Void SaveBackup();
```

- `private SaveBackupAndExitApplication() : System.Void`  

```csharp
private System.Void SaveBackupAndExitApplication();
```

- `private SaveBackupImpl() : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task SaveBackupImpl();
```

- `private SetClipboard(System.String text) : System.Void`  

```csharp
private System.Void SetClipboard(System.String text);
```

- `public SetEditorActive() : System.Void`  

```csharp
public System.Void SetEditorActive();
```

- `public SetGameActive() : System.Void`  

```csharp
public System.Void SetGameActive();
```

- `public SetMainMenuActive() : System.Void`  

```csharp
public System.Void SetMainMenuActive();
```

- `public SetNoneActive() : System.Void`  

```csharp
public System.Void SetNoneActive();
```

- `public ShowConfirmationDialog(Game.UI.ConfirmationDialog dialog, System.Action<System.Int32> callback) : System.Void`  

```csharp
public System.Void ShowConfirmationDialog(Game.UI.ConfirmationDialog dialog, System.Action<System.Int32> callback);
```

- `public ShowConfirmationDialog(Game.UI.DismissibleConfirmationDialog dialog, System.Action<System.Int32, System.Boolean> callback) : System.Void`  

```csharp
public System.Void ShowConfirmationDialog(Game.UI.DismissibleConfirmationDialog dialog, System.Action<System.Int32, System.Boolean> callback);
```

- `public ShowMessageDialog(Game.UI.MessageDialog dialog, System.Action<System.Int32> callback) : System.Void`  

```csharp
public System.Void ShowMessageDialog(Game.UI.MessageDialog dialog, System.Action<System.Int32> callback);
```

- `public virtual Update() : System.Boolean`  

```csharp
public virtual System.Boolean Update();
```

- `public UpdateActiveUIModsLocation(System.Collections.Generic.IList<System.String> locations) : System.Void`  

```csharp
public System.Void UpdateActiveUIModsLocation(System.Collections.Generic.IList<System.String> locations);
```

- `public UpdateCanContinueBinding() : System.Void`  

```csharp
public System.Void UpdateCanContinueBinding();
```

- `public UpdateOwnedPrerequisiteBinding() : System.Void`  

```csharp
public System.Void UpdateOwnedPrerequisiteBinding();
```


## Nested types

- `Game.UI.AppBindings+FrameTiming`  
- `Game.UI.AppBindings+<>c`  
- `Game.UI.AppBindings+<SaveBackup>d__42`  
- `Game.UI.AppBindings+<SaveBackupAndExitApplication>d__41`  
- `Game.UI.AppBindings+<SaveBackupImpl>d__43`  

