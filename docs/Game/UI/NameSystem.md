# Game.UI.NameSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_DeletedQuery`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_Names`  

## Constructors

- `public NameSystem()`  

## Methods

- `public BindFamilyName(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity household) : System.Void`  
- `public BindName(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  
- `public BindNameForVirtualKeyboard(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `private GetBrandId(Unity.Entities.Entity building) : System.String`  
- `private GetCitizenName(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : Game.UI.NameSystem+Name`  
- `public GetDebugName(Unity.Entities.Entity entity) : System.String`  
- `private GetFamilyName(Unity.Entities.Entity household) : Game.UI.NameSystem+Name`  
- `private GetGenderedLastNameId(Unity.Entities.Entity household, System.Boolean male) : System.String`  
- `private GetId(Unity.Entities.Entity entity, System.Boolean useRandomLocalization = True) : System.String`  
- `private GetMarkerTransportStopName(Unity.Entities.Entity stop) : Game.UI.NameSystem+Name`  
- `public GetName(Unity.Entities.Entity entity, System.Boolean omitBrand = False) : Game.UI.NameSystem+Name`  
- `public GetNameForVirtualKeyboard(Unity.Entities.Entity entity) : Game.UI.NameSystem+Name`  
- `public GetRenderedLabelName(Unity.Entities.Entity entity) : System.String`  
- `private GetResidentName(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : Game.UI.NameSystem+Name`  
- `private GetRouteName(Unity.Entities.Entity route, Unity.Entities.Entity prefab) : Game.UI.NameSystem+Name`  
- `private GetSpawnableBuildingName(Unity.Entities.Entity building, Unity.Entities.Entity zone, System.Boolean omitBrand = False) : Game.UI.NameSystem+Name`  
- `private GetStaticTransportStopName(Unity.Entities.Entity stop) : Game.UI.NameSystem+Name`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetCustomName(Unity.Entities.Entity entity, System.String name) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public TryGetCustomName(Unity.Entities.Entity entity, System.String& customName) : System.Boolean`  

## Nested types

- `Game.UI.NameSystem+NameType`  
- `Game.UI.NameSystem+Name`  

