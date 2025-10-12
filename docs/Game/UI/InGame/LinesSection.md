# Game.UI.InGame.LinesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.InGame.TransportationOverviewUISystem m_TransportationOverviewUISystem`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> <lines>k__BackingField`  
- `private Unity.Collections.NativeArray<System.Boolean> m_BoolResult`  
- `private Unity.Collections.NativeArray<System.Int32> m_PassengersResult`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_LinesResult`  
- `private Game.UI.InGame.LinesSection+TypeHandle __TypeHandle`  

## Properties

- `protected System.String group { protected get }`  
- `protected System.Boolean displayForOutsideConnections { protected get }`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> lines { private get; private set }`  

## Constructors

- `public LinesSection()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `private OnToggle(Unity.Entities.Entity entity, System.Boolean state) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  

## Nested types

- `Game.UI.InGame.LinesSection+Result`  
- `Game.UI.InGame.LinesSection+LinesJob`  
- `Game.UI.InGame.LinesSection+TypeHandle`  

