# Game.UI.Editor.EditorToolUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem`  
- `private Game.UI.Editor.InspectorPanelSystem m_InspectorPanelSystem`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.Editor.IEditorTool[]> m_ToolsBinding`  
- `private Game.UI.Editor.IEditorTool[] m_Tools`  
- `private System.Boolean[] m_Disabled`  
- `private Game.UI.Editor.IEditorTool m_ActiveTool`  
- `private Unity.Entities.Entity m_LastSelectedEntity`  
- `private static const System.String kGroup`  

## Properties

- `public Game.GameMode gameMode { get }`  
- `public Game.UI.Editor.IEditorTool[] tools { get; set }`  
- `public Game.UI.Editor.IEditorTool activeTool { get; set }`  

## Constructors

- `public EditorToolUISystem()`  

## Methods

- `private <OnCreate>b__17_0() : Game.UI.Editor.IEditorTool[]`  
- `private <OnCreate>b__17_1() : System.String`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public SelectEntity(Unity.Entities.Entity entity) : System.Void`  
- `public SelectEntitySubMesh(Unity.Entities.Entity entity, System.Int32 subMeshIndex) : System.Void`  
- `public SelectTool(System.String id) : System.Void`  
- `private UpdateToolState() : System.Boolean`  

## Nested types

- `Game.UI.Editor.EditorToolUISystem+<>c`  
- `Game.UI.Editor.EditorToolUISystem+<>c__DisplayClass21_0`  

