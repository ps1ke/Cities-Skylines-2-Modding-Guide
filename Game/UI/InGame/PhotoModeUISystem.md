# Game.UI.InGame.PhotoModeUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class PhotoModeUISystem : Game.UI.UISystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Simulation.PlanetarySystem m_PlanetarySystem;
    private Game.Rendering.PhotoModeRenderSystem m_PhotoModeRenderSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.UI.InGame.CinematicCameraUISystem m_CinematicCameraUISystem;
    private Game.Tools.BulldozeToolSystem m_BulldozeTool;
    private Game.Input.InputBarrier m_ToolBarrier;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_OverlayHiddenBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_OrbitCameraActiveBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Single> m_FieldOfViewBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Single> m_TimeOfDayBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Single> m_SaturationBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AdjustmentCategoriesBinding;
    private System.Boolean m_TimeOfDayChanged;
    private System.Boolean <orbitMode>k__BackingField;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_CinematicCameraVisibleBinding;
    private Colossal.UI.Binding.ValueBinding<System.String> m_ActiveTabBinding;
    private Colossal.UI.Binding.RawValueBinding m_TabNamesBinding;
    private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
    private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> <tabs>k__BackingField;
    public static const System.String kGroup;

    public System.Boolean orbitMode { get; set; }
    private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> tabs { private get; private set; }

    public PhotoModeUISystem();

    private System.Boolean <OnCreate>b__22_0();
    public System.Void Activate(System.Boolean enabled);
    private System.Void AddCommonFields(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children, Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent);
    private System.Void BindTabNames(Colossal.UI.Binding.IJsonWriter writer);
    private Game.UI.Widgets.Group BuildCheckboxGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent);
    private Game.UI.Widgets.IWidget BuildColorGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> allProperties);
    private Game.UI.Widgets.IWidget BuildControl(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent);
    private Game.UI.Widgets.Group BuildDropdownGroup(System.String groupName, System.Collections.Generic.List<Game.UI.Widgets.DropdownItem<System.Int32>> items, Game.Reflection.DelegateAccessor<System.Int32> accessor);
    private Game.UI.Widgets.Group BuildEnumGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent);
    private Game.UI.Widgets.Group BuildGroupTitle(Game.Rendering.CinematicCamera.PhotoModeProperty property);
    private Game.UI.Widgets.Group BuildMultiPropertyGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> allProperties);
    private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> BuildProperties();
    private Game.UI.Widgets.Group BuildValueGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent);
    private static System.Collections.IEnumerator CaptureScreenshot();
    private static System.Boolean CheckMultiPropertyHandled(System.Collections.Generic.HashSet<System.String> handledGroupsCache, Game.Rendering.CinematicCamera.PhotoModeProperty property);
    private System.Void InjectPreset(Game.UI.InGame.PhotoModeUIPreset preset);
    private System.Void InjectPresets();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    private System.Void SelectTab(System.String tabID);
    private System.Void SetCinematicCameraVisible(System.Boolean visible);
    private System.Void SetOverlayHidden(System.Boolean overlayHidden);
    private System.Void TakeScreenshot();
    private System.Void ToggleOrbitCameraActive();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  

```csharp
private Game.Simulation.PlanetarySystem m_PlanetarySystem;
```

- `private Game.Rendering.PhotoModeRenderSystem m_PhotoModeRenderSystem`  

```csharp
private Game.Rendering.PhotoModeRenderSystem m_PhotoModeRenderSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.UI.InGame.CinematicCameraUISystem m_CinematicCameraUISystem`  

```csharp
private Game.UI.InGame.CinematicCameraUISystem m_CinematicCameraUISystem;
```

- `private Game.Tools.BulldozeToolSystem m_BulldozeTool`  

```csharp
private Game.Tools.BulldozeToolSystem m_BulldozeTool;
```

- `private Game.Input.InputBarrier m_ToolBarrier`  

