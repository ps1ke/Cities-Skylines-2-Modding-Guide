# Game.UI.Menu.InputRebindingUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class InputRebindingUISystem : Game.UI.UISystemBase
{
    private Colossal.UI.Binding.ValueBinding<System.Nullable<Game.Input.ProxyBinding>> m_ActiveRebindingBinding;
    private Colossal.UI.Binding.ValueBinding<System.Nullable<Game.UI.Menu.InputRebindingUISystem+ConflictInfo>> m_ActiveConflictBinding;
    private UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation m_Operation;
    private UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation m_ModifierOperation;
    private System.Nullable<Game.Input.ProxyBinding> m_ActiveRebinding;
    private System.Action<Game.Input.ProxyBinding> m_OnSetBinding;
    private System.Nullable<Game.Input.ProxyBinding> m_PendingRebinding;
    private System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> m_Conflicts;
    private static const System.String kGroup;

    public InputRebindingUISystem();

    internal static System.Boolean <Process>g__NeedAskUser|20_0(Game.Input.ProxyBinding binding);
    private System.Void <ProcessConflict>g__AddToConflictInfos|28_0(Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem info, Game.UI.Menu.InputRebindingUISystem+<>c__DisplayClass28_0& );
    private System.Void Apply(Game.Input.ProxyBinding newBinding);
    public System.Void Cancel();
    private static System.Boolean CanSwap(Game.Input.ProxyBinding x, Game.Input.ProxyBinding y, System.Boolean checkUsage);
    private System.Void CollectAliases(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem mainInfo);
    private System.Void CollectBindingConflicts(System.Collections.Generic.List<Game.UI.Menu.InputRebindingUISystem+BindingPair> conflicts, Game.Input.ProxyBinding toCheck, Game.Input.ProxyBinding resolution);
    private System.Boolean CollectLinkedBindings(Game.Input.ProxyBinding oldBinding, Game.Input.ProxyBinding newBinding, System.Collections.Generic.Dictionary`2[[Game.Input.ProxyBinding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.List`1[[Game.UI.Menu.InputRebindingUISystem+BindingPair, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& rebindingMap);
    private System.Void CompleteAndSwapConflicts();
    private System.Void CompleteAndUnsetConflicts();
    private System.Void GetRebindOptions(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, Game.Input.ProxyBinding oldBinding, Game.Input.ProxyBinding newBinding, System.Boolean& unsolved, System.Boolean& batchSwap, System.Boolean& swap, System.Boolean& unset);
    private System.Void GetRebindOptions(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, System.Collections.Generic.List<Game.UI.Menu.InputRebindingUISystem+BindingPair> list);
    private System.Void OnApplyBinding(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation, System.String path);
    private System.Void OnCancel(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation);
    private System.Void OnComplete(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    private System.Void OnDeviceChange(UnityEngine.InputSystem.InputDevice changedDevice, UnityEngine.InputSystem.InputDeviceChange change);
    private System.Void OnModifierApplyBinding(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation, System.String path);
    private System.Void OnModifierPotentialMatch(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation);
    private System.Void Process(Game.Input.ProxyBinding oldBinding, Game.Input.ProxyBinding newBinding);
    private System.Void ProcessConflict(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, System.Collections.Generic.List<Game.UI.Menu.InputRebindingUISystem+BindingPair> bindingConflicts, Game.Input.Usages& usages, Game.Input.Usages& otherUsages, Game.UI.Menu.InputRebindingUISystem+Options direction, System.Boolean& changed);
    private System.Void Reset();
    public System.Void Start(Game.Input.ProxyBinding binding, System.Action<Game.Input.ProxyBinding> onSetBinding);
    public System.Void Start(Game.Input.ProxyBinding binding, Game.Input.ProxyBinding newBinding, System.Action<Game.Input.ProxyBinding> onSetBinding);
}
```


## Fields

- `private Colossal.UI.Binding.ValueBinding<System.Nullable<Game.Input.ProxyBinding>> m_ActiveRebindingBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Nullable<Game.Input.ProxyBinding>> m_ActiveRebindingBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Nullable<Game.UI.Menu.InputRebindingUISystem+ConflictInfo>> m_ActiveConflictBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Nullable<Game.UI.Menu.InputRebindingUISystem+ConflictInfo>> m_ActiveConflictBinding;
```

- `private UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation m_Operation`  

```csharp
private UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation m_Operation;
```

- `private UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation m_ModifierOperation`  

```csharp
private UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation m_ModifierOperation;
```

- `private System.Nullable<Game.Input.ProxyBinding> m_ActiveRebinding`  

```csharp
private System.Nullable<Game.Input.ProxyBinding> m_ActiveRebinding;
```

- `private System.Action<Game.Input.ProxyBinding> m_OnSetBinding`  

```csharp
private System.Action<Game.Input.ProxyBinding> m_OnSetBinding;
```

- `private System.Nullable<Game.Input.ProxyBinding> m_PendingRebinding`  

```csharp
private System.Nullable<Game.Input.ProxyBinding> m_PendingRebinding;
```

- `private System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> m_Conflicts`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> m_Conflicts;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public InputRebindingUISystem()`  

```csharp
public InputRebindingUISystem();
```


## Methods

- `internal static <Process>g__NeedAskUser|20_0(Game.Input.ProxyBinding binding) : System.Boolean`  

```csharp
internal static System.Boolean <Process>g__NeedAskUser|20_0(Game.Input.ProxyBinding binding);
```

- `private <ProcessConflict>g__AddToConflictInfos|28_0(Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem info, Game.UI.Menu.InputRebindingUISystem+<>c__DisplayClass28_0& ) : System.Void`  

```csharp
private System.Void <ProcessConflict>g__AddToConflictInfos|28_0(Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem info, Game.UI.Menu.InputRebindingUISystem+<>c__DisplayClass28_0& );
```

- `private Apply(Game.Input.ProxyBinding newBinding) : System.Void`  

```csharp
private System.Void Apply(Game.Input.ProxyBinding newBinding);
```

- `public Cancel() : System.Void`  

```csharp
public System.Void Cancel();
```

- `private static CanSwap(Game.Input.ProxyBinding x, Game.Input.ProxyBinding y, System.Boolean checkUsage) : System.Boolean`  

```csharp
private static System.Boolean CanSwap(Game.Input.ProxyBinding x, Game.Input.ProxyBinding y, System.Boolean checkUsage);
```

- `private CollectAliases(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem mainInfo) : System.Void`  

```csharp
private System.Void CollectAliases(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem mainInfo);
```

- `private CollectBindingConflicts(System.Collections.Generic.List<Game.UI.Menu.InputRebindingUISystem+BindingPair> conflicts, Game.Input.ProxyBinding toCheck, Game.Input.ProxyBinding resolution) : System.Void`  

```csharp
private System.Void CollectBindingConflicts(System.Collections.Generic.List<Game.UI.Menu.InputRebindingUISystem+BindingPair> conflicts, Game.Input.ProxyBinding toCheck, Game.Input.ProxyBinding resolution);
```

- `private CollectLinkedBindings(Game.Input.ProxyBinding oldBinding, Game.Input.ProxyBinding newBinding, System.Collections.Generic.Dictionary`2[[Game.Input.ProxyBinding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.List`1[[Game.UI.Menu.InputRebindingUISystem+BindingPair, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& rebindingMap) : System.Boolean`  

```csharp
private System.Boolean CollectLinkedBindings(Game.Input.ProxyBinding oldBinding, Game.Input.ProxyBinding newBinding, System.Collections.Generic.Dictionary`2[[Game.Input.ProxyBinding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.List`1[[Game.UI.Menu.InputRebindingUISystem+BindingPair, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& rebindingMap);
```

- `private CompleteAndSwapConflicts() : System.Void`  

```csharp
private System.Void CompleteAndSwapConflicts();
```

- `private CompleteAndUnsetConflicts() : System.Void`  

```csharp
private System.Void CompleteAndUnsetConflicts();
```

- `private GetRebindOptions(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, Game.Input.ProxyBinding oldBinding, Game.Input.ProxyBinding newBinding, System.Boolean& unsolved, System.Boolean& batchSwap, System.Boolean& swap, System.Boolean& unset) : System.Void`  

```csharp
private System.Void GetRebindOptions(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, Game.Input.ProxyBinding oldBinding, Game.Input.ProxyBinding newBinding, System.Boolean& unsolved, System.Boolean& batchSwap, System.Boolean& swap, System.Boolean& unset);
```

- `private GetRebindOptions(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, System.Collections.Generic.List<Game.UI.Menu.InputRebindingUISystem+BindingPair> list) : System.Void`  

```csharp
private System.Void GetRebindOptions(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, System.Collections.Generic.List<Game.UI.Menu.InputRebindingUISystem+BindingPair> list);
```

- `private OnApplyBinding(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation, System.String path) : System.Void`  

```csharp
private System.Void OnApplyBinding(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation, System.String path);
```

- `private OnCancel(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation) : System.Void`  

```csharp
private System.Void OnCancel(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation);
```

- `private OnComplete(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation) : System.Void`  

```csharp
private System.Void OnComplete(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `private OnDeviceChange(UnityEngine.InputSystem.InputDevice changedDevice, UnityEngine.InputSystem.InputDeviceChange change) : System.Void`  

```csharp
private System.Void OnDeviceChange(UnityEngine.InputSystem.InputDevice changedDevice, UnityEngine.InputSystem.InputDeviceChange change);
```

- `private OnModifierApplyBinding(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation, System.String path) : System.Void`  

```csharp
private System.Void OnModifierApplyBinding(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation, System.String path);
```

- `private OnModifierPotentialMatch(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation) : System.Void`  

```csharp
private System.Void OnModifierPotentialMatch(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation);
```

- `private Process(Game.Input.ProxyBinding oldBinding, Game.Input.ProxyBinding newBinding) : System.Void`  

```csharp
private System.Void Process(Game.Input.ProxyBinding oldBinding, Game.Input.ProxyBinding newBinding);
```

- `private ProcessConflict(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, System.Collections.Generic.List<Game.UI.Menu.InputRebindingUISystem+BindingPair> bindingConflicts, Game.Input.Usages& usages, Game.Input.Usages& otherUsages, Game.UI.Menu.InputRebindingUISystem+Options direction, System.Boolean& changed) : System.Void`  

```csharp
private System.Void ProcessConflict(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, System.Collections.Generic.List<Game.UI.Menu.InputRebindingUISystem+BindingPair> bindingConflicts, Game.Input.Usages& usages, Game.Input.Usages& otherUsages, Game.UI.Menu.InputRebindingUISystem+Options direction, System.Boolean& changed);
```

- `private Reset() : System.Void`  

```csharp
private System.Void Reset();
```

- `public Start(Game.Input.ProxyBinding binding, System.Action<Game.Input.ProxyBinding> onSetBinding) : System.Void`  

```csharp
public System.Void Start(Game.Input.ProxyBinding binding, System.Action<Game.Input.ProxyBinding> onSetBinding);
```

- `public Start(Game.Input.ProxyBinding binding, Game.Input.ProxyBinding newBinding, System.Action<Game.Input.ProxyBinding> onSetBinding) : System.Void`  

```csharp
public System.Void Start(Game.Input.ProxyBinding binding, Game.Input.ProxyBinding newBinding, System.Action<Game.Input.ProxyBinding> onSetBinding);
```


## Nested types

- `Game.UI.Menu.InputRebindingUISystem+Options`  
- `Game.UI.Menu.InputRebindingUISystem+BindingPair`  
- `Game.UI.Menu.InputRebindingUISystem+ConflictInfo`  
- `Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem`  
- `Game.UI.Menu.InputRebindingUISystem+<>c`  
- `Game.UI.Menu.InputRebindingUISystem+<>c__DisplayClass17_0`  
- `Game.UI.Menu.InputRebindingUISystem+<>c__DisplayClass28_0`  

