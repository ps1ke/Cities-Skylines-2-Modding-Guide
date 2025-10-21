# Game.Rendering.CinematicCamera.PhotoModeUtils

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.CinematicCamera`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class PhotoModeUtils
{
    public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.FloatParameter>> expression, System.Func<System.Boolean> isAvailable);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.FloatParameter>> expression, System.Single min, System.Single max, System.Func<System.Boolean> isAvailable);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.MinFloatParameter>> expression, System.Func<System.Boolean> isAvailable);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector4Parameter>> expression, System.Func<UnityEngine.Vector4, System.Single> getter, System.Func<UnityEngine.Vector4, System.Single, UnityEngine.Vector4> setter, System.Single min, System.Single max, System.Func<System.Boolean> isAvailable);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.OverridableProperty<System.Single>>> expression, System.Func<System.Boolean> isAvailable);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.ClampedFloatParameter>> expression, System.Func<System.Boolean> isAvailable);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.ClampedIntParameter>> expression, System.Func<System.Boolean> isAvailable);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single>>> expression, System.Single min, System.Single max, System.Func<System.Single, System.Single> from, System.Func<System.Single, System.Single> to, System.Func<System.Boolean> isAvailable);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single>>> expression, System.Func<System.Single> min, System.Func<System.Single> max, System.Func<System.Single, System.Single> from, System.Func<System.Single, System.Single> to, System.Func<System.Boolean> isAvailable);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<System.Int32>>> expression, System.Int32 min, System.Int32 max, System.Func<System.Boolean> isAvailable);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<System.Int32>>> expression, System.Int32 min, System.Func<System.Boolean> isAvailable);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty<T>(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.VolumeParameter<T>>> expression, System.Func<System.Boolean> isAvailable);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty<T>(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<T>>> expression, System.Func<System.Boolean> isAvailable);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.BoolParameter>> expression, System.Func<System.Boolean> isAvailable);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.ColorParameter>> expression);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector2Parameter>> expression, System.Single min, System.Single max);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector2Parameter>> expression, Colossal.Mathematics.Bounds1 bounds);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector2Parameter>> expression, Colossal.Mathematics.Bounds1 xBounds, Colossal.Mathematics.Bounds1 yBounds);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector2Parameter>> expression);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector3Parameter>> expression, System.Single min, System.Single max);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector3Parameter>> expression, Colossal.Mathematics.Bounds1 bounds);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector3Parameter>> expression, Colossal.Mathematics.Bounds1 xBounds, Colossal.Mathematics.Bounds1 yBounds, Colossal.Mathematics.Bounds1 zBounds);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector3Parameter>> expression);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2>>> expression);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2>>> expression, System.Single min, System.Single max);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2>>> expression, Colossal.Mathematics.Bounds1 bounds);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2>>> expression, Colossal.Mathematics.Bounds1 xBounds, Colossal.Mathematics.Bounds1 yBounds);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty BindPropertyW(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector4Parameter>> expression, System.Single min, System.Single max, System.Func<System.Boolean> isAvailable);
    public static System.Single BooleanToFloat(System.Boolean value);
    public static Game.UI.InGame.PhotoModeUIPreset CreatePreset(System.String name, Game.Rendering.CinematicCamera.PhotoModeProperty injectionProperty, Game.Rendering.CinematicCamera.PhotoModeProperty[] targetProperties, System.String[] options, UnityEngine.Vector2[] values);
    private static T ExtractMember<T>(System.Linq.Expressions.Expression<System.Func<T>> expression, System.String& name);
    private static T ExtractMember<T>(System.Linq.Expressions.Expression<System.Func<T>> expression, System.String& name, Game.GameSystemBase& systemBase);
    public static System.Collections.Generic.IEnumerable<Game.Rendering.CinematicCamera.PhotoModeProperty> ExtractMultiPropertyComponents(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> allProperties);
    public static System.String ExtractPropertyID(Game.Rendering.CinematicCamera.PhotoModeProperty property);
    public static T FindClosestEnumValue<T>(System.Single value);
    public static System.Boolean FloatToBoolean(System.Single value);
    public static Game.Rendering.CinematicCamera.PhotoModeProperty GroupTitle(System.String tab, System.String name);
}
```