```csharp
private Game.Input.InputBarrier m_ToolBarrier;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_OverlayHiddenBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_OverlayHiddenBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_OrbitCameraActiveBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_OrbitCameraActiveBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_FieldOfViewBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Single> m_FieldOfViewBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_TimeOfDayBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Single> m_TimeOfDayBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_SaturationBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Single> m_SaturationBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AdjustmentCategoriesBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AdjustmentCategoriesBinding;
```

- `private System.Boolean m_TimeOfDayChanged`  

```csharp
private System.Boolean m_TimeOfDayChanged;
```

- `private System.Boolean <orbitMode>k__BackingField`  

```csharp
private System.Boolean <orbitMode>k__BackingField;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_CinematicCameraVisibleBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_CinematicCameraVisibleBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.String> m_ActiveTabBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_ActiveTabBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_TabNamesBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TabNamesBinding;
```

- `private Game.UI.Widgets.WidgetBindings m_WidgetBindings`  

```csharp
private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
```

- `private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> <tabs>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> <tabs>k__BackingField;
```

- `public static const System.String kGroup`  

```csharp
public static const System.String kGroup;
```


## Properties

- `public System.Boolean orbitMode { get; set }`  

```csharp
public System.Boolean orbitMode { get; set; }
```

- `private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> tabs { private get; private set }`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> tabs { private get; private set; }
```


## Constructors

- `public PhotoModeUISystem()`  

```csharp
[Preserve]
	public PhotoModeUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__22_0() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__22_0();
```

- `public Activate(System.Boolean enabled) : System.Void`  

```csharp
public void Activate(bool enabled)
	{
		if (enabled)
		{
			orbitMode = m_CameraUpdateSystem.activeCameraController == m_CameraUpdateSystem.orbitCameraController;
			if (m_CameraUpdateSystem.activeCameraController == m_CameraUpdateSystem.gamePlayController)
			{
				m_CameraUpdateSystem.cinematicCameraController.TryMatchPosition(m_CameraUpdateSystem.activeCameraController);
				m_CameraUpdateSystem.activeCameraController = m_CameraUpdateSystem.cinematicCameraController;
			}
			m_CameraUpdateSystem.orbitCameraController.mode = OrbitCameraController.Mode.PhotoMode;
			m_CameraUpdateSystem.orbitCameraController.collisionsEnabled = false;
			m_CameraUpdateSystem.cinematicCameraController.collisionsEnabled = false;
		}
		else
		{
			if (m_CameraUpdateSystem.activeCameraController != m_CameraUpdateSystem.orbitCameraController || m_CameraUpdateSystem.orbitCameraController.followedEntity == Entity.Null)
			{
				m_CameraUpdateSystem.gamePlayController.TryMatchPosition(m_CameraUpdateSystem.activeCameraController);
				m_CameraUpdateSystem.activeCameraController = m_CameraUpdateSystem.gamePlayController;
			}
			m_CameraUpdateSystem.orbitCameraController.mode = OrbitCameraController.Mode.Follow;
			m_CameraUpdateSystem.orbitCameraController.collisionsEnabled = true;
			m_PhotoModeRenderSystem.DisableAllCameraProperties();
		}
		m_ToolBarrier.blocked = enabled;
		m_PhotoModeRenderSystem.Enable(enabled);
	}
```

- `private AddCommonFields(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children, Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent) : System.Void`  

```csharp
private void AddCommonFields(IList<IWidget> children, PhotoModeProperty property, bool multiPropertyComponent)
	{
		if (multiPropertyComponent)
		{
			return;
		}
		if (property.isEnabled != null && property.setEnabled != null)
		{
			children.Add(new ToggleField
			{
				displayName = property.id + "EnableToggle",
				tooltip = "PhotoMode.ENABLE_PROPERTY_TOOLTIP",
				accessor = new DelegateAccessor<bool>(property.isEnabled, property.setEnabled),
				disabled = () => property.isAvailable != null && !property.isAvailable(),
				tutorialTag = "UITagPrefab:PhotoModePropertyEnableCheckbox"
			});
		}
		children.Add(new IconButton
		{
			icon = "Media/PhotoMode/AddKeyframe.svg",
			tooltip = "PhotoMode.CAPTURE_PROPERTY_TOOLTIP",
			disabled = () => !m_CinematicCameraVisibleBinding.value || (property.isEnabled != null && !property.isEnabled()),
			action = delegate
			{
				m_CinematicCameraUISystem.ToggleModifier(property);
			},
			tutorialTag = "UITagPrefab:PhotoModePropertyKeyframeButton"
		});
	}
