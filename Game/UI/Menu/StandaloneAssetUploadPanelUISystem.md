# Game.UI.Menu.StandaloneAssetUploadPanelUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class StandaloneAssetUploadPanelUISystem : Game.UI.UISystemBase
{
    private Game.UI.Menu.AssetUploadPanelUISystem m_AssetUploadPanelUISystem;
    private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Visible;
    private static readonly System.String kGroup;

    public StandaloneAssetUploadPanelUISystem();

    private System.Void OnChildrenChange(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children);
    private System.Void OnClose();
    protected virtual System.Void OnCreate();
    public System.Void Show(Colossal.IO.AssetDatabase.AssetData mainAsset, System.Boolean allowManualFileCopy);
}
```


## Fields

- `private Game.UI.Menu.AssetUploadPanelUISystem m_AssetUploadPanelUISystem`  

```csharp
private Game.UI.Menu.AssetUploadPanelUISystem m_AssetUploadPanelUISystem;
```

- `private Game.UI.Widgets.WidgetBindings m_WidgetBindings`  

```csharp
private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Visible`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Visible;
```

- `private static readonly System.String kGroup`  

```csharp
private static readonly System.String kGroup;
```


## Constructors

- `public StandaloneAssetUploadPanelUISystem()`  

```csharp
[Preserve]
	public StandaloneAssetUploadPanelUISystem()
	{
	}
```


## Methods

- `private OnChildrenChange(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children) : System.Void`  

```csharp
private void OnChildrenChange(IList<IWidget> children)
	{
		m_WidgetBindings.children = children;
	}
```

- `private OnClose() : System.Void`  

```csharp
private void OnClose()
	{
		if (m_AssetUploadPanelUISystem.Close())
		{
			AssetUploadPanelUISystem assetUploadPanelUISystem = m_AssetUploadPanelUISystem;
			assetUploadPanelUISystem.onChildrenChange = (Action<IList<IWidget>>)Delegate.Remove(assetUploadPanelUISystem.onChildrenChange, new Action<IList<IWidget>>(OnChildrenChange));
			m_AssetUploadPanelUISystem.Enabled = false;
			m_WidgetBindings.children = Array.Empty<IWidget>();
			m_Visible.Update(newValue: false);
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_AssetUploadPanelUISystem = base.World.GetOrCreateSystemManaged<AssetUploadPanelUISystem>();
		m_AssetUploadPanelUISystem.Enabled = false;
		AddUpdateBinding(m_WidgetBindings = new WidgetBindings(kGroup));
		EditorPanelUISystem.AddEditorWidgetBindings(m_WidgetBindings);
		AddBinding(m_Visible = new ValueBinding<bool>(kGroup, "visible", initialValue: false));
		AddBinding(new TriggerBinding(kGroup, "close", OnClose));
	}
```

- `public Show(Colossal.IO.AssetDatabase.AssetData mainAsset, System.Boolean allowManualFileCopy = True) : System.Void`  

```csharp
public void Show(AssetData mainAsset, bool allowManualFileCopy = true)
	{
		m_AssetUploadPanelUISystem.Show(mainAsset, allowManualFileCopy);
		AssetUploadPanelUISystem assetUploadPanelUISystem = m_AssetUploadPanelUISystem;
		assetUploadPanelUISystem.onChildrenChange = (Action<IList<IWidget>>)Delegate.Remove(assetUploadPanelUISystem.onChildrenChange, new Action<IList<IWidget>>(OnChildrenChange));
		AssetUploadPanelUISystem assetUploadPanelUISystem2 = m_AssetUploadPanelUISystem;
		assetUploadPanelUISystem2.onChildrenChange = (Action<IList<IWidget>>)Delegate.Combine(assetUploadPanelUISystem2.onChildrenChange, new Action<IList<IWidget>>(OnChildrenChange));
		m_AssetUploadPanelUISystem.Enabled = true;
		m_WidgetBindings.children = m_AssetUploadPanelUISystem.children;
		m_Visible.Update(newValue: true);
	}
```


