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
[Preserve]
	public InputRebindingUISystem()
	{
	}
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
private void Apply(ProxyBinding newBinding)
	{
		using (Game.Input.InputManager.DeferUpdating())
		{
			m_OnSetBinding?.Invoke(newBinding);
		}
	}
```

- `public Cancel() : System.Void`  

```csharp
public void Cancel()
	{
		m_Operation.Reset();
		Reset();
	}
```

- `private static CanSwap(Game.Input.ProxyBinding x, Game.Input.ProxyBinding y, System.Boolean checkUsage) : System.Boolean`  

```csharp
private static bool CanSwap(ProxyBinding x, ProxyBinding y, bool checkUsage)
	{
		if (!x.isSet || !y.isSet)
		{
			return false;
		}
		if (!x.isRebindable || !y.isRebindable)
		{
			return false;
		}
		if (ProxyBinding.PathEquals(x, y))
		{
			return false;
		}
		if (checkUsage && Usages.TestAny(x.usages, y.usages))
		{
			return false;
		}
		if (ProxyBinding.defaultModifiersComparer.Equals(x.modifiers, y.modifiers))
		{
			return true;
		}
		if (!x.allowModifiers || !y.allowModifiers)
		{
			return false;
		}
		if (!x.isModifiersRebindable || !y.isModifiersRebindable)
		{
			return false;
		}
		return true;
	}
```

- `private CollectAliases(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem mainInfo) : System.Void`  

```csharp
private void CollectAliases(Dictionary<string, ConflictInfoItem> conflictInfos, ConflictInfoItem mainInfo)
	{
		foreach (UIBaseInputAction uIAlias in mainInfo.binding.action.m_UIAliases)
		{
			if (mainInfo.binding.alies == uIAlias || !uIAlias.showInOptions)
			{
				continue;
			}
			foreach (UIInputActionPart actionPart in uIAlias.actionParts)
			{
				if ((actionPart.m_Transform == UIBaseInputAction.Transform.None || (mainInfo.binding.component.ToTransform() & actionPart.m_Transform) != UIBaseInputAction.Transform.None) && (actionPart.m_Mask & mainInfo.binding.device) != Game.Input.InputManager.DeviceType.None)
				{
					ProxyBinding binding = mainInfo.binding.Copy();
					binding.alies = uIAlias;
					ProxyBinding resolution = mainInfo.resolution.Copy();
					resolution.alies = uIAlias;
					conflictInfos.TryAdd(binding.title, new ConflictInfoItem
					{
						binding = binding,
						resolution = resolution,
						options = mainInfo.options,
						isAlias = true
					});
				}
			}
		}
		if (mainInfo.binding.isAlias)
		{
			ProxyBinding binding2 = mainInfo.binding.Copy();
			binding2.alies = null;
			ProxyBinding resolution2 = mainInfo.resolution.Copy();
			resolution2.alies = null;
			conflictInfos.TryAdd(binding2.title, new ConflictInfoItem
			{
				binding = binding2,
				resolution = resolution2,
				options = mainInfo.options,
				isAlias = true
			});
		}
	}
