# Game.UI.Widgets.EditorGenerator

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IEditorGenerator`  

## Code

```csharp
public class EditorGenerator : Game.UI.Widgets.IEditorGenerator
{
    private System.Int32 <maxLevel>k__BackingField;
    public static readonly System.Collections.Generic.List<Game.UI.Widgets.IFieldBuilderFactory> kFactories;
    private static readonly Colossal.OdinSerializer.CustomSerializationPolicy kMemberFilter;
    private static System.Boolean <sBypassValueLimits>k__BackingField;

    public System.Int32 maxLevel { get; set; }
    public static System.Boolean sBypassValueLimits { get; set; }

    public EditorGenerator();

    public Game.UI.Widgets.IWidget Build(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.Int32 level, System.String path);
    private Game.UI.Widgets.IWidget BuildMember(Game.Reflection.IValueAccessor parent, System.Reflection.MemberInfo member, System.Int32 level, System.String parentPath);
    private Game.UI.Widgets.IWidget BuildMemberImpl(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.Int32 level, System.String path);
    public System.Collections.Generic.IEnumerable<Game.UI.Widgets.IWidget> BuildMembers(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String parentPath);
    private Game.UI.Widgets.ValueField BuildUnknownMember(System.Type memberType);
    private static System.String GetMemberTooltipLocaleId(System.Reflection.MemberInfo member);
    private System.Reflection.MemberInfo[] GetSpecialMembers(System.Type type);
    public static T NamedWidget<T>(T widget, Game.UI.Localization.LocalizedString displayName, Game.UI.Localization.LocalizedString tooltip);
    private Game.UI.Widgets.IWidget TryBuildField(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.String path);
    private Game.UI.Widgets.ExpandableGroup TryBuildGroup(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String path);
    public Game.UI.Widgets.PagedList TryBuildList(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String path, System.Object[] attributes);
    public Game.UI.Widgets.IListAdapter TryBuildListAdapter(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String path, System.Object[] attributes);
    private Game.UI.Widgets.FieldBuilder TryCreateFieldBuilder(System.Type memberType, System.Object[] attributes);
}
```


## Fields

- `private System.Int32 <maxLevel>k__BackingField`  

```csharp
private System.Int32 <maxLevel>k__BackingField;
```

- `public static readonly System.Collections.Generic.List<Game.UI.Widgets.IFieldBuilderFactory> kFactories`  

```csharp
public static readonly System.Collections.Generic.List<Game.UI.Widgets.IFieldBuilderFactory> kFactories;
```

- `private static readonly Colossal.OdinSerializer.CustomSerializationPolicy kMemberFilter`  

```csharp
private static readonly Colossal.OdinSerializer.CustomSerializationPolicy kMemberFilter;
```

- `private static System.Boolean <sBypassValueLimits>k__BackingField`  

```csharp
private static System.Boolean <sBypassValueLimits>k__BackingField;
```


## Properties

- `public System.Int32 maxLevel { get; set }`  

```csharp
public System.Int32 maxLevel { get; set; }
```

- `public static System.Boolean sBypassValueLimits { get; set }`  

```csharp
public static System.Boolean sBypassValueLimits { get; set; }
```


## Constructors

- `public EditorGenerator()`  

```csharp
public EditorGenerator();
```


## Methods

- `public Build(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.Int32 level, System.String path) : Game.UI.Widgets.IWidget`  

```csharp
public IWidget Build(IValueAccessor accessor, object[] attributes, int level, string path)
	{
		if (level > maxLevel)
		{
			return new ValueField
			{
				accessor = new ObjectAccessor<string>(string.Empty)
			};
		}
		return BuildMemberImpl(accessor, attributes, level, path);
	}
```

- `private BuildMember(Game.Reflection.IValueAccessor parent, System.Reflection.MemberInfo member, System.Int32 level, System.String parentPath) : Game.UI.Widgets.IWidget`  

```csharp
[NotNull]
	private IWidget BuildMember(IValueAccessor parent, MemberInfo member, int level, string parentPath)
	{
		IValueAccessor accessor = ValueAccessorUtils.CreateMemberAccessor(parent, member);
		IWidget widget = BuildMemberImpl(accessor, member.GetCustomAttributes(inherit: false), level, parentPath + "." + member.Name);
		if (widget is INamed named)
		{
			InspectorNameAttribute attribute = member.GetAttribute<InspectorNameAttribute>();
			EditorNameAttribute attribute2 = member.GetAttribute<EditorNameAttribute>();
			string text = ((attribute2 != null) ? attribute2.displayName : ((attribute == null) ? WidgetReflectionUtils.NicifyVariableName(member.Name) : attribute.displayName));
			named.displayName = LocalizedString.IdWithFallback(text, text);
		}
		if (widget is ITooltipTarget tooltipTarget)
		{
			tooltipTarget.tooltip = (member.TryGetAttribute<TooltipAttribute>(out var attribute3) ? LocalizedString.IdWithFallback(GetMemberTooltipLocaleId(member), attribute3.tooltip) : LocalizedString.Id(GetMemberTooltipLocaleId(member)));
		}
		return widget;
	}
```

- `private BuildMemberImpl(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.Int32 level, System.String path) : Game.UI.Widgets.IWidget`  

```csharp
[NotNull]
	private IWidget BuildMemberImpl(IValueAccessor accessor, object[] attributes, int level, string path)
	{
		IWidget widget = TryBuildField(accessor, attributes, path);
		if (widget == null)
		{
			widget = TryBuildList(accessor, level, path, attributes);
		}
		if (widget == null)
		{
			widget = TryBuildGroup(accessor, level, path);
		}
		if (widget == null)
		{
			widget = BuildUnknownMember(accessor.valueType);
		}
		return widget;
	}
