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
private static Game.UI.Widgets.Button BuildButton(UnityEngine.Rendering.DebugUI+Button debugWidget);
```

- `private static BuildColorField(UnityEngine.Rendering.DebugUI+ColorField debugWidget) : Game.UI.Widgets.ColorField`  

```csharp
private static Game.UI.Widgets.ColorField BuildColorField(UnityEngine.Rendering.DebugUI+ColorField debugWidget);
```

- `private static BuildEnumField(UnityEngine.Rendering.DebugUI+EnumField debugWidget) : Game.UI.Widgets.EnumField`  

```csharp
private static Game.UI.Widgets.EnumField BuildEnumField(UnityEngine.Rendering.DebugUI+EnumField debugWidget);
```

- `private static BuildEnumMembers<T>(UnityEngine.Rendering.DebugUI+EnumField<T> debugWidget) : Game.UI.Widgets.EnumMember[]`  

```csharp
private static Game.UI.Widgets.EnumMember[] BuildEnumMembers<T>(UnityEngine.Rendering.DebugUI+EnumField<T> debugWidget);
```

- `private static BuildExpandableGroup(UnityEngine.Rendering.DebugUI+Foldout debugWidget) : Game.UI.Widgets.ExpandableGroup`  

```csharp
private static Game.UI.Widgets.ExpandableGroup BuildExpandableGroup(UnityEngine.Rendering.DebugUI+Foldout debugWidget);
```

- `private static BuildFlagsField(UnityEngine.Rendering.DebugUI+BitField debugWidget) : Game.UI.Widgets.FlagsField`  

```csharp
private static Game.UI.Widgets.FlagsField BuildFlagsField(UnityEngine.Rendering.DebugUI+BitField debugWidget);
```

- `private static BuildFloat2Field(UnityEngine.Rendering.DebugUI+Vector2Field debugWidget) : Game.UI.Widgets.Float2SliderField`  

```csharp
private static Game.UI.Widgets.Float2SliderField BuildFloat2Field(UnityEngine.Rendering.DebugUI+Vector2Field debugWidget);
```

- `private static BuildFloat3Field(UnityEngine.Rendering.DebugUI+Vector3Field debugWidget) : Game.UI.Widgets.Float3SliderField`  

```csharp
private static Game.UI.Widgets.Float3SliderField BuildFloat3Field(UnityEngine.Rendering.DebugUI+Vector3Field debugWidget);
```

- `private static BuildFloat4Field(UnityEngine.Rendering.DebugUI+Vector4Field debugWidget) : Game.UI.Widgets.Float4SliderField`  

```csharp
private static Game.UI.Widgets.Float4SliderField BuildFloat4Field(UnityEngine.Rendering.DebugUI+Vector4Field debugWidget);
```

- `private static BuildFloatField(UnityEngine.Rendering.DebugUI+FloatField debugWidget) : Game.UI.Widgets.FloatField<System.Double>`  

```csharp
private static Game.UI.Widgets.FloatField<System.Double> BuildFloatField(UnityEngine.Rendering.DebugUI+FloatField debugWidget);
```

- `private static BuildGroup(UnityEngine.Rendering.DebugUI+Container debugWidget) : Game.UI.Widgets.Group`  

```csharp
private static Game.UI.Widgets.Group BuildGroup(UnityEngine.Rendering.DebugUI+Container debugWidget);
```

- `private static BuildGroup(UnityEngine.Rendering.DebugUI+ValueTuple debugWidget) : Game.UI.Widgets.Group`  

```csharp
private static Game.UI.Widgets.Group BuildGroup(UnityEngine.Rendering.DebugUI+ValueTuple debugWidget);
```

- `private static BuildIntField(UnityEngine.Rendering.DebugUI+IntField debugWidget) : Game.UI.Widgets.IntField<System.Int32>`  

```csharp
private static Game.UI.Widgets.IntField<System.Int32> BuildIntField(UnityEngine.Rendering.DebugUI+IntField debugWidget);
```

- `private static BuildIntInputField(Game.Debug.IntInputField debugWidget) : Game.UI.Debug.IntInputField`  

```csharp
private static Game.UI.Debug.IntInputField BuildIntInputField(Game.Debug.IntInputField debugWidget);
```

- `private static BuildStringInputField(UnityEngine.Rendering.DebugUI+TextField debugWidget) : Game.UI.Widgets.StringInputField`  

```csharp
private static Game.UI.Widgets.StringInputField BuildStringInputField(UnityEngine.Rendering.DebugUI+TextField debugWidget);
```

- `private static BuildToggleField(UnityEngine.Rendering.DebugUI+BoolField debugWidget) : Game.UI.Widgets.ToggleField`  

```csharp
private static Game.UI.Widgets.ToggleField BuildToggleField(UnityEngine.Rendering.DebugUI+BoolField debugWidget);
```

- `private static BuildUIntField(UnityEngine.Rendering.DebugUI+UIntField debugWidget) : Game.UI.Widgets.UIntField`  

```csharp
private static Game.UI.Widgets.UIntField BuildUIntField(UnityEngine.Rendering.DebugUI+UIntField debugWidget);
```

- `private static BuildValueField(UnityEngine.Rendering.DebugUI+Value debugWidget) : Game.UI.Debug.ValueField`  

```csharp
private static Game.UI.Debug.ValueField BuildValueField(UnityEngine.Rendering.DebugUI+Value debugWidget);
```

- `public static BuildWidgets(UnityEngine.Rendering.ObservableList<UnityEngine.Rendering.DebugUI+Widget> debugWidgets) : System.Collections.Generic.IEnumerable<Game.UI.Widgets.IWidget>`  

```csharp
public static System.Collections.Generic.IEnumerable<Game.UI.Widgets.IWidget> BuildWidgets(UnityEngine.Rendering.ObservableList<UnityEngine.Rendering.DebugUI+Widget> debugWidgets);
```

- `private static Invoke<T>(System.Func<T> func, T fallback) : T`  

```csharp
private static T Invoke<T>(System.Func<T> func, T fallback);
```

- `private static TryBuildWidget(UnityEngine.Rendering.DebugUI+Widget debugWidget) : Game.UI.Widgets.IWidget`  

```csharp
private static Game.UI.Widgets.IWidget TryBuildWidget(UnityEngine.Rendering.DebugUI+Widget debugWidget);
```


## Nested types

- `Game.UI.Debug.DebugWidgetBuilders+<>c`  
- `Game.UI.Debug.DebugWidgetBuilders+<>c__DisplayClass14_0`  
- `Game.UI.Debug.DebugWidgetBuilders+<>c__DisplayClass15_0`  
- `Game.UI.Debug.DebugWidgetBuilders+<>c__DisplayClass2_0`  
- `Game.UI.Debug.DebugWidgetBuilders+<BuildWidgets>d__0`  

