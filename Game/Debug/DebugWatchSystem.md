# Game.Debug.DebugWatchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class DebugWatchSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private System.Collections.Generic.List<Game.Debug.DebugWatchSystem+ManagedSystemState> m_ManagedSystemStates;
    private System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch> m_Watches;
    private System.UInt32 m_LastFrameIndex;
    private System.Boolean m_WatchesChanged;
    private static readonly System.String[] colors;

    public System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch> watches { get; }
    public System.Boolean watchesChanged { get; }

    public DebugWatchSystem();

    internal static UnityEngine.Rendering.DebugUI+Widget <BuildSystemFoldouts>g__Value|15_3(System.String name, Game.Reflection.IValueAccessor accessor);
    internal static UnityEngine.Rendering.DebugUI+Widget <BuildSystemFoldouts>g__ValueContainer|15_2(System.String name, Game.Reflection.IValueAccessor accessor);
    public System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildSystemFoldouts();
    public System.Void ClearWatches();
    public System.Void ClearWatchesChanged();
    public static Game.Reflection.IValueAccessor CreateTypedAccessor(Game.Reflection.IValueAccessor accessor);
    private static System.String GetArrayItemName(System.Reflection.MemberInfo member, System.Int32 index);
    private static System.Reflection.FieldInfo[] GetWatchDepsFields(System.Type systemType);
    private static System.Collections.Generic.IEnumerable<System.Reflection.MemberInfo> GetWatchValueMembers(System.Type systemType);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private System.Collections.Generic.List<Game.Debug.DebugWatchSystem+ManagedSystemState> m_ManagedSystemStates`  

```csharp
private System.Collections.Generic.List<Game.Debug.DebugWatchSystem+ManagedSystemState> m_ManagedSystemStates;
```

- `private System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch> m_Watches`  

```csharp
private System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch> m_Watches;
```

- `private System.UInt32 m_LastFrameIndex`  

```csharp
private System.UInt32 m_LastFrameIndex;
```

- `private System.Boolean m_WatchesChanged`  

```csharp
private System.Boolean m_WatchesChanged;
```

- `private static readonly System.String[] colors`  

```csharp
private static readonly System.String[] colors;
```


## Properties

- `public System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch> watches { get }`  

```csharp
public System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch> watches { get; }
```

- `public System.Boolean watchesChanged { get }`  

```csharp
public System.Boolean watchesChanged { get; }
```


## Constructors

- `public DebugWatchSystem()`  

```csharp
[Preserve]
	public DebugWatchSystem()
	{
	}
