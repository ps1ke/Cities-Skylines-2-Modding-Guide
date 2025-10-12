# Game.UI.Editor.EditorTool

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.IEditorTool`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IUITagProvider`  

## Fields

- `private System.String <id>k__BackingField`  
- `private System.String <icon>k__BackingField`  
- `private System.Boolean <disabled>k__BackingField`  
- `private System.String <shortcut>k__BackingField`  
- `private System.String <uiTag>k__BackingField`  
- `private Game.UI.Editor.IEditorPanel <panel>k__BackingField`  
- `private Game.Tools.ToolBaseSystem <tool>k__BackingField`  
- `protected Game.Tools.ToolSystem m_ToolSystem`  
- `protected Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem`  

## Properties

- `public System.String id { get; set }`  
- `public System.String icon { get; set }`  
- `public System.Boolean disabled { get; set }`  
- `public System.String shortcut { get; set }`  
- `public System.String uiTag { get; set }`  
- `public Game.UI.Editor.IEditorPanel panel { get; set }`  
- `public Game.Tools.ToolBaseSystem tool { get; set }`  
- `public System.Boolean active { get; set }`  

## Constructors

- `public EditorTool(Unity.Entities.World world)`  

## Methods

- `protected virtual IsActive() : System.Boolean`  
- `protected virtual OnDisable() : System.Void`  
- `protected virtual OnEnable() : System.Void`  

