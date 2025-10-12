# Game.UI.Widgets.EditorGenerator

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IEditorGenerator`  

## Fields

- `private System.Int32 <maxLevel>k__BackingField`  
- `public static readonly System.Collections.Generic.List<Game.UI.Widgets.IFieldBuilderFactory> kFactories`  
- `private static readonly Colossal.OdinSerializer.CustomSerializationPolicy kMemberFilter`  
- `private static System.Boolean <sBypassValueLimits>k__BackingField`  

## Properties

- `public System.Int32 maxLevel { get; set }`  
- `public static System.Boolean sBypassValueLimits { get; set }`  

## Constructors

- `public EditorGenerator()`  

## Methods

- `public Build(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.Int32 level, System.String path) : Game.UI.Widgets.IWidget`  
- `private BuildMember(Game.Reflection.IValueAccessor parent, System.Reflection.MemberInfo member, System.Int32 level, System.String parentPath) : Game.UI.Widgets.IWidget`  
- `private BuildMemberImpl(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.Int32 level, System.String path) : Game.UI.Widgets.IWidget`  
- `public BuildMembers(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String parentPath) : System.Collections.Generic.IEnumerable<Game.UI.Widgets.IWidget>`  
- `private BuildUnknownMember(System.Type memberType) : Game.UI.Widgets.ValueField`  
- `private static GetMemberTooltipLocaleId(System.Reflection.MemberInfo member) : System.String`  
- `private GetSpecialMembers(System.Type type) : System.Reflection.MemberInfo[]`  
- `public static NamedWidget<T>(T widget, Game.UI.Localization.LocalizedString displayName, Game.UI.Localization.LocalizedString tooltip) : T`  
- `private TryBuildField(Game.Reflection.IValueAccessor accessor, System.Object[] attributes, System.String path) : Game.UI.Widgets.IWidget`  
- `private TryBuildGroup(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String path) : Game.UI.Widgets.ExpandableGroup`  
- `public TryBuildList(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String path, System.Object[] attributes) : Game.UI.Widgets.PagedList`  
- `public TryBuildListAdapter(Game.Reflection.IValueAccessor accessor, System.Int32 level, System.String path, System.Object[] attributes) : Game.UI.Widgets.IListAdapter`  
- `private TryCreateFieldBuilder(System.Type memberType, System.Object[] attributes) : Game.UI.Widgets.FieldBuilder`  

## Nested types

- `Game.UI.Widgets.EditorGenerator+<>c`  
- `Game.UI.Widgets.EditorGenerator+<>c__DisplayClass16_0`  

