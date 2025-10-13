# Game.UI.Debug.DebugWidgetBuilders

**Assembly:** `Game`  
**Namespace:** `Game.UI.Debug`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class DebugWidgetBuilders
{
    internal static UnityEngine.Vector2 <BuildFloat2Field>g__FromFloat2|11_1(Unity.Mathematics.float2 value);
    internal static Unity.Mathematics.float2 <BuildFloat2Field>g__ToFloat2|11_0(UnityEngine.Vector2 value);
    internal static UnityEngine.Vector3 <BuildFloat3Field>g__FromFloat3|12_1(Unity.Mathematics.float3 value);
    internal static Unity.Mathematics.float3 <BuildFloat3Field>g__ToFloat3|12_0(UnityEngine.Vector3 value);
    internal static UnityEngine.Vector4 <BuildFloat4Field>g__FromFloat4|13_1(Unity.Mathematics.float4 value);
    internal static Unity.Mathematics.float4 <BuildFloat4Field>g__ToFloat4|13_0(UnityEngine.Vector4 value);
    private static Game.UI.Widgets.Button BuildButton(UnityEngine.Rendering.DebugUI+Button debugWidget);
    private static Game.UI.Widgets.ColorField BuildColorField(UnityEngine.Rendering.DebugUI+ColorField debugWidget);
    private static Game.UI.Widgets.EnumField BuildEnumField(UnityEngine.Rendering.DebugUI+EnumField debugWidget);
    private static Game.UI.Widgets.EnumMember[] BuildEnumMembers<T>(UnityEngine.Rendering.DebugUI+EnumField<T> debugWidget);
    private static Game.UI.Widgets.ExpandableGroup BuildExpandableGroup(UnityEngine.Rendering.DebugUI+Foldout debugWidget);
    private static Game.UI.Widgets.FlagsField BuildFlagsField(UnityEngine.Rendering.DebugUI+BitField debugWidget);
    private static Game.UI.Widgets.Float2SliderField BuildFloat2Field(UnityEngine.Rendering.DebugUI+Vector2Field debugWidget);
    private static Game.UI.Widgets.Float3SliderField BuildFloat3Field(UnityEngine.Rendering.DebugUI+Vector3Field debugWidget);
    private static Game.UI.Widgets.Float4SliderField BuildFloat4Field(UnityEngine.Rendering.DebugUI+Vector4Field debugWidget);
    private static Game.UI.Widgets.FloatField<System.Double> BuildFloatField(UnityEngine.Rendering.DebugUI+FloatField debugWidget);
    private static Game.UI.Widgets.Group BuildGroup(UnityEngine.Rendering.DebugUI+Container debugWidget);
    private static Game.UI.Widgets.Group BuildGroup(UnityEngine.Rendering.DebugUI+ValueTuple debugWidget);
    private static Game.UI.Widgets.IntField<System.Int32> BuildIntField(UnityEngine.Rendering.DebugUI+IntField debugWidget);
    private static Game.UI.Debug.IntInputField BuildIntInputField(Game.Debug.IntInputField debugWidget);
    private static Game.UI.Widgets.StringInputField BuildStringInputField(UnityEngine.Rendering.DebugUI+TextField debugWidget);
    private static Game.UI.Widgets.ToggleField BuildToggleField(UnityEngine.Rendering.DebugUI+BoolField debugWidget);
    private static Game.UI.Widgets.UIntField BuildUIntField(UnityEngine.Rendering.DebugUI+UIntField debugWidget);
    private static Game.UI.Debug.ValueField BuildValueField(UnityEngine.Rendering.DebugUI+Value debugWidget);
    public static System.Collections.Generic.IEnumerable<Game.UI.Widgets.IWidget> BuildWidgets(UnityEngine.Rendering.ObservableList<UnityEngine.Rendering.DebugUI+Widget> debugWidgets);
    private static T Invoke<T>(System.Func<T> func, T fallback);
    private static Game.UI.Widgets.IWidget TryBuildWidget(UnityEngine.Rendering.DebugUI+Widget debugWidget);
}
```


## Methods

- `internal static <BuildFloat2Field>g__FromFloat2|11_1(Unity.Mathematics.float2 value) : UnityEngine.Vector2`  

```csharp
internal static UnityEngine.Vector2 <BuildFloat2Field>g__FromFloat2|11_1(Unity.Mathematics.float2 value);
```

- `internal static <BuildFloat2Field>g__ToFloat2|11_0(UnityEngine.Vector2 value) : Unity.Mathematics.float2`  

```csharp
internal static Unity.Mathematics.float2 <BuildFloat2Field>g__ToFloat2|11_0(UnityEngine.Vector2 value);
```

- `internal static <BuildFloat3Field>g__FromFloat3|12_1(Unity.Mathematics.float3 value) : UnityEngine.Vector3`  

```csharp
internal static UnityEngine.Vector3 <BuildFloat3Field>g__FromFloat3|12_1(Unity.Mathematics.float3 value);
```

- `internal static <BuildFloat3Field>g__ToFloat3|12_0(UnityEngine.Vector3 value) : Unity.Mathematics.float3`  

```csharp
internal static Unity.Mathematics.float3 <BuildFloat3Field>g__ToFloat3|12_0(UnityEngine.Vector3 value);
```

- `internal static <BuildFloat4Field>g__FromFloat4|13_1(Unity.Mathematics.float4 value) : UnityEngine.Vector4`  

```csharp
internal static UnityEngine.Vector4 <BuildFloat4Field>g__FromFloat4|13_1(Unity.Mathematics.float4 value);
```

- `internal static <BuildFloat4Field>g__ToFloat4|13_0(UnityEngine.Vector4 value) : Unity.Mathematics.float4`  

```csharp
internal static Unity.Mathematics.float4 <BuildFloat4Field>g__ToFloat4|13_0(UnityEngine.Vector4 value);
```

- `private static BuildButton(UnityEngine.Rendering.DebugUI+Button debugWidget) : Game.UI.Widgets.Button`  

```csharp
private static Button BuildButton(DebugUI.Button debugWidget)
	{
		return new Button
		{
			action = debugWidget.action
		};
	}
