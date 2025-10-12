# Game.UI.InGame.DestroyedBuildingSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  
- `private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Rebuilding`  
- `private Unity.Entities.EntityQuery m_FireStationQuery`  
- `private Unity.Entities.EntityQuery m_ServiceDispatchQuery`  
- `private Unity.Entities.Entity <destroyer>k__BackingField`  
- `private System.Boolean <cleared>k__BackingField`  
- `private System.Single <progress>k__BackingField`  
- `private Game.UI.InGame.DestroyedBuildingSection+Status <status>k__BackingField`  

## Properties

- `protected System.String group { protected get }`  
- `private Unity.Entities.Entity destroyer { private get; private set }`  
- `private System.Boolean cleared { private get; private set }`  
- `private System.Single progress { private get; private set }`  
- `private Game.UI.InGame.DestroyedBuildingSection+Status status { private get; private set }`  
- `protected System.Boolean displayForDestroyedObjects { protected get }`  
- `protected System.Boolean displayForUpgrades { protected get }`  

## Constructors

- `public DestroyedBuildingSection()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `private OnToggleRebuild() : System.Void`  
- `private OnToolChanged(Game.Tools.ToolBaseSystem tool) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private VehicleAtTarget(Unity.Entities.Entity vehicle) : System.Boolean`  
- `private Visible() : System.Boolean`  

## Nested types

- `Game.UI.InGame.DestroyedBuildingSection+Status`  