```

- `private BindTabNames(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private void BindTabNames(IJsonWriter writer)
	{
		writer.ArrayBegin(tabs.Count);
		foreach (Tab tab in tabs)
		{
			tab.Write(writer);
		}
		writer.ArrayEnd();
	}
```

- `private BuildCheckboxGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent = False) : Game.UI.Widgets.Group`  

```csharp
private Group BuildCheckboxGroup(PhotoModeProperty property, bool multiPropertyComponent = false)
	{
		bool flag = property.setEnabled != null && property.isEnabled != null;
		List<IWidget> list = new List<IWidget>();
		AddCommonFields(list, property, multiPropertyComponent);
		list.Add(new ToggleField
		{
			displayName = property.id,
			accessor = new DelegateAccessor<bool>(() => Mathf.RoundToInt(property.getValue()) != 0, delegate(bool value)
			{
				property.setValue(value ? 1f : 0f);
			}),
			disabled = (flag ? ((Func<bool>)(() => !property.isEnabled())) : ((Func<bool>)(() => false)))
		});
		if (!multiPropertyComponent && property.reset != null)
		{
			list.Add(new IconButton
			{
				icon = "Media/Glyphs/ArrowCircular.svg",
				tooltip = LocalizedString.Id("PhotoMode.RESET_PROPERTY_TOOLTIP"),
				action = property.reset
			});
		}
		return new Group
		{
			displayName = LocalizedString.IdWithFallback("PhotoMode.PROPERTY_TITLE[" + property.id + "]", property.id),
			tooltip = ((!multiPropertyComponent) ? LocalizedString.IdWithFallback("PhotoMode.PROPERTY_TOOLTIP[" + property.id + "]", property.id) : ((LocalizedString)null)),
			tooltipPos = Group.TooltipPosition.Title,
			children = list
		};
	}
```

- `private BuildColorGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> allProperties) : Game.UI.Widgets.IWidget`  

```csharp
private IWidget BuildColorGroup(PhotoModeProperty property, IDictionary<string, PhotoModeProperty> allProperties)
	{
		PhotoModeProperty[] source = PhotoModeUtils.ExtractMultiPropertyComponents(property, allProperties).ToArray();
		PhotoModeProperty r = source.FirstOrDefault((PhotoModeProperty c) => c.id.EndsWith("/r"));
		PhotoModeProperty g = source.FirstOrDefault((PhotoModeProperty c) => c.id.EndsWith("/g"));
		PhotoModeProperty b = source.FirstOrDefault((PhotoModeProperty c) => c.id.EndsWith("/b"));
		PhotoModeProperty a = source.FirstOrDefault((PhotoModeProperty c) => c.id.EndsWith("/a"));
		Func<Color> getter = () => new Color(r?.getValue() ?? 0f, g?.getValue() ?? 0f, b?.getValue() ?? 0f, a?.getValue() ?? 1f);
		Action<Color> setter = delegate(Color c)
		{
			r?.setValue(c.r);
			g?.setValue(c.g);
			b?.setValue(c.b);
			a?.setValue(c.a);
		};
		return new ColorField
		{
			accessor = new DelegateAccessor<Color>(getter, setter),
			disabled = () => property.isEnabled != null && !property.isEnabled(),
			showAlpha = (a != null),
			hdr = (property.max == null)
		};
	}
```

- `private BuildControl(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent = False) : Game.UI.Widgets.IWidget`  

```csharp
private IWidget BuildControl(PhotoModeProperty property, bool multiPropertyComponent = false)
	{
		if (!multiPropertyComponent && property.id.IndexOf("/") >= 0)
		{
			return BuildMultiPropertyGroup(property, m_PhotoModeRenderSystem.photoModeProperties);
		}
		if (property.setValue == null && property.getValue == null)
		{
			return BuildGroupTitle(property);
		}
		if (property.overrideControl == PhotoModeProperty.OverrideControl.Checkbox)
		{
			return BuildCheckboxGroup(property, multiPropertyComponent);
		}
		if (property.enumType != null)
		{
			return BuildEnumGroup(property, multiPropertyComponent);
		}
		return BuildValueGroup(property, multiPropertyComponent);
	}
