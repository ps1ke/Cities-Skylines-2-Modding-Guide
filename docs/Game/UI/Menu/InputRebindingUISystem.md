# Game.UI.Menu.InputRebindingUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Fields

- `private Colossal.UI.Binding.ValueBinding<System.Nullable<Game.Input.ProxyBinding>> m_ActiveRebindingBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Nullable<Game.UI.Menu.InputRebindingUISystem+ConflictInfo>> m_ActiveConflictBinding`  
- `private UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation m_Operation`  
- `private UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation m_ModifierOperation`  
- `private System.Nullable<Game.Input.ProxyBinding> m_ActiveRebinding`  
- `private System.Action<Game.Input.ProxyBinding> m_OnSetBinding`  
- `private System.Nullable<Game.Input.ProxyBinding> m_PendingRebinding`  
- `private System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> m_Conflicts`  
- `private static const System.String kGroup`  

## Constructors

- `public InputRebindingUISystem()`  

## Methods

- `internal static <Process>g__NeedAskUser|20_0(Game.Input.ProxyBinding binding) : System.Boolean`  
- `private <ProcessConflict>g__AddToConflictInfos|28_0(Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem info, Game.UI.Menu.InputRebindingUISystem+<>c__DisplayClass28_0& ) : System.Void`  
- `private Apply(Game.Input.ProxyBinding newBinding) : System.Void`  
- `public Cancel() : System.Void`  
- `private static CanSwap(Game.Input.ProxyBinding x, Game.Input.ProxyBinding y, System.Boolean checkUsage) : System.Boolean`  
- `private CollectAliases(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem mainInfo) : System.Void`  
- `private CollectBindingConflicts(System.Collections.Generic.List<Game.UI.Menu.InputRebindingUISystem+BindingPair> conflicts, Game.Input.ProxyBinding toCheck, Game.Input.ProxyBinding resolution) : System.Void`  
- `private CollectLinkedBindings(Game.Input.ProxyBinding oldBinding, Game.Input.ProxyBinding newBinding, System.Collections.Generic.Dictionary`2[[Game.Input.ProxyBinding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.List`1[[Game.UI.Menu.InputRebindingUISystem+BindingPair, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& rebindingMap) : System.Boolean`  
- `private CompleteAndSwapConflicts() : System.Void`  
- `private CompleteAndUnsetConflicts() : System.Void`  
- `private GetRebindOptions(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, Game.Input.ProxyBinding oldBinding, Game.Input.ProxyBinding newBinding, System.Boolean& unsolved, System.Boolean& batchSwap, System.Boolean& swap, System.Boolean& unset) : System.Void`  
- `private GetRebindOptions(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, System.Collections.Generic.List<Game.UI.Menu.InputRebindingUISystem+BindingPair> list) : System.Void`  
- `private OnApplyBinding(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation, System.String path) : System.Void`  
- `private OnCancel(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation) : System.Void`  
- `private OnComplete(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `private OnDeviceChange(UnityEngine.InputSystem.InputDevice changedDevice, UnityEngine.InputSystem.InputDeviceChange change) : System.Void`  
- `private OnModifierApplyBinding(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation, System.String path) : System.Void`  
- `private OnModifierPotentialMatch(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation) : System.Void`  
- `private Process(Game.Input.ProxyBinding oldBinding, Game.Input.ProxyBinding newBinding) : System.Void`  
- `private ProcessConflict(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, System.Collections.Generic.List<Game.UI.Menu.InputRebindingUISystem+BindingPair> bindingConflicts, Game.Input.Usages& usages, Game.Input.Usages& otherUsages, Game.UI.Menu.InputRebindingUISystem+Options direction, System.Boolean& changed) : System.Void`  
- `private Reset() : System.Void`  
- `public Start(Game.Input.ProxyBinding binding, System.Action<Game.Input.ProxyBinding> onSetBinding) : System.Void`  
- `public Start(Game.Input.ProxyBinding binding, Game.Input.ProxyBinding newBinding, System.Action<Game.Input.ProxyBinding> onSetBinding) : System.Void`  

## Nested types

- `Game.UI.Menu.InputRebindingUISystem+Options`  
- `Game.UI.Menu.InputRebindingUISystem+BindingPair`  
- `Game.UI.Menu.InputRebindingUISystem+ConflictInfo`  
- `Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem`  
- `Game.UI.Menu.InputRebindingUISystem+<>c`  
- `Game.UI.Menu.InputRebindingUISystem+<>c__DisplayClass17_0`  
- `Game.UI.Menu.InputRebindingUISystem+<>c__DisplayClass28_0`  