```

- `private CollectBindingConflicts(System.Collections.Generic.List<Game.UI.Menu.InputRebindingUISystem+BindingPair> conflicts, Game.Input.ProxyBinding toCheck, Game.Input.ProxyBinding resolution) : System.Void`  

```csharp
private void CollectBindingConflicts(List<BindingPair> conflicts, ProxyBinding toCheck, ProxyBinding resolution)
	{
		if (!Game.Input.InputManager.instance.keyActionMap.TryGetValue(toCheck.path, out var value))
		{
			return;
		}
		ProxyAction action = toCheck.action;
		foreach (ProxyAction item3 in value)
		{
			foreach (var (_, proxyComposite2) in item3.composites)
			{
				if (proxyComposite2.isDummy || proxyComposite2.m_Device != toCheck.device)
				{
					continue;
				}
				bool flag = Game.Input.InputManager.CanConflict(action, item3, proxyComposite2.m_Device);
				foreach (var (_, proxyBinding2) in proxyComposite2.bindings)
				{
					if ((!flag && ProxyBinding.componentComparer.Equals(proxyBinding2, toCheck)) || !ProxyBinding.PathEquals(proxyBinding2, toCheck) || proxyBinding2.usages.isNone)
					{
						continue;
					}
					BindingPair item = new BindingPair(proxyBinding2, resolution);
					if (!conflicts.Contains(item))
					{
						conflicts.Add(item);
					}
					foreach (ProxyAction.LinkInfo linkedAction in item3.m_LinkedActions)
					{
						if (linkedAction.m_Device == proxyBinding2.device && linkedAction.m_Action.TryGetComposite(proxyBinding2.device, out var composite) && composite.TryGetBinding(proxyBinding2.component, out var foundBinding) && !foundBinding.usages.isNone)
						{
							ProxyBinding newBinding = resolution.Copy();
							if (!foundBinding.isModifiersRebindable)
							{
								newBinding.modifiers = foundBinding.modifiers;
							}
							BindingPair item2 = new BindingPair(foundBinding, newBinding);
							if (!conflicts.Contains(item2))
							{
								conflicts.Add(item2);
							}
						}
					}
				}
			}
		}
	}