```

- `private BuildDropdownGroup(System.String groupName, System.Collections.Generic.List<Game.UI.Widgets.DropdownItem<System.Int32>> items, Game.Reflection.DelegateAccessor<System.Int32> accessor) : Game.UI.Widgets.Group`  

```csharp
private Group BuildDropdownGroup(string groupName, List<DropdownItem<int>> items, DelegateAccessor<int> accessor)
	{
		Group obj = new Group();
		obj.displayName = LocalizedString.IdWithFallback("PhotoMode.PROPERTY_TITLE[" + groupName + "]", groupName);
		obj.tooltip = LocalizedString.IdWithFallback("PhotoMode.PROPERTY_TOOLTIP[" + groupName + "]", string.Empty);
		obj.children = new IWidget[1]
		{
			new DropdownField<int>
			{
				displayName = groupName + "Dropdown",
				accessor = accessor,
				items = items.ToArray()
			}
		};
		return obj;
	}
```

- `private BuildEnumGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent = False) : Game.UI.Widgets.Group`  

```csharp
private Group BuildEnumGroup(PhotoModeProperty property, bool multiPropertyComponent = false)
	{
		bool flag = property.isEnabled != null && property.setEnabled != null;
		List<IWidget> list = new List<IWidget>();
		AddCommonFields(list, property, multiPropertyComponent);
		list.Add(new EnumField
		{
			displayName = property.id + "Dropdown",
			disabled = (flag ? ((Func<bool>)(() => !property.isEnabled())) : ((Func<bool>)(() => false))),
			enumMembers = AutomaticSettings.GetEnumValues(property.enumType, "PhotoMode"),
			accessor = new DelegateAccessor<ulong>(() => (ulong)Mathf.RoundToInt(property.getValue()), delegate(ulong value)
			{
				property.setValue(value);
			})
		});
		if (!multiPropertyComponent && property.reset != null)
		{
			list.Add(new IconButton
			{
				icon = "Media/Glyphs/ArrowCircular.svg",
				tooltip = LocalizedString.Id("PhotoMode.RESET_PROPERTY_TOOLTIP"),
				action = property.reset
			});
		}
		return new Group
		{
			displayName = LocalizedString.IdWithFallback("PhotoMode.PROPERTY_TITLE[" + property.id + "]", property.id),
			tooltip = ((!multiPropertyComponent) ? LocalizedString.IdWithFallback("PhotoMode.PROPERTY_TOOLTIP[" + property.id + "]", string.Empty) : ((LocalizedString)null)),
			tooltipPos = Group.TooltipPosition.Title,
			children = list
		};
	}
```

- `private BuildGroupTitle(Game.Rendering.CinematicCamera.PhotoModeProperty property) : Game.UI.Widgets.Group`  

```csharp
private Group BuildGroupTitle(PhotoModeProperty property)
	{
		return new Group
		{
			displayName = LocalizedString.IdWithFallback("PhotoMode.PROPERTY_TITLE[" + property.id + "]", property.id),
			tooltip = LocalizedString.IdWithFallback("PhotoMode.PROPERTY_TOOLTIP[" + property.id + "]", string.Empty),
			tooltipPos = Group.TooltipPosition.Title
		};
	}