```

- `private static BuildColorField(UnityEngine.Rendering.DebugUI+ColorField debugWidget) : Game.UI.Widgets.ColorField`  

```csharp
private static ColorField BuildColorField(DebugUI.ColorField debugWidget)
	{
		return new ColorField
		{
			hdr = debugWidget.hdr,
			showAlpha = debugWidget.showAlpha,
			accessor = new DebugFieldAccessor<Color>(debugWidget)
		};
	}
```

- `private static BuildEnumField(UnityEngine.Rendering.DebugUI+EnumField debugWidget) : Game.UI.Widgets.EnumField`  

```csharp
private static EnumField BuildEnumField(DebugUI.EnumField debugWidget)
	{
		return new EnumField
		{
			enumMembers = BuildEnumMembers(debugWidget),
			accessor = new DelegateAccessor<ulong>(() => (ulong)debugWidget.GetValue(), delegate(ulong value)
			{
				debugWidget.SetValue((int)value);
			})
		};
	}
```

- `private static BuildEnumMembers<T>(UnityEngine.Rendering.DebugUI+EnumField<T> debugWidget) : Game.UI.Widgets.EnumMember[]`  

```csharp
private static Game.UI.Widgets.EnumMember[] BuildEnumMembers<T>(UnityEngine.Rendering.DebugUI+EnumField<T> debugWidget);
```

- `private static BuildExpandableGroup(UnityEngine.Rendering.DebugUI+Foldout debugWidget) : Game.UI.Widgets.ExpandableGroup`  

```csharp
private static ExpandableGroup BuildExpandableGroup(DebugUI.Foldout debugWidget)
	{
		return new ExpandableGroup(new DelegateAccessor<bool>(() => debugWidget.opened, delegate(bool value)
		{
			debugWidget.opened = value;
		}))
		{
			children = new List<IWidget>(BuildWidgets(debugWidget.children))
		};
	}
