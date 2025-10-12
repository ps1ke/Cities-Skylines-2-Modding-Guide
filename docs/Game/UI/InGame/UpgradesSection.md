# Game.UI.InGame.UpgradesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <extensions>k__BackingField`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> <subBuildings>k__BackingField`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  
- `private Game.Prefabs.UIInitializeSystem m_UIInitializeSystem`  
- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  
- `private Game.Prefabs.PolicyPrefab m_BuildingOutOfServicePolicy`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private Unity.Entities.EntityQuery m_SoundQuery`  

## Properties

- `protected System.String group { protected get }`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> extensions { private get; private set }`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> subBuildings { private get; private set }`  

## Constructors

- `public UpgradesSection()`  

## Methods

- `private GetUpgradable(Unity.Entities.Entity entity) : Unity.Entities.Entity`  
- `protected virtual OnCreate() : System.Void`  
- `private OnDelete(Unity.Entities.Entity entity) : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `private OnFocus(Unity.Entities.Entity entity) : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `private OnRelocate(Unity.Entities.Entity entity) : System.Void`  
- `private OnToggle(Unity.Entities.Entity entity) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