```

- `private BuildMultiPropertyGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> allProperties) : Game.UI.Widgets.Group`  

```csharp
private Group BuildMultiPropertyGroup(PhotoModeProperty property, IDictionary<string, PhotoModeProperty> allProperties)
	{
		string text = property.id.Substring(0, property.id.IndexOf("/"));
		List<IWidget> list = new List<IWidget>();
		AddCommonFields(list, property, multiPropertyComponent: false);
		if (property.overrideControl == PhotoModeProperty.OverrideControl.ColorField)
		{
			list.Add(BuildColorGroup(property, allProperties));
			if (property.reset != null)
			{
				list.Add(new IconButton
				{
					icon = "Media/Glyphs/ArrowCircular.svg",
					tooltip = LocalizedString.Id("PhotoMode.RESET_PROPERTY_TOOLTIP"),
					action = property.reset
				});
			}
		}
		else
		{
			if (property.reset != null)
			{
				list.Add(new IconButton
				{
					icon = "Media/Glyphs/ArrowCircular.svg",
					tooltip = LocalizedString.Id("PhotoMode.RESET_PROPERTY_TOOLTIP"),
					action = property.reset
				});
			}
			foreach (PhotoModeProperty item in PhotoModeUtils.ExtractMultiPropertyComponents(property, allProperties))
			{
				list.Add(BuildControl(item, multiPropertyComponent: true));
			}
		}
		return new Group
		{
			displayName = LocalizedString.IdWithFallback("PhotoMode.PROPERTY_TITLE[" + text + "]", text),
			tooltip = LocalizedString.IdWithFallback("PhotoMode.PROPERTY_TOOLTIP[" + text + "]", string.Empty),
			tooltipPos = Group.TooltipPosition.Title,
			children = list
		};
	}
```

- `private BuildProperties() : System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab>`  

```csharp
private List<Tab> BuildProperties()
	{
		HashSet<string> handledGroupsCache = new HashSet<string>();
		OrderedDictionary<string, Tab> orderedDictionary = new OrderedDictionary<string, Tab>();
		foreach (KeyValuePair<string, PhotoModeProperty> photoModeProperty in m_PhotoModeRenderSystem.photoModeProperties)
		{
			if (!orderedDictionary.TryGetValue(photoModeProperty.Value.group, out var value))
			{
				value = new Tab
				{
					id = photoModeProperty.Value.group,
					icon = "Media/PhotoMode/" + photoModeProperty.Value.group + ".svg",
					items = new List<IWidget>()
				};
				orderedDictionary.Add(photoModeProperty.Value.group, value);
			}
			if (CheckMultiPropertyHandled(handledGroupsCache, photoModeProperty.Value))
			{
				value.items.Add(BuildControl(photoModeProperty.Value));
			}
		}
		return orderedDictionary.Values.ToList();
	}
