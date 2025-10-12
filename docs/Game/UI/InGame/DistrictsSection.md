# Game.UI.InGame.DistrictsSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  
- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  
- `private Game.Tools.SelectionToolSystem m_SelectionToolSystem`  
- `private Unity.Entities.EntityQuery m_ConfigQuery`  
- `private Unity.Entities.EntityQuery m_DistrictQuery`  
- `private Unity.Entities.EntityQuery m_DistrictPrefabQuery`  
- `private Unity.Entities.EntityQuery m_DistrictModifiedQuery`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Selecting`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> <districts>k__BackingField`  
- `private System.Boolean <districtMissing>k__BackingField`  

## Properties

- `protected System.String group { protected get }`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> districts { private get; private set }`  
- `private System.Boolean districtMissing { private get; private set }`  

## Constructors

- `public DistrictsSection()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnPreUpdate() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `private OnToolChanged(Game.Tools.ToolBaseSystem tool) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `public RemoveServiceDistrict(Unity.Entities.Entity district) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private ToggleDistrictTool() : System.Void`  
- `private ToggleSelectionTool() : System.Void`  
- `private Visible() : System.Boolean`  

