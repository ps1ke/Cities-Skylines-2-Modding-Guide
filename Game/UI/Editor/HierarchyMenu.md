# Game.UI.Editor.HierarchyMenu

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class abstract public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public abstract class HierarchyMenu : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    protected HierarchyMenu();

    protected abstract System.Void OnSetItemExpanded(System.Int32 viewportIndex, System.Boolean expanded);
    protected abstract System.Void OnSetItemSelected(System.Int32 viewportIndex, System.Boolean selected);
    protected abstract System.Void OnSetRenderedRange(System.Int32 startVisibleIndex, System.Int32 endVisibleIndex);
}
```


## Constructors

- `protected HierarchyMenu()`  

```csharp
protected HierarchyMenu();
```


## Methods

- `protected abstract OnSetItemExpanded(System.Int32 viewportIndex, System.Boolean expanded) : System.Void`  

```csharp
protected abstract System.Void OnSetItemExpanded(System.Int32 viewportIndex, System.Boolean expanded);
```

- `protected abstract OnSetItemSelected(System.Int32 viewportIndex, System.Boolean selected) : System.Void`  

```csharp
protected abstract System.Void OnSetItemSelected(System.Int32 viewportIndex, System.Boolean selected);
```

- `protected abstract OnSetRenderedRange(System.Int32 startVisibleIndex, System.Int32 endVisibleIndex) : System.Void`  

```csharp
protected abstract System.Void OnSetRenderedRange(System.Int32 startVisibleIndex, System.Int32 endVisibleIndex);
```


## Nested types

- `Game.UI.Editor.HierarchyMenu+SelectionType`  
- `Game.UI.Editor.HierarchyMenu+Bindings`  