```

- `private BuildValueGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent = False) : Game.UI.Widgets.Group`  

```csharp
private Group BuildValueGroup(PhotoModeProperty property, bool multiPropertyComponent = false)
	{
		bool flag = property.setEnabled != null && property.isEnabled != null;
		List<IWidget> list = new List<IWidget>();
		if (property.fractionDigits > 0)
		{
			list.Add(new FloatInputField
			{
				displayName = property.id + " Value",
				dynamicMin = ((property.min != null) ? ((Func<double>)(() => property.min())) : null),
				dynamicMax = ((property.max != null) ? ((Func<double>)(() => property.max())) : null),
				fractionDigits = property.fractionDigits,
				disabled = (flag ? ((Func<bool>)(() => !property.isEnabled())) : ((Func<bool>)(() => false))),
				accessor = new DelegateAccessor<double>(() => property.getValue(), delegate(double value)
				{
					property.setValue((float)value);
				})
			});
		}
		else
		{
			list.Add(new IntInputField
			{
				displayName = property.id + " Value",
				dynamicMin = ((property.min != null) ? ((Func<int>)(() => Mathf.RoundToInt(property.min()))) : null),
				dynamicMax = ((property.max != null) ? ((Func<int>)(() => Mathf.RoundToInt(property.max()))) : null),
				disabled = (flag ? ((Func<bool>)(() => !property.isEnabled())) : ((Func<bool>)(() => false))),
				accessor = new DelegateAccessor<int>(() => Mathf.RoundToInt(property.getValue()), delegate(int value)
				{
					property.setValue(value);
				})
			});
		}
		AddCommonFields(list, property, multiPropertyComponent);
		if (property.fractionDigits > 0)
		{
			list.Add(new FloatSliderField
			{
				displayName = LocalizedString.IdWithFallback("PhotoMode.PROPERTY_TITLE[" + property.id + "]", property.id),
				tooltip = LocalizedString.IdWithFallback("PhotoMode.PROPERTY_TOOLTIP[" + property.id + "]", string.Empty),
				dynamicMin = ((property.min != null) ? ((Func<double>)(() => property.min())) : ((Func<double>)(() => double.NegativeInfinity))),
				dynamicMax = ((property.max != null) ? ((Func<double>)(() => property.max())) : ((Func<double>)(() => double.PositiveInfinity))),
				disabled = (flag ? ((Func<bool>)(() => !property.isEnabled())) : ((Func<bool>)(() => false))),
				accessor = new DelegateAccessor<double>(() => property.getValue(), delegate(double value)
				{
					property.setValue((float)value);
				}),
				fractionDigits = property.fractionDigits
			});
		}
		else
		{
			list.Add(new IntSliderField
			{
				displayName = LocalizedString.IdWithFallback("PhotoMode.PROPERTY_TITLE[" + property.id + "]", property.id),
				tooltip = LocalizedString.IdWithFallback("PhotoMode.PROPERTY_TOOLTIP[" + property.id + "]", string.Empty),
				dynamicMin = ((property.min != null) ? ((Func<int>)(() => Mathf.RoundToInt(property.min()))) : ((Func<int>)(() => Mathf.RoundToInt(float.NegativeInfinity)))),
				dynamicMax = ((property.max != null) ? ((Func<int>)(() => Mathf.RoundToInt(property.max()))) : ((Func<int>)(() => Mathf.RoundToInt(float.PositiveInfinity)))),
				disabled = (flag ? ((Func<bool>)(() => !property.isEnabled())) : ((Func<bool>)(() => false))),
				accessor = new DelegateAccessor<int>(() => Mathf.RoundToInt(property.getValue()), delegate(int value)
				{
					property.setValue(value);
				})
			});
		}
		if (!multiPropertyComponent && property.reset != null)
		{
			list.Add(new IconButton
			{
				icon = "Media/Glyphs/ArrowCircular.svg",
				tooltip = LocalizedString.Id("PhotoMode.RESET_PROPERTY_TOOLTIP"),
				action = property.reset
			});
		}
		return new Group
		{
			displayName = LocalizedString.IdWithFallback("PhotoMode.PROPERTY_TITLE[" + property.id + "]", property.id),
			tooltip = ((!multiPropertyComponent) ? LocalizedString.IdWithFallback("PhotoMode.PROPERTY_TOOLTIP[" + property.id + "]", string.Empty) : ((LocalizedString)null)),
			tooltipPos = Group.TooltipPosition.Title,
			children = list
		};
	}
```

- `private static CaptureScreenshot() : System.Collections.IEnumerator`  

```csharp
private static IEnumerator CaptureScreenshot()
	{
		UserInterface ui = GameManager.instance.userInterface;
		if (ui != null)
		{
			ui.view.enabled = false;
		}
		yield return new WaitForEndOfFrame();
		PlatformManager.instance.TakeScreenshot();
		if (ui != null)
		{
			ui.view.enabled = true;
		}
	}
```

- `private static CheckMultiPropertyHandled(System.Collections.Generic.HashSet<System.String> handledGroupsCache, Game.Rendering.CinematicCamera.PhotoModeProperty property) : System.Boolean`  

```csharp
private static bool CheckMultiPropertyHandled(HashSet<string> handledGroupsCache, PhotoModeProperty property)
	{
		int num = property.id.IndexOf("/");
		if (num >= 0)
		{
			string item = property.id.Substring(0, num);
			if (handledGroupsCache.Contains(item))
			{
				return false;
			}
			handledGroupsCache.Add(item);
			return true;
		}
		return true;
	}
