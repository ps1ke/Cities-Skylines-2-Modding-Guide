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
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.FloatParameter>> expression, System.Single min, System.Single max, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.MinFloatParameter>> expression, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector4Parameter>> expression, System.Func<UnityEngine.Vector4, System.Single> getter, System.Func<UnityEngine.Vector4, System.Single, UnityEngine.Vector4> setter, System.Single min, System.Single max, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.OverridableProperty<System.Single>>> expression, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.ClampedFloatParameter>> expression, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.ClampedIntParameter>> expression, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single>>> expression, System.Single min, System.Single max, System.Func<System.Single, System.Single> from = null, System.Func<System.Single, System.Single> to = null, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<System.Single>>> expression, System.Func<System.Single> min, System.Func<System.Single> max, System.Func<System.Single, System.Single> from = null, System.Func<System.Single, System.Single> to = null, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<System.Int32>>> expression, System.Int32 min, System.Int32 max, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<System.Int32>>> expression, System.Int32 min, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
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
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.ColorParameter>> expression) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector2Parameter>> expression, System.Single min, System.Single max) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector2Parameter>> expression, Colossal.Mathematics.Bounds1 bounds) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector2Parameter>> expression, Colossal.Mathematics.Bounds1 xBounds, Colossal.Mathematics.Bounds1 yBounds) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector2Parameter>> expression) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector3Parameter>> expression, System.Single min, System.Single max) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector3Parameter>> expression, Colossal.Mathematics.Bounds1 bounds) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector3Parameter>> expression, Colossal.Mathematics.Bounds1 xBounds, Colossal.Mathematics.Bounds1 yBounds, Colossal.Mathematics.Bounds1 zBounds) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector3Parameter>> expression) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2>>> expression) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2>>> expression, System.Single min = 0, System.Single max = 0) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2>>> expression, Colossal.Mathematics.Bounds1 bounds) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindProperty(System.String tab, System.Linq.Expressions.Expression<System.Func<Game.Rendering.CinematicCamera.OverridableLensProperty<UnityEngine.Vector2>>> expression, Colossal.Mathematics.Bounds1 xBounds, Colossal.Mathematics.Bounds1 yBounds) : Game.Rendering.CinematicCamera.PhotoModeProperty[]`  

```csharp
public static PhotoModeProperty[] BindProperty(string tab, Expression<Func<OverridableLensProperty<Vector2>>> expression, Bounds1 xBounds, Bounds1 yBounds)
	{
		string name;
		OverridableLensProperty<Vector2> parameter = ExtractMember(expression, out name);
		return new PhotoModeProperty[2]
		{
			new PhotoModeProperty
			{
				id = name + "/x",
				group = tab,
				setValue = delegate(float x)
				{
					Vector2 value = parameter.value;
					value.x = x;
					parameter.Override(value);
				},
				getValue = () => parameter.value.x,
				min = () => xBounds.min,
				max = () => xBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			},
			new PhotoModeProperty
			{
				id = name + "/y",
				group = tab,
				setValue = delegate(float y)
				{
					Vector2 value = parameter.value;
					value.y = y;
					parameter.Override(value);
				},
				getValue = () => parameter.value.y,
				min = () => yBounds.min,
				max = () => yBounds.max,
				isEnabled = () => parameter.overrideState,
				setEnabled = delegate(bool enabled)
				{
					parameter.overrideState = enabled;
				},
				reset = delegate
				{
					parameter.Sync();
				}
			}
		};
	}
```

- `public static BindPropertyW(System.String tab, System.Linq.Expressions.Expression<System.Func<UnityEngine.Rendering.Vector4Parameter>> expression, System.Single min, System.Single max, System.Func<System.Boolean> isAvailable = null) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static PhotoModeProperty BindPropertyW(string tab, Expression<Func<Vector4Parameter>> expression, float min, float max, Func<bool> isAvailable = null)
	{
		return BindProperty(tab, expression, (Vector4 v) => v.w, (Vector4 i, float o) => new Vector4(i.x, i.y, i.z, o), min, max, isAvailable);
	}
```

- `public static BooleanToFloat(System.Boolean value) : System.Single`  

```csharp
public static float BooleanToFloat(bool value)
	{
		if (!value)
		{
			return 0f;
		}
		return 1f;
	}
```

- `public static CreatePreset(System.String name, Game.Rendering.CinematicCamera.PhotoModeProperty injectionProperty, Game.Rendering.CinematicCamera.PhotoModeProperty[] targetProperties, System.String[] options, UnityEngine.Vector2[] values) : Game.UI.InGame.PhotoModeUIPreset`  

```csharp
public static PhotoModeUIPreset CreatePreset(string name, PhotoModeProperty injectionProperty, PhotoModeProperty[] targetProperties, string[] options, Vector2[] values)
	{
		if (targetProperties.Length != 2)
		{
			throw new ArgumentException("targetProperties must be of length 2 with Vector2 values");
		}
		PresetDescriptor presetDescriptor = new PresetDescriptor();
		presetDescriptor.AddOptions(options);
		foreach (PhotoModeProperty photoModeProperty in targetProperties)
		{
			if (photoModeProperty.id.EndsWith("x"))
			{
				presetDescriptor.AddValues(photoModeProperty, values.Select((Vector2 v) => v.x).ToArray());
			}
			else if (photoModeProperty.id.EndsWith("y"))
			{
				presetDescriptor.AddValues(photoModeProperty, values.Select((Vector2 v) => v.y).ToArray());
			}
		}
		if (!presetDescriptor.Validate())
		{
			throw new ArgumentException("Preset descriptor is invalid");
		}
		return new PhotoModeUIPreset
		{
			id = name,
			injectionProperty = injectionProperty,
			descriptor = presetDescriptor
		};
	}
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
public static IEnumerable<PhotoModeProperty> ExtractMultiPropertyComponents(PhotoModeProperty property, IDictionary<string, PhotoModeProperty> allProperties)
	{
		int num = property.id.IndexOf("/");
		if (num < 0)
		{
			yield return property;
			yield break;
		}
		string name = property.id.Substring(0, num + 1);
		foreach (KeyValuePair<string, PhotoModeProperty> allProperty in allProperties)
		{
			if (allProperty.Key.StartsWith(name))
			{
				yield return allProperty.Value;
			}
		}
	}
```

- `public static ExtractPropertyID(Game.Rendering.CinematicCamera.PhotoModeProperty property) : System.String`  

```csharp
public static string ExtractPropertyID(PhotoModeProperty property)
	{
		int num = property.id.IndexOf("/");
		if (num < 0)
		{
			return property.id;
		}
		return property.id.Substring(0, num);
	}
```

- `public static FindClosestEnumValue<T>(System.Single value) : T`  

```csharp
public static T FindClosestEnumValue<T>(System.Single value);
```

- `public static FloatToBoolean(System.Single value) : System.Boolean`  

```csharp
public static bool FloatToBoolean(float value)
	{
		return Mathf.RoundToInt(value) != 0;
	}
```

- `public static GroupTitle(System.String tab, System.String name) : Game.Rendering.CinematicCamera.PhotoModeProperty`  

```csharp
public static PhotoModeProperty GroupTitle(string tab, string name)
	{
		return new PhotoModeProperty
		{
			id = name,
			group = tab
		};
	}
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

