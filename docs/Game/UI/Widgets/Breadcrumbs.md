# Game.UI.Widgets.Breadcrumbs

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `System.Collections.Generic.IEnumerable<Game.UI.Widgets.Label>`, `System.Collections.IEnumerable`, `Game.UI.Widgets.IContainerWidget`  

## Fields

- `private System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_Labels`  

## Properties

- `public System.Int32 labelCount { get }`  
- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get }`  
- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get }`  

## Constructors

- `public Breadcrumbs()`  

## Methods

- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Game.UI.Widgets.Label>`  
- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  
- `public WithLabel(Game.UI.Widgets.Label label) : Game.UI.Widgets.Breadcrumbs`  
- `public WithOutLabel(Game.UI.Widgets.Label label) : Game.UI.Widgets.Breadcrumbs`  

