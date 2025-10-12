# Game.UI.AppBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `System.IDisposable`  

## Fields

- `private Colossal.UI.Binding.ValueBinding<System.String> m_BackgroundProcessMessageBinding`  
- `private Colossal.UI.Binding.EventBinding<Game.UI.ConfirmationDialogBase> m_ConfirmationDialogBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.HashSet<System.String>> m_ActiveUIModsLocation`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.Assets.SaveInfo> m_CanContinueBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.String[]> m_OwnedPrerequisites`  
- `private Colossal.UI.Binding.EventBinding m_CheckContinueGamePrerequisites`  
- `private System.Action<System.Int32> m_ConfirmationDialogCallback`  
- `private System.Action<System.Int32, System.Boolean> m_DismissibleConfirmationDialogCallback`  
- `private Game.UI.Debug.DebugUISystem m_DebugUISystem`  
- `private System.Boolean <ready>k__BackingField`  
- `private System.String <activeUI>k__BackingField`  
- `private static Game.UI.AppBindings+FrameTiming m_FrameTiming`  
- `private static const System.String kGroup`  
- `public static const System.String kBodyClassNames`  

## Properties

- `public System.Boolean ready { get; set }`  
- `public System.String activeUI { get; set }`  

## Constructors

- `public AppBindings()`  

## Methods

- `private <.ctor>b__30_0() : System.Boolean`  
- `private <.ctor>b__30_1() : System.String`  
- `public AddActiveUIModLocation(System.Collections.Generic.IList<System.String> locations) : System.Void`  
- `private DismissCurrentError() : System.Void`  
- `public Dispose() : System.Void`  
- `private ExitApplication() : System.Void`  
- `private GetCPUMainThreadTime() : System.Single`  
- `private GetCPURenderThreadTime() : System.Single`  
- `private GetFPS() : System.Single`  
- `private GetFullFrameTime() : System.Single`  
- `private GetGPUTime() : System.Single`  
- `private GetLastSaveInfo() : Game.Assets.SaveInfo`  
- `internal LauncherContinueGame() : System.Threading.Tasks.Task<System.Boolean>`  
- `private OnConfirmationDialogCallback(System.Int32 msg) : System.Void`  
- `private OnDismissibleConfirmationDialogCallback(System.Int32 msg, System.Boolean dontShowAgain) : System.Void`  
- `public RemoveActiveUIModLocation(System.Collections.Generic.IList<System.String> locations) : System.Void`  
- `private SaveBackup() : System.Void`  
- `private SaveBackupAndExitApplication() : System.Void`  
- `private SaveBackupImpl() : System.Threading.Tasks.Task`  
- `private SetClipboard(System.String text) : System.Void`  
- `public SetEditorActive() : System.Void`  
- `public SetGameActive() : System.Void`  
- `public SetMainMenuActive() : System.Void`  
- `public SetNoneActive() : System.Void`  
- `public ShowConfirmationDialog(Game.UI.ConfirmationDialog dialog, System.Action<System.Int32> callback) : System.Void`  
- `public ShowConfirmationDialog(Game.UI.DismissibleConfirmationDialog dialog, System.Action<System.Int32, System.Boolean> callback) : System.Void`  
- `public ShowMessageDialog(Game.UI.MessageDialog dialog, System.Action<System.Int32> callback) : System.Void`  
- `public virtual Update() : System.Boolean`  
- `public UpdateActiveUIModsLocation(System.Collections.Generic.IList<System.String> locations) : System.Void`  
- `public UpdateCanContinueBinding() : System.Void`  
- `public UpdateOwnedPrerequisiteBinding() : System.Void`  

## Nested types

- `Game.UI.AppBindings+FrameTiming`  
- `Game.UI.AppBindings+<>c`  
- `Game.UI.AppBindings+<SaveBackup>d__42`  
- `Game.UI.AppBindings+<SaveBackupAndExitApplication>d__41`  
- `Game.UI.AppBindings+<SaveBackupImpl>d__43`  