```

- `private InjectPreset(Game.UI.InGame.PhotoModeUIPreset preset) : System.Void`  

```csharp
private void InjectPreset(PhotoModeUIPreset preset)
	{
		Tab tab = tabs.Find((Tab tab2) => tab2.id == preset.injectionProperty.group);
		if (tab == null)
		{
			return;
		}
		DelegateAccessor<int> accessor = new DelegateAccessor<int>(delegate
		{
			int num2 = -1;
			bool flag = false;
			foreach (KeyValuePair<PhotoModeProperty, float[]> value in preset.descriptor.values)
			{
				if (flag && num2 == -1)
				{
					return num2;
				}
				num2 = -1;
				flag = true;
				for (int i = 0; i < value.Value.Length; i++)
				{
					if (value.Key.getValue() == value.Value[i])
					{
						if (num2 != -1 && num2 != i)
						{
							return -1;
						}
						num2 = i;
					}
				}
			}
			return num2;
		}, delegate(int value)
		{
			foreach (KeyValuePair<PhotoModeProperty, float[]> value2 in preset.descriptor.values)
			{
				if (value >= 0)
				{
					value2.Key.setValue(value2.Value[value]);
				}
			}
		});
		List<DropdownItem<int>> list = new List<DropdownItem<int>>();
		list.Add(new DropdownItem<int>
		{
			value = -1,
			displayName = "PhotoMode.SENSORTYPE[Custom]"
		});
		int num = 0;
		foreach (string item in preset.descriptor.optionsId)
		{
			list.Add(new DropdownItem<int>
			{
				value = num++,
				displayName = item
			});
		}
		int index = tab.items.FindIndex((IWidget x) => (x as NamedWidget)?.displayName.value == PhotoModeUtils.ExtractPropertyID(preset.injectionProperty));
		tab.items.Insert(index, BuildDropdownGroup(preset.id, list, accessor));
	}