```

- `private CollectLinkedBindings(Game.Input.ProxyBinding oldBinding, Game.Input.ProxyBinding newBinding, System.Collections.Generic.Dictionary`2[[Game.Input.ProxyBinding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Collections.Generic.List`1[[Game.UI.Menu.InputRebindingUISystem+BindingPair, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& rebindingMap) : System.Boolean`  

```csharp
private bool CollectLinkedBindings(ProxyBinding oldBinding, ProxyBinding newBinding, out Dictionary<ProxyBinding, List<BindingPair>> rebindingMap)
	{
		rebindingMap = new Dictionary<ProxyBinding, List<BindingPair>>(ProxyBinding.pathAndModifiersComparer) { 
		{
			oldBinding,
			new List<BindingPair>
			{
				new BindingPair(oldBinding, newBinding)
			}
		} };
		ProxyAction action = oldBinding.action;
		if (action == null)
		{
			return true;
		}
		foreach (ProxyAction.LinkInfo linkedAction in action.m_LinkedActions)
		{
			if (linkedAction.m_Device != oldBinding.device)
			{
				continue;
			}
			foreach (var (_, proxyComposite2) in linkedAction.m_Action.composites)
			{
				if (proxyComposite2.isDummy)
				{
					continue;
				}
				foreach (var (_, proxyBinding2) in proxyComposite2.bindings)
				{
					if (ProxyBinding.componentComparer.Equals(oldBinding, proxyBinding2))
					{
						if (!proxyBinding2.isRebindable)
						{
							return false;
						}
						ProxyBinding newBinding2 = proxyBinding2.Copy();
						newBinding2.path = newBinding.path;
						if (newBinding2.allowModifiers && newBinding2.isModifiersRebindable)
						{
							newBinding2.modifiers = newBinding.modifiers;
						}
						if (!rebindingMap.TryGetValue(proxyBinding2, out var value))
						{
							value = new List<BindingPair>();
							rebindingMap[proxyBinding2] = value;
						}
						value.Add(new BindingPair(proxyBinding2, newBinding2));
					}
				}
			}
		}
		return true;
	}
```

- `private CompleteAndSwapConflicts() : System.Void`  

```csharp
private void CompleteAndSwapConflicts()
	{
		if (m_PendingRebinding.HasValue)
		{
			using (Game.Input.InputManager.DeferUpdating())
			{
				IEnumerable<ProxyBinding> newBindings = from c in m_Conflicts.Values
					where !c.isAlias
					select c.resolution;
				Game.Input.InputManager.instance.SetBindings(newBindings, out var _);
				Apply(m_PendingRebinding.Value);
			}
		}
		Reset();
	}
```

- `private CompleteAndUnsetConflicts() : System.Void`  

```csharp
private void CompleteAndUnsetConflicts()
	{
		if (m_PendingRebinding.HasValue)
		{
			using (Game.Input.InputManager.DeferUpdating())
			{
				IEnumerable<ProxyBinding> newBindings = from c in m_Conflicts.Values
					where !c.isAlias
					select c.binding.WithPath(string.Empty).WithModifiers(Array.Empty<ProxyModifier>());
				Game.Input.InputManager.instance.SetBindings(newBindings, out var _);
				Apply(m_PendingRebinding.Value);
			}
		}
		Reset();
	}
```

- `private GetRebindOptions(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, Game.Input.ProxyBinding oldBinding, Game.Input.ProxyBinding newBinding, System.Boolean& unsolved, System.Boolean& batchSwap, System.Boolean& swap, System.Boolean& unset) : System.Void`  

```csharp
private void GetRebindOptions(Dictionary<string, ConflictInfoItem> conflictInfos, List<BindingPair> list)
	{
		List<BindingPair> list2 = new List<BindingPair>();
		List<BindingPair> list3 = new List<BindingPair>();
		Usages otherUsages = new Usages(0, readOnly: false);
		Usages otherUsages2 = new Usages(0, readOnly: false);
		ProxyBinding newBinding;
		ProxyBinding oldBinding;
		foreach (BindingPair item in list)
		{
			item.Deconstruct(out newBinding, out oldBinding);
			ProxyBinding proxyBinding = newBinding;
			ProxyBinding proxyBinding2 = oldBinding;
			CollectBindingConflicts(list2, proxyBinding, proxyBinding2);
			CollectBindingConflicts(list3, proxyBinding2, proxyBinding);
			otherUsages2 = Usages.Combine(otherUsages2, proxyBinding2.usages);
		}
		foreach (BindingPair item2 in list)
		{
			item2.Deconstruct(out oldBinding, out newBinding);
			ProxyBinding x = oldBinding;
			ProxyBinding y = newBinding;
			if (ProxyBinding.PathEquals(x, y))
			{
				ProcessConflict(conflictInfos, list3, ref otherUsages2, ref otherUsages2, Options.None, out var _);
			}
		}
		bool changed2 = true;
		while (changed2)
		{
			ProcessConflict(conflictInfos, list3, ref otherUsages2, ref otherUsages, Options.Forward, out changed2);
			if (changed2)
			{
				ProcessConflict(conflictInfos, list2, ref otherUsages, ref otherUsages2, Options.Backward, out changed2);
				if (!changed2)
				{
					break;
				}
				continue;
			}
			break;
		}
	}
```

- `private GetRebindOptions(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, System.Collections.Generic.List<Game.UI.Menu.InputRebindingUISystem+BindingPair> list) : System.Void`  

```csharp
private void GetRebindOptions(Dictionary<string, ConflictInfoItem> conflictInfos, List<BindingPair> list)
	{
		List<BindingPair> list2 = new List<BindingPair>();
		List<BindingPair> list3 = new List<BindingPair>();
		Usages otherUsages = new Usages(0, readOnly: false);
		Usages otherUsages2 = new Usages(0, readOnly: false);
		ProxyBinding newBinding;
		ProxyBinding oldBinding;
		foreach (BindingPair item in list)
		{
			item.Deconstruct(out newBinding, out oldBinding);
			ProxyBinding proxyBinding = newBinding;
			ProxyBinding proxyBinding2 = oldBinding;
			CollectBindingConflicts(list2, proxyBinding, proxyBinding2);
			CollectBindingConflicts(list3, proxyBinding2, proxyBinding);
			otherUsages2 = Usages.Combine(otherUsages2, proxyBinding2.usages);
		}
		foreach (BindingPair item2 in list)
		{
			item2.Deconstruct(out oldBinding, out newBinding);
			ProxyBinding x = oldBinding;
			ProxyBinding y = newBinding;
			if (ProxyBinding.PathEquals(x, y))
			{
				ProcessConflict(conflictInfos, list3, ref otherUsages2, ref otherUsages2, Options.None, out var _);
			}
		}
		bool changed2 = true;
		while (changed2)
		{
			ProcessConflict(conflictInfos, list3, ref otherUsages2, ref otherUsages, Options.Forward, out changed2);
			if (changed2)
			{
				ProcessConflict(conflictInfos, list2, ref otherUsages, ref otherUsages2, Options.Backward, out changed2);
				if (!changed2)
				{
					break;
				}
				continue;
			}
			break;
		}
	}
```

- `private OnApplyBinding(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation, System.String path) : System.Void`  

```csharp
private void OnApplyBinding(InputActionRebindingExtensions.RebindingOperation operation, string path)
	{
		if (!m_ActiveRebinding.HasValue)
		{
			return;
		}
		Game.Input.InputManager.instance.blockedControlTypes = Game.Input.InputManager.DeviceType.None;
		if (path != null && path.StartsWith("<DualShockGamepad>"))
		{
			path = path.Replace("<DualShockGamepad>", "<Gamepad>");
		}
		ProxyBinding oldBinding = m_ActiveRebinding.Value;
		ProxyBinding newBinding = oldBinding.Copy();
		newBinding.path = path;
		if (newBinding.isModifiersRebindable)
		{
			newBinding.modifiers = (from c in m_ModifierOperation.candidates
				where c.IsPressed()
				select new ProxyModifier
				{
					m_Component = oldBinding.component,
					m_Name = Game.Input.InputManager.GetModifierName(oldBinding.component),
					m_Path = Game.Input.InputManager.GeneratePathForControl(c)
				}).ToList();
		}
		m_ModifierOperation.Reset();
		Process(oldBinding, newBinding);
	}
```

- `private OnCancel(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation) : System.Void`  

```csharp
private void OnCancel(InputActionRebindingExtensions.RebindingOperation operation)
	{
		Game.Input.InputManager.instance.blockedControlTypes = Game.Input.InputManager.DeviceType.None;
		Reset();
	}
```

- `private OnComplete(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation) : System.Void`  

```csharp
private void OnComplete(InputActionRebindingExtensions.RebindingOperation operation)
	{
		Game.Input.InputManager.instance.blockedControlTypes = Game.Input.InputManager.DeviceType.None;
		if (!m_PendingRebinding.HasValue)
		{
			Reset();
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		AddBinding(m_ActiveRebindingBinding = new ValueBinding<ProxyBinding?>("inputRebinding", "activeRebinding", null, ValueWritersStruct.Nullable(new ValueWriter<ProxyBinding>())));
		AddBinding(m_ActiveConflictBinding = new ValueBinding<ConflictInfo?>("inputRebinding", "activeConflict", null, ValueWritersStruct.Nullable(new ValueWriter<ConflictInfo>())));
		AddBinding(new TriggerBinding("inputRebinding", "cancelRebinding", Cancel));
		AddBinding(new TriggerBinding("inputRebinding", "completeAndSwapConflicts", CompleteAndSwapConflicts));
		AddBinding(new TriggerBinding("inputRebinding", "completeAndUnsetConflicts", CompleteAndUnsetConflicts));
		m_Operation = new InputActionRebindingExtensions.RebindingOperation();
		m_Operation.OnApplyBinding(OnApplyBinding);
		m_Operation.OnComplete(OnComplete);
		m_Operation.OnCancel(OnCancel);
		m_ModifierOperation = new InputActionRebindingExtensions.RebindingOperation();
		m_ModifierOperation.OnPotentialMatch(OnModifierPotentialMatch);
		m_ModifierOperation.OnApplyBinding(OnModifierApplyBinding);
		InputSystem.onDeviceChange += OnDeviceChange;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_Operation.Dispose();
		m_ModifierOperation.Dispose();
		InputSystem.onDeviceChange -= OnDeviceChange;
		base.OnDestroy();
	}
```

- `private OnDeviceChange(UnityEngine.InputSystem.InputDevice changedDevice, UnityEngine.InputSystem.InputDeviceChange change) : System.Void`  

```csharp
private void OnDeviceChange(InputDevice changedDevice, InputDeviceChange change)
	{
		if ((change != InputDeviceChange.Added && change != InputDeviceChange.Removed) || !m_ActiveRebinding.HasValue)
		{
			return;
		}
		foreach (InputDevice device in InputSystem.devices)
		{
			if (device.added && ((device is Keyboard && m_ActiveRebinding.Value.isKeyboard) || (device is Mouse && m_ActiveRebinding.Value.isMouse) || (device is Gamepad && m_ActiveRebinding.Value.isGamepad)))
			{
				return;
			}
		}
		Cancel();
	}
```

- `private OnModifierApplyBinding(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation, System.String path) : System.Void`  

```csharp
private void OnModifierApplyBinding(InputActionRebindingExtensions.RebindingOperation operation, string path)
	{
	}
```

- `private OnModifierPotentialMatch(UnityEngine.InputSystem.InputActionRebindingExtensions+RebindingOperation operation) : System.Void`  

```csharp
private void OnModifierPotentialMatch(InputActionRebindingExtensions.RebindingOperation operation)
	{
	}
```

- `private Process(Game.Input.ProxyBinding oldBinding, Game.Input.ProxyBinding newBinding) : System.Void`  

```csharp
private void Process(ProxyBinding oldBinding, ProxyBinding newBinding)
	{
		UISystemBase.log.InfoFormat("Rebinding from {0} to {1}", oldBinding, newBinding);
		if (newBinding.action == null)
		{
			Reset();
			return;
		}
		if (!NeedAskUser(newBinding))
		{
			Apply(newBinding);
			Reset();
			return;
		}
		m_Conflicts.Clear();
		GetRebindOptions(m_Conflicts, oldBinding, newBinding, out var unsolved, out var batchSwap, out var swap, out var unset);
		if (m_Conflicts.Count == 0)
		{
			Apply(newBinding);
			Reset();
			return;
		}
		m_PendingRebinding = newBinding;
		m_ActiveConflictBinding.Update(new ConflictInfo
		{
			binding = newBinding,
			conflicts = m_Conflicts.Values.OrderBy((ConflictInfoItem b) => b.binding.mapName).ToArray(),
			unsolved = unsolved,
			swap = swap,
			unset = unset,
			batchSwap = batchSwap
		});
		static bool NeedAskUser(ProxyBinding binding)
		{
			ProxyAction action = binding.action;
			if (action.m_LinkedActions.Count != 0)
			{
				return true;
			}
			foreach (UIBaseInputAction uIAlias in action.m_UIAliases)
			{
				if (!uIAlias.showInOptions)
				{
					break;
				}
				foreach (UIInputActionPart actionPart in uIAlias.actionParts)
				{
					if ((actionPart.m_Mask & binding.device) != Game.Input.InputManager.DeviceType.None)
					{
						return true;
					}
				}
			}
			return binding.hasConflicts != ProxyBinding.ConflictType.None;
		}
	}
```

- `private ProcessConflict(System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem> conflictInfos, System.Collections.Generic.List<Game.UI.Menu.InputRebindingUISystem+BindingPair> bindingConflicts, Game.Input.Usages& usages, Game.Input.Usages& otherUsages, Game.UI.Menu.InputRebindingUISystem+Options direction, System.Boolean& changed) : System.Void`  

```csharp
private void ProcessConflict(Dictionary<string, ConflictInfoItem> conflictInfos, List<BindingPair> bindingConflicts, ref Usages usages, ref Usages otherUsages, Options direction, out bool changed)
	{
		changed = false;
		for (int i = 0; i < bindingConflicts.Count; i++)
		{
			var (y, x) = bindingConflicts[i];
			if (!Usages.TestAny(usages, y.usages))
			{
				continue;
			}
			bool flag = CanSwap(x, y, direction == Options.Backward);
			bool canBeEmpty = y.canBeEmpty;
			if (!flag && !canBeEmpty)
			{
				AddToConflictInfos(new ConflictInfoItem
				{
					binding = y.Copy(),
					resolution = y.Copy(),
					options = (direction | Options.Unsolved)
				});
				changed = true;
			}
			else if (flag)
			{
				ProxyBinding resolution = y.Copy();
				resolution.path = x.path;
				if (y.allowModifiers && y.isModifiersRebindable)
				{
					resolution.modifiers = x.modifiers;
				}
				AddToConflictInfos(new ConflictInfoItem
				{
					binding = y.Copy(),
					resolution = resolution,
					options = (direction | Options.Swap)
				});
				changed = true;
				otherUsages = Usages.Combine(otherUsages, y.usages);
				foreach (ProxyAction.LinkInfo linkedAction in y.action.m_LinkedActions)
				{
					if (linkedAction.m_Device == x.device && linkedAction.m_Action.TryGetComposite(x.device, out var composite) && composite.TryGetBinding(x.component, out var foundBinding))
					{
						usages = Usages.Combine(usages, foundBinding.usages);
					}
				}
			}
			else if (canBeEmpty)
			{
				ProxyBinding resolution2 = y.Copy();
				resolution2.path = string.Empty;
				resolution2.modifiers = Array.Empty<ProxyModifier>();
				AddToConflictInfos(new ConflictInfoItem
				{
					binding = y.Copy(),
					resolution = resolution2,
					options = (direction | Options.Unset)
				});
				changed = true;
			}
			bindingConflicts.RemoveAt(i);
			i--;
		}
		void AddToConflictInfos(ConflictInfoItem info)
		{
			if (conflictInfos.TryAdd(info.binding.title, info))
			{
				CollectAliases(conflictInfos, info);
			}
		}
	}
```

- `private Reset() : System.Void`  

```csharp
private void Reset()
	{
		m_ActiveRebindingBinding.Update(null);
		m_ActiveConflictBinding.Update(null);
		m_ModifierOperation.Reset();
		m_ActiveRebinding = null;
		m_OnSetBinding = null;
		m_PendingRebinding = null;
		m_Conflicts.Clear();
	}
```

- `public Start(Game.Input.ProxyBinding binding, System.Action<Game.Input.ProxyBinding> onSetBinding) : System.Void`  

```csharp
public void Start(ProxyBinding binding, ProxyBinding newBinding, Action<ProxyBinding> onSetBinding)
	{
		if (!(m_ActiveRebinding == binding) && onSetBinding != null)
		{
			m_ActiveRebinding = binding;
			m_OnSetBinding = onSetBinding;
			m_ActiveRebindingBinding.Update(binding);
			m_ActiveConflictBinding.Update(null);
			Process(binding, newBinding);
		}
	}
```

- `public Start(Game.Input.ProxyBinding binding, Game.Input.ProxyBinding newBinding, System.Action<Game.Input.ProxyBinding> onSetBinding) : System.Void`  

```csharp
public void Start(ProxyBinding binding, ProxyBinding newBinding, Action<ProxyBinding> onSetBinding)
	{
		if (!(m_ActiveRebinding == binding) && onSetBinding != null)
		{
			m_ActiveRebinding = binding;
			m_OnSetBinding = onSetBinding;
			m_ActiveRebindingBinding.Update(binding);
			m_ActiveConflictBinding.Update(null);
			Process(binding, newBinding);
		}
	}
```


## Nested types

- `Game.UI.Menu.InputRebindingUISystem+Options`  
- `Game.UI.Menu.InputRebindingUISystem+BindingPair`  
- `Game.UI.Menu.InputRebindingUISystem+ConflictInfo`  
- `Game.UI.Menu.InputRebindingUISystem+ConflictInfoItem`  
- `Game.UI.Menu.InputRebindingUISystem+<>c`  
- `Game.UI.Menu.InputRebindingUISystem+<>c__DisplayClass17_0`  
- `Game.UI.Menu.InputRebindingUISystem+<>c__DisplayClass28_0`  