```

- `public BuildMembers(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String parentPath) : System.Collections.Generic.IEnumerable<Game.UI.Widgets.IWidget>`  

```csharp
[NotNull]
	public IEnumerable<IWidget> BuildMembers(IValueAccessor accessor, int level, string parentPath)
	{
		List<MemberInfo> list = new List<MemberInfo>();
		list.AddRange(GetSpecialMembers(accessor.valueType));
		list.AddRange(FormatterUtilities.GetSerializableMembers(accessor.valueType, kMemberFilter));
		return list.Select((MemberInfo member) => BuildMember(accessor, member, level, parentPath));
	}
```

- `private BuildUnknownMember(System.Type memberType) : Game.UI.Widgets.ValueField`  

```csharp
private ValueField BuildUnknownMember(Type memberType)
	{
		string name = memberType.Name;
		return new ValueField
		{
			accessor = new ObjectAccessor<string>(name)
		};
	}
```

- `private static GetMemberTooltipLocaleId(System.Reflection.MemberInfo member) : System.String`  

```csharp
private static string GetMemberTooltipLocaleId(MemberInfo member)
	{
		string text = ((member.DeclaringType != null) ? (member.DeclaringType.FullName + "." + member.Name) : member.Name);
		return "Editor.TOOLTIP[" + text + "]";
	}
```

- `private GetSpecialMembers(System.Type type) : System.Reflection.MemberInfo[]`  

```csharp
private MemberInfo[] GetSpecialMembers(Type type)
	{
		if (type.InheritsFrom(typeof(PrefabBase)))
		{
			return typeof(UnityEngine.Object).GetMember("name", MemberTypes.Property, BindingFlags.Instance | BindingFlags.Public);
		}
		return Array.Empty<MemberInfo>();
	}
```

- `public static NamedWidget<T>(T widget, Game.UI.Localization.LocalizedString displayName, Game.UI.Localization.LocalizedString tooltip) : T`  

```csharp
public static T NamedWidget<T>(T widget, Game.UI.Localization.LocalizedString displayName, Game.UI.Localization.LocalizedString tooltip);
```

- `private TryBuildField(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.String path) : Game.UI.Widgets.IWidget`  

```csharp
[CanBeNull]
	private IWidget TryBuildField(IValueAccessor accessor, object[] attributes, string path)
	{
		FieldBuilder fieldBuilder = TryCreateFieldBuilder(accessor.valueType, attributes);
		if (fieldBuilder != null)
		{
			IWidget widget = fieldBuilder(accessor);
			widget.path = path;
			return widget;
		}
		return null;
	}
```

- `private TryBuildGroup(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String path) : Game.UI.Widgets.ExpandableGroup`  

```csharp
[CanBeNull]
	private ExpandableGroup TryBuildGroup(IValueAccessor accessor, int level, string path)
	{
		if (accessor.valueType.IsSerializable && !typeof(ComponentBase).IsAssignableFrom(accessor.valueType))
		{
			return new ExpandableGroup
			{
				path = path,
				children = BuildMembers(accessor, level, path).ToArray()
			};
		}
		return null;
	}
```

- `public TryBuildList(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String path, System.Object[] attributes) : Game.UI.Widgets.PagedList`  

```csharp
[CanBeNull]
	public PagedList TryBuildList(IValueAccessor accessor, int level, string path, object[] attributes)
	{
		IListAdapter listAdapter = TryBuildListAdapter(accessor, level, path, attributes);
		if (listAdapter != null)
		{
			return new PagedList
			{
				adapter = listAdapter,
				level = level,
				path = path
			};
		}
		return null;
	}
```

- `public TryBuildListAdapter(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String path, System.Object[] attributes) : Game.UI.Widgets.IListAdapter`  

```csharp
public IListAdapter TryBuildListAdapter(IValueAccessor accessor, int level, string path, object[] attributes)
	{
		if (WidgetReflectionUtils.IsListType(accessor.valueType))
		{
			Type listElementType = WidgetReflectionUtils.GetListElementType(accessor.valueType);
			if (listElementType != null)
			{
				bool flag = attributes.Any((object attr) => attr is FixedLengthAttribute);
				MemberInfo listElementLabelMember = WidgetReflectionUtils.GetListElementLabelMember(listElementType);
				if (accessor.valueType.IsArray)
				{
					return new ArrayAdapter
					{
						accessor = new CastAccessor<Array>(accessor),
						elementType = listElementType,
						generator = this,
						level = level,
						path = path,
						resizable = !flag,
						attributes = attributes,
						labelMember = listElementLabelMember
					};
				}
				return new ListAdapter
				{
					accessor = new CastAccessor<IList>(accessor),
					listType = accessor.valueType,
					elementType = listElementType,
					generator = this,
					level = level,
					path = path,
					resizable = !flag,
					attributes = attributes,
					labelMember = listElementLabelMember
				};
			}
		}
		return null;
	}
```

- `private TryCreateFieldBuilder(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
[CanBeNull]
	private FieldBuilder TryCreateFieldBuilder(Type memberType, object[] attributes)
	{
		foreach (IFieldBuilderFactory kFactory in kFactories)
		{
			FieldBuilder fieldBuilder = kFactory.TryCreate(memberType, attributes);
			if (fieldBuilder != null)
			{
				return fieldBuilder;
			}
		}
		return null;
	}
```


## Nested types

- `Game.UI.Widgets.EditorGenerator+<>c`  
- `Game.UI.Widgets.EditorGenerator+<>c__DisplayClass16_0`  