```

- `private InjectPresets() : System.Void`  

```csharp
private void InjectPresets()
	{
		foreach (PhotoModeUIPreset preset in m_PhotoModeRenderSystem.presets)
		{
			InjectPreset(preset);
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_DefaultToolSystem = base.World.GetOrCreateSystemManaged<DefaultToolSystem>();
		m_PlanetarySystem = base.World.GetOrCreateSystemManaged<PlanetarySystem>();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_ToolRaycastSystem = base.World.GetOrCreateSystemManaged<ToolRaycastSystem>();
		m_PhotoModeRenderSystem = base.World.GetOrCreateSystemManaged<PhotoModeRenderSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_CinematicCameraUISystem = base.World.GetOrCreateSystemManaged<CinematicCameraUISystem>();
		m_BulldozeTool = base.World.GetOrCreateSystemManaged<BulldozeToolSystem>();
		m_ToolBarrier = InputManager.instance.CreateMapBarrier("Tool", "PhotoModeUISystem");
		tabs = BuildProperties();
		InjectPresets();
		AddUpdateBinding(m_WidgetBindings = new WidgetBindings("photoMode"));
		m_WidgetBindings.AddDefaultBindings();
		AddBinding(new TriggerBinding<string>("photoMode", "selectTab", SelectTab));
		AddBinding(new TriggerBinding<bool>("photoMode", "setCinematicCameraVisible", SetCinematicCameraVisible));
		AddBinding(m_CinematicCameraVisibleBinding = new ValueBinding<bool>("photoMode", "cinematicCameraVisible", initialValue: false));
		AddBinding(m_ActiveTabBinding = new ValueBinding<string>("photoMode", "activeTab", string.Empty));
		AddBinding(m_TabNamesBinding = new RawValueBinding("photoMode", "tabs", BindTabNames));
		SelectTab("Camera");
		AddBinding(m_OverlayHiddenBinding = new ValueBinding<bool>("photoMode", "overlayHidden", initialValue: false));
		AddBinding(m_OrbitCameraActiveBinding = new GetterValueBinding<bool>("photoMode", "orbitCameraActive", () => m_CameraUpdateSystem.activeCameraController is OrbitCameraController));
		AddBinding(new TriggerBinding<bool>("photoMode", "setOverlayHidden", SetOverlayHidden));
		AddBinding(new TriggerBinding("photoMode", "takeScreenshot", TakeScreenshot));
		AddBinding(new TriggerBinding("photoMode", "toggleOrbitCameraActive", ToggleOrbitCameraActive));
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
		if (m_OverlayHiddenBinding.value)
		{
			if (m_ToolSystem.activeTool != m_BulldozeTool)
			{
				m_RenderingSystem.hideOverlay = true;
				m_ToolRaycastSystem.raycastFlags |= RaycastFlags.FreeCameraDisable;
				m_ToolSystem.activeTool = m_DefaultToolSystem;
			}
			else
			{
				m_ToolRaycastSystem.raycastFlags &= ~RaycastFlags.FreeCameraDisable;
				m_OverlayHiddenBinding.Update(newValue: false);
			}
		}
		if (m_TimeOfDayChanged)
		{
			m_TimeOfDayChanged = false;
			m_PlanetarySystem.Update();
		}
	}
```

- `private SelectTab(System.String tabID) : System.Void`  

```csharp
private void SelectTab(string tabID)
	{
		Tab tab = tabs.Find((Tab tab2) => tab2.id == tabID);
		if (tab != null)
		{
			m_ActiveTabBinding.Update(tab.id);
			m_WidgetBindings.children = tab.items;
		}
	}
```

- `private SetCinematicCameraVisible(System.Boolean visible) : System.Void`  

```csharp
private void SetCinematicCameraVisible(bool visible)
	{
		m_CinematicCameraVisibleBinding.Update(visible);
	}
```

- `private SetOverlayHidden(System.Boolean overlayHidden) : System.Void`  

```csharp
private void SetOverlayHidden(bool overlayHidden)
	{
		m_RenderingSystem.hideOverlay = overlayHidden;
		if (overlayHidden)
		{
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.FreeCameraDisable;
			m_ToolSystem.activeTool = m_DefaultToolSystem;
		}
		else
		{
			m_ToolRaycastSystem.raycastFlags &= ~RaycastFlags.FreeCameraDisable;
		}
		m_OverlayHiddenBinding.Update(overlayHidden);
	}
```

- `private TakeScreenshot() : System.Void`  

```csharp
private void TakeScreenshot()
	{
		PlatformManager.instance.UnlockAchievement(Game.Achievements.Achievements.Snapshot);
		GameManager.instance.StartCoroutine(CaptureScreenshot());
	}
```

- `private ToggleOrbitCameraActive() : System.Void`  

```csharp
private void ToggleOrbitCameraActive()
	{
		if (m_CameraUpdateSystem.activeCameraController is OrbitCameraController)
		{
			orbitMode = false;
			m_CameraUpdateSystem.cinematicCameraController.TryMatchPosition(m_CameraUpdateSystem.activeCameraController);
			m_CameraUpdateSystem.activeCameraController = m_CameraUpdateSystem.cinematicCameraController;
		}
		else
		{
			orbitMode = true;
			m_CameraUpdateSystem.orbitCameraController.followedEntity = Entity.Null;
			m_CameraUpdateSystem.orbitCameraController.TryMatchPosition(m_CameraUpdateSystem.activeCameraController);
			m_CameraUpdateSystem.activeCameraController = m_CameraUpdateSystem.orbitCameraController;
		}
		m_OrbitCameraActiveBinding.Update();
	}
```


## Nested types

- `Game.UI.InGame.PhotoModeUISystem+Tab`  
- `Game.UI.InGame.PhotoModeUISystem+<>c`  
- `Game.UI.InGame.PhotoModeUISystem+<>c__DisplayClass37_0`  
- `Game.UI.InGame.PhotoModeUISystem+<>c__DisplayClass40_0`  
- `Game.UI.InGame.PhotoModeUISystem+<>c__DisplayClass44_0`  
- `Game.UI.InGame.PhotoModeUISystem+<>c__DisplayClass45_0`  
- `Game.UI.InGame.PhotoModeUISystem+<>c__DisplayClass46_0`  
- `Game.UI.InGame.PhotoModeUISystem+<>c__DisplayClass47_0`  
- `Game.UI.InGame.PhotoModeUISystem+<>c__DisplayClass48_0`  
- `Game.UI.InGame.PhotoModeUISystem+<CaptureScreenshot>d__53`  