## Methods

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.FloatParameter>> expression, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.FloatParameter>> expression, System.Func<System.Boolean> isAvailable);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.FloatParameter>> expression, System.Single min, System.Single max, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.FloatParameter>> expression, System.Single min, System.Single max, System.Func<System.Boolean> isAvailable);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.MinFloatParameter>> expression, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.MinFloatParameter>> expression, System.Func<System.Boolean> isAvailable);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector4Parameter>> expression, System.Func<UnityEngine.Vector4, System.Single> getter, System.Func<UnityEngine.Vector4, System.Single, UnityEngine.Vector4> setter, System.Single min, System.Single max, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector4Parameter>> expression, System.Func<UnityEngine.Vector4, System.Single> getter, System.Func<UnityEngine.Vector4, System.Single, UnityEngine.Vector4> setter, System.Single min, System.Single max, System.Func<System.Boolean> isAvailable);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.OverridableProperty<System.Single>>> expression, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.OverridableProperty<System.Single>>> expression, System.Func<System.Boolean> isAvailable);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.ClampedFloatParameter>> expression, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.ClampedFloatParameter>> expression, System.Func<System.Boolean> isAvailable);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.ClampedIntParameter>> expression, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.ClampedIntParameter>> expression, System.Func<System.Boolean> isAvailable);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single>>> expression, System.Single min, System.Single max, System.Func<System.Single, System.Single> from = null, System.Func<System.Single, System.Single> to = null, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single>>> expression, System.Single min, System.Single max, System.Func<System.Single, System.Single> from, System.Func<System.Single, System.Single> to, System.Func<System.Boolean> isAvailable);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single>>> expression, System.Func<System.Single> min, System.Func<System.Single> max, System.Func<System.Single, System.Single> from = null, System.Func<System.Single, System.Single> to = null, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single>>> expression, System.Func<System.Single> min, System.Func<System.Single> max, System.Func<System.Single, System.Single> from, System.Func<System.Single, System.Single> to, System.Func<System.Boolean> isAvailable);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<System.Int32>>> expression, System.Int32 min, System.Int32 max, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<System.Int32>>> expression, System.Int32 min, System.Int32 max, System.Func<System.Boolean> isAvailable);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<System.Int32>>> expression, System.Int32 min, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<System.Int32>>> expression, System.Int32 min, System.Func<System.Boolean> isAvailable);
```

- `public static BindProperty<T>(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.VolumeParameter<T>>> expression, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty<T>(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.VolumeParameter<T>>> expression, System.Func<System.Boolean> isAvailable);
```

- `public static BindProperty<T>(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<T>>> expression, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty<T>(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<T>>> expression, System.Func<System.Boolean> isAvailable);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.BoolParameter>> expression, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.BoolParameter>> expression, System.Func<System.Boolean> isAvailable);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.ColorParameter>> expression) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.ColorParameter>> expression);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector2Parameter>> expression, System.Single min, System.Single max) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector2Parameter>> expression, System.Single min, System.Single max);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector2Parameter>> expression, Colossal.Mathematics.Bounds1 bounds) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector2Parameter>> expression, Colossal.Mathematics.Bounds1 bounds);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector2Parameter>> expression, Colossal.Mathematics.Bounds1 xBounds, Colossal.Mathematics.Bounds1 yBounds) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector2Parameter>> expression, Colossal.Mathematics.Bounds1 xBounds, Colossal.Mathematics.Bounds1 yBounds);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector2Parameter>> expression) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector2Parameter>> expression);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector3Parameter>> expression, System.Single min, System.Single max) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector3Parameter>> expression, System.Single min, System.Single max);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector3Parameter>> expression, Colossal.Mathematics.Bounds1 bounds) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector3Parameter>> expression, Colossal.Mathematics.Bounds1 bounds);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector3Parameter>> expression, Colossal.Mathematics.Bounds1 xBounds, Colossal.Mathematics.Bounds1 yBounds, Colossal.Mathematics.Bounds1 zBounds) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector3Parameter>> expression, Colossal.Mathematics.Bounds1 xBounds, Colossal.Mathematics.Bounds1 yBounds, Colossal.Mathematics.Bounds1 zBounds);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector3Parameter>> expression) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector3Parameter>> expression);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2>>> expression) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2>>> expression);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2>>> expression, System.Single min = 0, System.Single max = 0) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2>>> expression, System.Single min, System.Single max);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2>>> expression, Colossal.Mathematics.Bounds1 bounds) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2>>> expression, Colossal.Mathematics.Bounds1 bounds);
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2>>> expression, Colossal.Mathematics.Bounds1 xBounds, Colossal.Mathematics.Bounds1 yBounds) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty[] BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2>>> expression, Colossal.Mathematics.Bounds1 xBounds, Colossal.Mathematics.Bounds1 yBounds);
```

- `public static BindPropertyW(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector4Parameter>> expression, System.Single min, System.Single max, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty BindPropertyW(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector4Parameter>> expression, System.Single min, System.Single max, System.Func<System.Boolean> isAvailable);
```

- `public static BooleanToFloat(System.Boolean value) : System.Single`  

```csharp
public static System.Single BooleanToFloat(System.Boolean value);
```

- `public static CreatePreset(System.String name, Game.Rendering.CinematicCamera.PhotoModeProperty injectionProperty, Game.Rendering.CinematicCamera.PhotoModeProperty[] targetProperties, System.String[] options, UnityEngine.Vector2[] values) : Game.UI.InGame.PhotoModeUIPreset`  

```csharp
public static Game.UI.InGame.PhotoModeUIPreset CreatePreset(System.String name, Game.Rendering.CinematicCamera.PhotoModeProperty injectionProperty, Game.Rendering.CinematicCamera.PhotoModeProperty[] targetProperties, System.String[] options, UnityEngine.Vector2[] values);
```

- `private static ExtractMember<T>(System.Linq.Expressions.Expression<System.Func<T>> expression, System.String& name) : T`  

```csharp
private static T ExtractMember<T>(System.Linq.Expressions.Expression<System.Func<T>> expression, System.String& name);
```

- `private static ExtractMember<T>(System.Linq.Expressions.Expression<System.Func<T>> expression, System.String& name, Game.GameSystemBase& systemBase) : T`  

```csharp
private static T ExtractMember<T>(System.Linq.Expressions.Expression<System.Func<T>> expression, System.String& name, Game.GameSystemBase& systemBase);
```

- `public static ExtractMultiPropertyComponents(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> allProperties) : System.Collections.Generic.IEnumerable<Game.Rendering.CinematicCamera.PhotoModeProperty>`  

```csharp
public static System.Collections.Generic.IEnumerable<Game.Rendering.CinematicCamera.PhotoModeProperty> ExtractMultiPropertyComponents(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> allProperties);
```

- `public static ExtractPropertyID(Game.Rendering.CinematicCamera.PhotoModeProperty property) : System.String`  

```csharp
public static System.String ExtractPropertyID(Game.Rendering.CinematicCamera.PhotoModeProperty property);
```

- `public static FindClosestEnumValue<T>(System.Single value) : T`  

```csharp
public static T FindClosestEnumValue<T>(System.Single value);
```

- `public static FloatToBoolean(System.Single value) : System.Boolean`  

```csharp
public static System.Boolean FloatToBoolean(System.Single value);
```

- `public static GroupTitle(System.String tab, System.String name) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static Game.Rendering.CinematicCamera.PhotoModeProperty GroupTitle(System.String tab, System.String name);
```


## Nested types

- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass10_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass12_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass13_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass14_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass15_0<T>`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass16_0<T>`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass18_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass21_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass24_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass25_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass28_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass29_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass30_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass33_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass3_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass4_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass5_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass6_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass7_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass8_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<>c__DisplayClass9_0`  
- `Game.Rendering.CinematicCamera.PhotoModeUtils+<ExtractMultiPropertyComponents>d__34`  

