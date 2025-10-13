# Game.UI.Editor.EditorPrefabTool

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorTool`  
**Implements:** `Game.UI.Editor.IEditorTool`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IUITagProvider`  

## Code

```csharp
public class EditorPrefabTool : Game.UI.Editor.EditorTool, Game.UI.Editor.IEditorTool, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IUITagProvider
{
    private Game.Prefabs.PrefabBase m_LastSelectedPrefab;
    public static const System.String kToolId;

    public EditorPrefabTool(Unity.Entities.World world);

    protected virtual System.Void OnDisable();
    protected virtual System.Void OnEnable();
}
```


## Fields

- `private Game.Prefabs.PrefabBase m_LastSelectedPrefab`  

```csharp
private Game.Prefabs.PrefabBase m_LastSelectedPrefab;
```

- `public static const System.String kToolId`  

```csharp
public static const System.String kToolId;
```


## Constructors

- `public EditorPrefabTool(Unity.Entities.World world)`  

```csharp
public EditorPrefabTool(Unity.Entities.World world);
```


## Methods

- `protected virtual OnDisable() : System.Void`  

```csharp
protected override void OnDisable()
	{
		m_LastSelectedPrefab = m_ToolSystem.activePrefab;
		base.OnDisable();
	}
```

- `protected virtual OnEnable() : System.Void`  

```csharp
protected override void OnEnable()
	{
		base.OnEnable();
		m_ToolSystem.ActivatePrefabTool(m_LastSelectedPrefab);
	}
```


