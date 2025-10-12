# Game.UI.InGame.InfoSectionBase

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Boolean <visible>k__BackingField`  
- `private System.Collections.Generic.List<System.String> <tooltipKeys>k__BackingField`  
- `private System.Collections.Generic.List<System.String> <tooltipTags>k__BackingField`  
- `protected System.Boolean m_Dirty`  
- `protected Game.UI.NameSystem m_NameSystem`  
- `protected Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `protected Game.EndFrameBarrier m_EndFrameBarrier`  
- `protected Game.UI.InGame.SelectedInfoUISystem m_InfoUISystem`  

## Properties

- `public Game.GameMode gameMode { get }`  
- `public System.Boolean visible { get; protected set }`  
- `protected System.Boolean displayForDestroyedObjects { protected get }`  
- `protected System.Boolean displayForOutsideConnections { protected get }`  
- `protected System.Boolean displayForUnderConstruction { protected get }`  
- `protected System.Boolean displayForUpgrades { protected get }`  
- `protected System.String group { protected get }`  
- `protected System.Collections.Generic.List<System.String> tooltipKeys { protected get; protected set }`  
- `protected System.Collections.Generic.List<System.String> tooltipTags { protected get; protected set }`  
- `protected Unity.Entities.Entity selectedEntity { protected get }`  
- `protected Unity.Entities.Entity selectedPrefab { protected get }`  
- `protected System.Boolean Destroyed { protected get }`  
- `protected System.Boolean OutsideConnection { protected get }`  
- `protected System.Boolean UnderConstruction { protected get }`  
- `protected System.Boolean Upgrade { protected get }`  

## Constructors

- `protected InfoSectionBase()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnPreUpdate() : System.Void`  
- `protected abstract OnProcess() : System.Void`  
- `public abstract OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `public PerformUpdate() : System.Void`  
- `public RequestUpdate() : System.Void`  
- `protected abstract Reset() : System.Void`  
- `protected TryGetComponentWithUpgrades<T>(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, T& data) : System.Boolean`  
- `private Visible() : System.Boolean`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