```

- `private static BuildFlagsField(UnityEngine.Rendering.DebugUI+BitField debugWidget) : Game.UI.Widgets.FlagsField`  

```csharp
private static FlagsField BuildFlagsField(DebugUI.BitField debugWidget)
	{
		if (!EnumFieldBuilders.GetConverters(debugWidget.enumType, out var fromObject, out var toObject))
		{
			fromObject = (object value) => (ulong)(long)value;
			toObject = (ulong value) => (long)value;
		}
		return new FlagsField
		{
			enumMembers = BuildEnumMembers(debugWidget),
			accessor = new DelegateAccessor<ulong>(() => fromObject(debugWidget.GetValue()), delegate(ulong value)
			{
				debugWidget.SetValue(toObject(value));
			})
		};
	}
```

- `private static BuildFloat2Field(UnityEngine.Rendering.DebugUI+Vector2Field debugWidget) : Game.UI.Widgets.Float2SliderField`  

```csharp
private static Float2SliderField BuildFloat2Field(DebugUI.Vector2Field debugWidget)
	{
		return new Float2SliderField
		{
			step = debugWidget.incStep,
			stepMultiplier = debugWidget.incStepMult,
			fractionDigits = debugWidget.decimals,
			accessor = new DebugFieldCastAccessor<float2, Vector2>(debugWidget, ToFloat, FromFloat)
		};
		static Vector2 FromFloat(float2 value)
		{
			return value;
		}
		static float2 ToFloat(Vector2 value)
		{
			return value;
		}
	}
```

- `private static BuildFloat3Field(UnityEngine.Rendering.DebugUI+Vector3Field debugWidget) : Game.UI.Widgets.Float3SliderField`  

```csharp
private static Float3SliderField BuildFloat3Field(DebugUI.Vector3Field debugWidget)
	{
		return new Float3SliderField
		{
			step = debugWidget.incStep,
			stepMultiplier = debugWidget.incStepMult,
			fractionDigits = debugWidget.decimals,
			accessor = new DebugFieldCastAccessor<float3, Vector3>(debugWidget, ToFloat, FromFloat)
		};
		static Vector3 FromFloat(float3 value)
		{
			return value;
		}
		static float3 ToFloat(Vector3 value)
		{
			return value;
		}
	}
```

- `private static BuildFloat4Field(UnityEngine.Rendering.DebugUI+Vector4Field debugWidget) : Game.UI.Widgets.Float4SliderField`  

```csharp
private static Float4SliderField BuildFloat4Field(DebugUI.Vector4Field debugWidget)
	{
		return new Float4SliderField
		{
			step = debugWidget.incStep,
			stepMultiplier = debugWidget.incStepMult,
			fractionDigits = debugWidget.decimals,
			accessor = new DebugFieldCastAccessor<float4, Vector4>(debugWidget, ToFloat, FromFloat)
		};
		static Vector4 FromFloat(float4 value)
		{
			return value;
		}
		static float4 ToFloat(Vector4 value)
		{
			return value;
		}
	}
```

- `private static BuildFloatField(UnityEngine.Rendering.DebugUI+FloatField debugWidget) : Game.UI.Widgets.FloatField<System.Double>`  

```csharp
private static FloatField<double> BuildFloatField(DebugUI.FloatField debugWidget)
	{
		float num = Invoke(debugWidget.min, float.MinValue);
		float num2 = Invoke(debugWidget.max, float.MaxValue);
		DebugFieldCastAccessor<double, float> accessor = new DebugFieldCastAccessor<double, float>(debugWidget, (float value) => value, (double value) => (float)value);
		if (num > float.MinValue && num2 < float.MaxValue)
		{
			return new FloatSliderField
			{
				min = num,
				max = num2,
				step = debugWidget.incStep,
				stepMultiplier = debugWidget.incStepMult,
				accessor = accessor
			};
		}
		return new FloatArrowField
		{
			min = num,
			max = num2,
			step = debugWidget.incStep,
			stepMultiplier = debugWidget.incStepMult,
			accessor = accessor
		};
	}