```


## Methods

- `internal static <BuildSystemFoldouts>g__Value|15_3(System.String name, Game.Reflection.IValueAccessor accessor) : UnityEngine.Rendering.DebugUI+Widget`  

```csharp
internal static UnityEngine.Rendering.DebugUI+Widget <BuildSystemFoldouts>g__Value|15_3(System.String name, Game.Reflection.IValueAccessor accessor);
```

- `internal static <BuildSystemFoldouts>g__ValueContainer|15_2(System.String name, Game.Reflection.IValueAccessor accessor) : UnityEngine.Rendering.DebugUI+Widget`  

```csharp
internal static UnityEngine.Rendering.DebugUI+Widget <BuildSystemFoldouts>g__ValueContainer|15_2(System.String name, Game.Reflection.IValueAccessor accessor);
```

- `public BuildSystemFoldouts() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
public List<DebugUI.Widget> BuildSystemFoldouts()
	{
		m_ManagedSystemStates.Clear();
		int colorIndex = 0;
		List<DebugUI.Widget> list = new List<DebugUI.Widget>();
		foreach (ComponentSystemBase system in base.World.Systems)
		{
			Type type = system.GetType();
			if (!GetWatchValueMembers(type).Any())
			{
				continue;
			}
			DebugUI.Foldout foldout = new DebugUI.Foldout
			{
				displayName = type.Name
			};
			list.Add(foldout);
			UpdateSystem.GetInterval(system, SystemUpdatePhase.GameSimulation, out var interval, out var offset);
			ObjectWithDepsAccessor<object> parent = new ObjectWithDepsAccessor<object>(system, GetWatchDepsFields(type));
			foreach (MemberInfo watchValueMember in GetWatchValueMembers(type))
			{
				DebugWatchValueAttribute customAttribute = watchValueMember.GetCustomAttribute<DebugWatchValueAttribute>();
				string text = WidgetReflectionUtils.NicifyVariableName(watchValueMember.Name);
				int updateInterval = ((customAttribute.updateInterval <= 0) ? interval : customAttribute.updateInterval);
				IValueAccessor valueAccessor = ValueAccessorUtils.CreateMemberAccessor(parent, watchValueMember);
				if (valueAccessor != null)
				{
					IValueAccessor valueAccessor2 = CreateTypedAccessor(valueAccessor);
					if (valueAccessor2 != null)
					{
						valueAccessor = valueAccessor2;
					}
				}
				Watch watch = Watch.TryCreate(valueAccessor, customAttribute.historyLength, updateInterval);
				if (watch != null)
				{
					foldout.opened |= m_Watches.Contains(watch);
					watch.m_System = system;
					watch.m_DisplayName = text;
					watch.m_Color = NextColor(customAttribute);
					foldout.children.Add(WatchToggle(text, watch));
				}
				else
				{
					foldout.children.Add(new DebugUI.Value
					{
						displayName = text,
						getter = () => ""
					});
				}
				Type type2 = valueAccessor?.valueType;
				if (type2 != null && type2.IsGenericType && type2.GetGenericTypeDefinition() == typeof(NativeArray<>))
				{
					object value = valueAccessor.GetValue();
					int num = math.min((int)type2.GetProperty("Length").GetGetMethod().Invoke(value, null), 100);
					DebugUI.Foldout foldout2 = new DebugUI.Foldout
					{
						displayName = "Values"
					};
					DebugUI.Foldout foldout3 = new DebugUI.Foldout
					{
						displayName = "Watches"
					};
					List<Watch> itemWatches = new List<Watch>();
					for (int num2 = 0; num2 < num; num2++)
					{
						string arrayItemName = GetArrayItemName(watchValueMember, num2);
						IValueAccessor accessor = ValueAccessorUtils.CreateNativeArrayItemAccessor(valueAccessor, num2);
						Watch watch2 = Watch.TryCreate(accessor, customAttribute.historyLength, updateInterval);
						foldout2.children.Add(Value(arrayItemName, accessor));
						if (watch2 != null)
						{
							itemWatches.Add(watch2);
							foldout2.opened |= m_Watches.Contains(watch2);
							watch2.m_System = system;
							watch2.m_DisplayName = text + " [" + arrayItemName + "]";
							watch2.m_Color = colors[colorIndex * 23 % colors.Length];
							offset = colorIndex;
							colorIndex = offset + 1;
							foldout3.children.Add(WatchToggle(arrayItemName, watch2));
						}
					}
					DebugUI.Container container = new DebugUI.Container();
					if (foldout2.children.Count > 0)
					{
						container.children.Add(foldout2);
					}
					if (foldout3.children.Count > 0)
					{
						container.children.Add(foldout3);
					}
					if (itemWatches.Count > 0)
					{
						container.children.Add(new DebugUI.BoolField
						{
							displayName = $"All Values ({itemWatches.Count})",
							getter = () => itemWatches.All((Watch w) => m_Watches.Contains(w)),
							setter = delegate(bool v)
							{
								m_Watches.RemoveAll((Watch w) => itemWatches.Contains(w));
								if (v)
								{
									m_Watches.AddRange(itemWatches);
								}
								m_WatchesChanged = true;
							}
						});
					}
					if (container.children.Count > 0)
					{
						foldout.children.Add(container);
					}
				}
				else
				{
					foldout.children.Add(ValueContainer("Value", valueAccessor));
				}
			}
			if (type.HasAttribute<DebugWatchOnlyAttribute>())
			{
				system.Enabled = foldout.opened;
				m_ManagedSystemStates.Add(new ManagedSystemState
				{
					m_System = system,
					m_Foldout = foldout
				});
			}
		}
		list.Sort((DebugUI.Widget a, DebugUI.Widget b) => string.Compare(a.displayName, b.displayName, StringComparison.Ordinal));
		return list;
		string NextColor(DebugWatchValueAttribute attr = null)
		{
			if (attr.color != null)
			{
				return attr.color;
			}
			colorIndex++;
			return colors[colorIndex * 23 % colors.Length];
		}
		static DebugUI.Widget Value(string name, IValueAccessor valueAccessor3)
		{
			return new DebugUI.Value
			{
				displayName = name,
				getter = () => valueAccessor3?.GetValue(),
				refreshRate = 0.2f
			};
		}
		static DebugUI.Widget ValueContainer(string name, IValueAccessor accessor2)
		{
			return new DebugUI.Container
			{
				children = { Value(name, accessor2) }
			};
		}
		DebugUI.Widget WatchToggle(string name, Watch watch3)
		{
			return new DebugUI.BoolField
			{
				displayName = name,
				getter = () => m_Watches.Contains(watch3),
				setter = delegate(bool v)
				{
					if (v)
					{
						m_Watches.Add(watch3);
						watch3.Enable();
					}
					else
					{
						watch3.Disable();
						m_Watches.Remove(watch3);
					}
					m_WatchesChanged = true;
				}
			};
		}
	}
```

- `public ClearWatches() : System.Void`  

```csharp
public void ClearWatches()
	{
		m_Watches.Clear();
		m_WatchesChanged = true;
	}
```

- `public ClearWatchesChanged() : System.Void`  

```csharp
public void ClearWatchesChanged()
	{
		m_WatchesChanged = false;
	}
