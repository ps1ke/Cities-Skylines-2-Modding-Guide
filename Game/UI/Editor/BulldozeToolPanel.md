# Game.UI.Editor.BulldozeToolPanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Code

```csharp
public class BulldozeToolPanel : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    public BulldozeToolPanel();

    protected virtual System.Void OnCreate();
}
```


## Constructors

- `public BulldozeToolPanel()`  

```csharp
[Preserve]
	public BulldozeToolPanel()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		children = Array.Empty<IWidget>();
		title = "Editor.TOOL[BulldozeTool]";
	}
```