```

- `private static BuildGroup(UnityEngine.Rendering.DebugUI+Container debugWidget) : Game.UI.Widgets.Group`  

```csharp
private static Group BuildGroup(DebugUI.ValueTuple debugWidget)
	{
		List<IWidget> list = new List<IWidget>(debugWidget.values.Length);
		string[] array = (debugWidget.parent as DebugUI.Foldout)?.columnLabels;
		for (int i = 0; i < debugWidget.values.Length; i++)
		{
			list.Add(new ValueField(debugWidget.values[i])
			{
				path = i,
				displayName = ((array != null && array.Length > i) ? array[i] : string.Empty)
			});
		}
		return new Group
		{
			children = list
		};
	}
```

- `private static BuildGroup(UnityEngine.Rendering.DebugUI+ValueTuple debugWidget) : Game.UI.Widgets.Group`  

```csharp
private static Group BuildGroup(DebugUI.ValueTuple debugWidget)
	{
		List<IWidget> list = new List<IWidget>(debugWidget.values.Length);
		string[] array = (debugWidget.parent as DebugUI.Foldout)?.columnLabels;
		for (int i = 0; i < debugWidget.values.Length; i++)
		{
			list.Add(new ValueField(debugWidget.values[i])
			{
				path = i,
				displayName = ((array != null && array.Length > i) ? array[i] : string.Empty)
			});
		}
		return new Group
		{
			children = list
		};
	}
```

- `private static BuildIntField(UnityEngine.Rendering.DebugUI+IntField debugWidget) : Game.UI.Widgets.IntField<System.Int32>`  

```csharp
private static IntField<int> BuildIntField(DebugUI.IntField debugWidget)
	{
		int num = Invoke(debugWidget.min, int.MinValue);
		int num2 = Invoke(debugWidget.max, int.MaxValue);
		DebugFieldAccessor<int> accessor = new DebugFieldAccessor<int>(debugWidget);
		if (num > int.MinValue && num2 < int.MaxValue)
		{
			return new IntSliderField
			{
				min = num,
				max = num2,
				step = debugWidget.incStep,
				stepMultiplier = debugWidget.intStepMult,
				accessor = accessor
			};
		}
		return new IntArrowField
		{
			step = debugWidget.incStep,
			stepMultiplier = debugWidget.intStepMult,
			accessor = accessor
		};
	}
```

- `private static BuildIntInputField(Game.Debug.IntInputField debugWidget) : Game.UI.Debug.IntInputField`  

```csharp
private static IntInputField BuildIntInputField(Game.Debug.IntInputField debugWidget)
	{
		return new IntInputField(debugWidget);
	}
```

- `private static BuildStringInputField(UnityEngine.Rendering.DebugUI+TextField debugWidget) : Game.UI.Widgets.StringInputField`  

```csharp
private static StringInputField BuildStringInputField(DebugUI.TextField debugWidget)
	{
		return new StringInputField
		{
			accessor = new DebugFieldAccessor<string>(debugWidget)
		};
	}
```

- `private static BuildToggleField(UnityEngine.Rendering.DebugUI+BoolField debugWidget) : Game.UI.Widgets.ToggleField`  

```csharp
private static ToggleField BuildToggleField(DebugUI.BoolField debugWidget)
	{
		return new ToggleField
		{
			accessor = new DebugFieldAccessor<bool>(debugWidget)
		};
	}
```

- `private static BuildUIntField(UnityEngine.Rendering.DebugUI+UIntField debugWidget) : Game.UI.Widgets.UIntField`  

```csharp
private static UIntField BuildUIntField(DebugUI.UIntField debugWidget)
	{
		uint num = Invoke(debugWidget.min, 0u);
		uint num2 = Invoke(debugWidget.max, uint.MaxValue);
		DebugFieldAccessor<uint> accessor = new DebugFieldAccessor<uint>(debugWidget);
		if (num != 0 && num2 < uint.MaxValue)
		{
			return new UIntSliderField
			{
				min = num,
				max = num2,
				step = debugWidget.incStep,
				stepMultiplier = debugWidget.intStepMult,
				accessor = accessor
			};
		}
		return new UIntArrowField
		{
			step = debugWidget.incStep,
			stepMultiplier = debugWidget.intStepMult,
			accessor = accessor
		};
	}