```

- `public static CreateTypedAccessor(Game.Reflection.IValueAccessor accessor) : Game.Reflection.IValueAccessor`  

```csharp
[CanBeNull]
	public static IValueAccessor CreateTypedAccessor(IValueAccessor accessor)
	{
		Type valueType = accessor.valueType;
		if (valueType == typeof(int))
		{
			return new CastAccessor<int>(accessor);
		}
		if (valueType == typeof(uint))
		{
			return new CastAccessor<uint>(accessor);
		}
		if (valueType == typeof(float))
		{
			return new CastAccessor<float>(accessor);
		}
		if (valueType.IsGenericType && valueType.GetGenericTypeDefinition() == typeof(NativeValue<>))
		{
			Type type = valueType.GenericTypeArguments[0];
			if (type == typeof(int))
			{
				return new NativeValueAccessor<int>(accessor);
			}
			if (type == typeof(uint))
			{
				return new NativeValueAccessor<uint>(accessor);
			}
			if (type == typeof(float))
			{
				return new NativeValueAccessor<float>(accessor);
			}
			if (type == typeof(int2))
			{
				return new NativeValueAccessor<int2>(accessor);
			}
			if (type == typeof(uint2))
			{
				return new NativeValueAccessor<uint2>(accessor);
			}
			if (type == typeof(float2))
			{
				return new NativeValueAccessor<float2>(accessor);
			}
			if (type == typeof(int3))
			{
				return new NativeValueAccessor<int3>(accessor);
			}
			if (type == typeof(uint3))
			{
				return new NativeValueAccessor<uint3>(accessor);
			}
			if (type == typeof(float3))
			{
				return new NativeValueAccessor<float3>(accessor);
			}
		}
		return accessor;
	}
```

- `private static GetArrayItemName(System.Reflection.MemberInfo member, System.Int32 index) : System.String`  

```csharp
private static string GetArrayItemName(MemberInfo member, int index)
	{
		if (member.HasAttribute<ResourceArrayAttribute>())
		{
			return EconomyUtils.GetResource(index).ToString();
		}
		if (member.HasAttribute<EnumArrayAttribute>())
		{
			return Enum.GetName(member.GetCustomAttribute<EnumArrayAttribute>().type, index);
		}
		return index.ToString();
	}
```

- `private static GetWatchDepsFields(System.Type systemType) : System.Reflection.FieldInfo[]`  

```csharp
private static FieldInfo[] GetWatchDepsFields(Type systemType)
	{
		return (from f in systemType.GetFields(BindingFlags.Instance | BindingFlags.Public | BindingFlags.NonPublic)
			where f.FieldType == typeof(JobHandle) && f.HasAttribute<DebugWatchDepsAttribute>()
			select f).ToArray();
	}
```

- `private static GetWatchValueMembers(System.Type systemType) : System.Collections.Generic.IEnumerable<System.Reflection.MemberInfo>`  

```csharp
private static IEnumerable<MemberInfo> GetWatchValueMembers(Type systemType)
	{
		return from m in systemType.GetMembers(BindingFlags.Instance | BindingFlags.Public | BindingFlags.NonPublic)
			where (m is PropertyInfo || m is FieldInfo || m is MethodInfo) && m.HasAttribute<DebugWatchValueAttribute>()
			select m;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ManagedSystemStates = new List<ManagedSystemState>();
		m_Watches = new List<Watch>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		base.Enabled = false;
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		base.OnStopRunning();
		foreach (ManagedSystemState managedSystemState in m_ManagedSystemStates)
		{
			managedSystemState.m_System.Enabled = false;
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		foreach (ManagedSystemState entry in m_ManagedSystemStates)
		{
			entry.m_System.Enabled = entry.m_Foldout.opened || m_Watches.Any((Watch w) => w.m_System == entry.m_System);
		}
		if (m_SimulationSystem.frameIndex == m_LastFrameIndex)
		{
			return;
		}
		m_LastFrameIndex = m_SimulationSystem.frameIndex;
		foreach (Watch watch in m_Watches)
		{
			m_WatchesChanged |= watch.Advance(m_SimulationSystem.frameIndex);
		}
	}
```


## Nested types

- `Game.Debug.DebugWatchSystem+ManagedSystemState`  
- `Game.Debug.DebugWatchSystem+Watch`  
- `Game.Debug.DebugWatchSystem+HistoryWatch<T>`  
- `Game.Debug.DebugWatchSystem+DistributionWatch`  
- `Game.Debug.DebugWatchSystem+<>c`  
- `Game.Debug.DebugWatchSystem+<>c__DisplayClass11_0`  
- `Game.Debug.DebugWatchSystem+<>c__DisplayClass15_0`  
- `Game.Debug.DebugWatchSystem+<>c__DisplayClass15_1`  
- `Game.Debug.DebugWatchSystem+<>c__DisplayClass15_2`  
- `Game.Debug.DebugWatchSystem+<>c__DisplayClass15_3`  

