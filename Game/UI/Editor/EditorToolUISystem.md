# Game.UI.Editor.EditorToolUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class EditorToolUISystem : Game.UI.UISystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem;
    private Game.UI.Editor.InspectorPanelSystem m_InspectorPanelSystem;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.Editor.IEditorTool[]> m_ToolsBinding;
    private Game.UI.Editor.IEditorTool[] m_Tools;
    private System.Boolean[] m_Disabled;
    private Game.UI.Editor.IEditorTool m_ActiveTool;
    private Unity.Entities.Entity m_LastSelectedEntity;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }
    public Game.UI.Editor.IEditorTool[] tools { get; set; }
    public Game.UI.Editor.IEditorTool activeTool { get; set; }

    public EditorToolUISystem();

    private Game.UI.Editor.IEditorTool[] <OnCreate>b__17_0();
    private System.String <OnCreate>b__17_1();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void SelectEntity(Unity.Entities.Entity entity);
    public System.Void SelectEntitySubMesh(Unity.Entities.Entity entity, System.Int32 subMeshIndex);
    public System.Void SelectTool(System.String id);
    private System.Boolean UpdateToolState();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem`  

```csharp
private Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem;
```

- `private Game.UI.Editor.InspectorPanelSystem m_InspectorPanelSystem`  

```csharp
private Game.UI.Editor.InspectorPanelSystem m_InspectorPanelSystem;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.Editor.IEditorTool[]> m_ToolsBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.Editor.IEditorTool[]> m_ToolsBinding;
```

- `private Game.UI.Editor.IEditorTool[] m_Tools`  

```csharp
private Game.UI.Editor.IEditorTool[] m_Tools;
```

- `private System.Boolean[] m_Disabled`  

```csharp
private System.Boolean[] m_Disabled;
```

- `private Game.UI.Editor.IEditorTool m_ActiveTool`  

```csharp
private Game.UI.Editor.IEditorTool m_ActiveTool;
```

- `private Unity.Entities.Entity m_LastSelectedEntity`  

```csharp
private Unity.Entities.Entity m_LastSelectedEntity;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```

- `public Game.UI.Editor.IEditorTool[] tools { get; set }`  

```csharp
public Game.UI.Editor.IEditorTool[] tools { get; set; }
```

- `public Game.UI.Editor.IEditorTool activeTool { get; set }`  

```csharp
public Game.UI.Editor.IEditorTool activeTool { get; set; }
```


## Constructors

- `public EditorToolUISystem()`  

```csharp
public EditorToolUISystem();
```


## Methods

- `private <OnCreate>b__17_0() : Game.UI.Editor.IEditorTool[]`  

```csharp
private Game.UI.Editor.IEditorTool[] <OnCreate>b__17_0();
```

- `private <OnCreate>b__17_1() : System.String`  

```csharp
private System.String <OnCreate>b__17_1();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public SelectEntity(Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void SelectEntity(Unity.Entities.Entity entity);
```

- `public SelectEntitySubMesh(Unity.Entities.Entity entity, System.Int32 subMeshIndex) : System.Void`  

```csharp
public System.Void SelectEntitySubMesh(Unity.Entities.Entity entity, System.Int32 subMeshIndex);
```

- `public SelectTool(System.String id) : System.Void`  

```csharp
public System.Void SelectTool(System.String id);
```

- `private UpdateToolState() : System.Boolean`  

```csharp
private System.Boolean UpdateToolState();
```


## Nested types

- `Game.UI.Editor.EditorToolUISystem+<>c`  
- `Game.UI.Editor.EditorToolUISystem+<>c__DisplayClass21_0`  