```

- `private static BuildValueField(UnityEngine.Rendering.DebugUI+Value debugWidget) : Game.UI.Debug.ValueField`  

```csharp
private static ValueField BuildValueField(DebugUI.Value debugWidget)
	{
		return new ValueField(debugWidget);
	}
```

- `public static BuildWidgets(UnityEngine.Rendering.ObservableList<UnityEngine.Rendering.DebugUI+Widget> debugWidgets) : System.Collections.Generic.IEnumerable<Game.UI.Widgets.IWidget>`  

```csharp
public static IEnumerable<IWidget> BuildWidgets(ObservableList<DebugUI.Widget> debugWidgets)
	{
		foreach (DebugUI.Widget debugWidget in debugWidgets)
		{
			if (debugWidget.isEditorOnly)
			{
				continue;
			}
			IWidget widget = TryBuildWidget(debugWidget);
			if (widget != null)
			{
				if (widget is INamed named)
				{
					named.displayName = LocalizedString.Value(debugWidget.displayName);
				}
				yield return widget;
			}
		}
	}
```

- `private static Invoke<T>(System.Func<T> func, T fallback) : T`  

```csharp
private static T Invoke<T>(System.Func<T> func, T fallback);
```

- `private static TryBuildWidget(UnityEngine.Rendering.DebugUI+Widget debugWidget) : Game.UI.Widgets.IWidget`  

```csharp
[CanBeNull]
	private static IWidget TryBuildWidget(DebugUI.Widget debugWidget)
	{
		if (debugWidget is DebugUI.Foldout debugWidget2)
		{
			return BuildExpandableGroup(debugWidget2);
		}
		if (debugWidget is DebugUI.Container debugWidget3)
		{
			return BuildGroup(debugWidget3);
		}
		if (debugWidget is DebugUI.ValueTuple debugWidget4)
		{
			return BuildGroup(debugWidget4);
		}
		if (debugWidget is DebugUI.Button debugWidget5)
		{
			return BuildButton(debugWidget5);
		}
		if (debugWidget is DebugUI.Value debugWidget6)
		{
			return BuildValueField(debugWidget6);
		}
		if (debugWidget is DebugUI.BoolField debugWidget7)
		{
			return BuildToggleField(debugWidget7);
		}
		if (debugWidget is DebugUI.IntField debugWidget8)
		{
			return BuildIntField(debugWidget8);
		}
		if (debugWidget is Game.Debug.IntInputField debugWidget9)
		{
			return BuildIntInputField(debugWidget9);
		}
		if (debugWidget is DebugUI.UIntField debugWidget10)
		{
			return BuildUIntField(debugWidget10);
		}
		if (debugWidget is DebugUI.FloatField debugWidget11)
		{
			return BuildFloatField(debugWidget11);
		}
		if (debugWidget is DebugUI.Vector2Field debugWidget12)
		{
			return BuildFloat2Field(debugWidget12);
		}
		if (debugWidget is DebugUI.Vector3Field debugWidget13)
		{
			return BuildFloat3Field(debugWidget13);
		}
		if (debugWidget is DebugUI.Vector4Field debugWidget14)
		{
			return BuildFloat4Field(debugWidget14);
		}
		if (debugWidget is DebugUI.EnumField debugWidget15)
		{
			return BuildEnumField(debugWidget15);
		}
		if (debugWidget is DebugUI.BitField debugWidget16)
		{
			return BuildFlagsField(debugWidget16);
		}
		if (debugWidget is DebugUI.ColorField debugWidget17)
		{
			return BuildColorField(debugWidget17);
		}
		if (debugWidget is DebugUI.TextField debugWidget18)
		{
			return BuildStringInputField(debugWidget18);
		}
		return null;
	}
```


## Nested types

- `Game.UI.Debug.DebugWidgetBuilders+<>c`  
- `Game.UI.Debug.DebugWidgetBuilders+<>c__DisplayClass14_0`  
- `Game.UI.Debug.DebugWidgetBuilders+<>c__DisplayClass15_0`  
- `Game.UI.Debug.DebugWidgetBuilders+<>c__DisplayClass2_0`  
- `Game.UI.Debug.DebugWidgetBuilders+<BuildWidgets>d__0`  

