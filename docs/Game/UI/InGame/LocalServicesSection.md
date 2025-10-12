# Game.UI.InGame.LocalServicesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.ImageSystem m_ImageSystem`  
- `private Unity.Entities.EntityQuery m_ServiceDistrictBuildingQuery`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> <localServiceBuildings>k__BackingField`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> <prefabs>k__BackingField`  

## Properties

- `protected System.String group { protected get }`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> localServiceBuildings { private get; private set }`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> prefabs { private get; private set }`  

## Constructors

- `public LocalServicesSection()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  

