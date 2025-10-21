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
public Game.UI.Widgets.IWidget Build(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.Int32 level, System.String path);
```

- `private BuildMember(Game.Reflection.IValueAccessor parent, System.Reflection.MemberInfo member, System.Int32 level, System.String parentPath) : Game.UI.Widgets.IWidget`  

```csharp
private Game.UI.Widgets.IWidget BuildMember(Game.Reflection.IValueAccessor parent, System.Reflection.MemberInfo member, System.Int32 level, System.String parentPath);
```

- `private BuildMemberImpl(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.Int32 level, System.String path) : Game.UI.Widgets.IWidget`  

```csharp
private Game.UI.Widgets.IWidget BuildMemberImpl(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.Int32 level, System.String path);
```

- `public BuildMembers(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String parentPath) : System.Collections.Generic.IEnumerable<Game.UI.Widgets.IWidget>`  

```csharp
public System.Collections.Generic.IEnumerable<Game.UI.Widgets.IWidget> BuildMembers(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String parentPath);
```

- `private BuildUnknownMember(System.Type memberType) : Game.UI.Widgets.ValueField`  

```csharp
private Game.UI.Widgets.ValueField BuildUnknownMember(System.Type memberType);
```

- `private static GetMemberTooltipLocaleId(System.Reflection.MemberInfo member) : System.String`  

```csharp
private static System.String GetMemberTooltipLocaleId(System.Reflection.MemberInfo member);
```

- `private GetSpecialMembers(System.Type type) : System.Reflection.MemberInfo[]`  

```csharp
private System.Reflection.MemberInfo[] GetSpecialMembers(System.Type type);
```

- `public static NamedWidget<T>(T widget, Game.UI.Localization.LocalizedString displayName, Game.UI.Localization.LocalizedString tooltip) : T`  

```csharp
public static T NamedWidget<T>(T widget, Game.UI.Localization.LocalizedString displayName, Game.UI.Localization.LocalizedString tooltip);
```

- `private TryBuildField(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.String path) : Game.UI.Widgets.IWidget`  

```csharp
private Game.UI.Widgets.IWidget TryBuildField(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.String path);
```

- `private TryBuildGroup(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String path) : Game.UI.Widgets.ExpandableGroup`  

```csharp
private Game.UI.Widgets.ExpandableGroup TryBuildGroup(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String path);
```

- `public TryBuildList(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String path, System.Object[] attributes) : Game.UI.Widgets.PagedList`  

```csharp
public Game.UI.Widgets.PagedList TryBuildList(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String path, System.Object[] attributes);
```

- `public TryBuildListAdapter(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String path, System.Object[] attributes) : Game.UI.Widgets.IListAdapter`  

```csharp
public Game.UI.Widgets.IListAdapter TryBuildListAdapter(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String path, System.Object[] attributes);
```

- `private TryCreateFieldBuilder(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

```csharp
private Game.UI.Widgets.FieldBuilder TryCreateFieldBuilder(System.Type memberType, System.Object[] attributes);
```


## Nested types

- `Game.UI.Widgets.EditorGenerator+<>c`  
- `Game.UI.Widgets.EditorGenerator+<>c__DisplayClass16_0`  

