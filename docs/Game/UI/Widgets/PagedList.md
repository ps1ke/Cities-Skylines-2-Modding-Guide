# Game.UI.Widgets.PagedList

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.NamedWidgetWithTooltip`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.IExpandable`, `Game.UI.Widgets.IPaged`, `Game.UI.Widgets.IListWidget`, `Game.UI.Widgets.IContainerWidget`  

## Fields

- `private System.Int32 m_Length`  
- `private System.Int32 m_CurrentPageIndex`  
- `private System.Int32 m_ChildStartIndex`  
- `private System.Int32 m_ChildEndIndex`  
- `private System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_Children`  
- `private System.Boolean m_Expanded`  
- `private Game.UI.Widgets.IListAdapter <adapter>k__BackingField`  
- `private System.Int32 <level>k__BackingField`  
- `private System.Int32 <pageSize>k__BackingField`  

## Properties

- `public System.Boolean expanded { get; set }`  
- `public Game.UI.Widgets.IListAdapter adapter { get; set }`  
- `public System.Int32 level { get; set }`  
- `public System.Int32 pageSize { get; set }`  
- `public System.Int32 pageCount { get }`  
- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get }`  
- `public System.Int32 currentPageIndex { get; set }`  
- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get }`  

## Constructors

- `public PagedList()`  

## Methods

- `public AddElement() : System.Int32`  
- `private CalculateChildIndices(System.Int32 pageIndex, System.Int32 length, System.Int32& childStartIndex, System.Int32& childEndIndex) : System.Void`  
- `private CalculateIndices(System.Int32 elementIndex, System.Int32 length, System.Int32& pageIndex, System.Int32& childStartIndex, System.Int32& childEndIndex) : System.Void`  
- `public Clear() : System.Void`  
- `public DeleteElement(System.Int32 index) : System.Void`  
- `private DisableChildren(Game.UI.Widgets.IWidget child) : System.Void`  
- `public DuplicateElement(System.Int32 index) : System.Int32`  
- `public InsertElement(System.Int32 index) : System.Void`  
- `public MoveElement(System.Int32 fromIndex, System.Int32 toIndex) : System.Void`  
- `private ShowElement(System.Int32 elementIndex) : System.Void`  
- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.UI.Widgets.PagedList+<>c`  

