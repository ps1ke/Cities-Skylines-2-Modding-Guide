# Game.UI.InGame.PollutionSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.InGame.PollutionThreshold <groundPollutionKey>k__BackingField`  
- `private Game.UI.InGame.PollutionThreshold <airPollutionKey>k__BackingField`  
- `private Game.UI.InGame.PollutionThreshold <noisePollutionKey>k__BackingField`  
- `private Unity.Entities.EntityQuery m_UIConfigQuery`  
- `private Game.UI.InGame.PollutionSection+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_1774369403_0`  
- `private Unity.Entities.EntityQuery __query_1774369403_1`  

## Properties

- `protected System.String group { protected get }`  
- `protected System.Boolean displayForDestroyedObjects { protected get }`  
- `private Game.UI.InGame.PollutionThreshold groundPollutionKey { private get; private set }`  
- `private Game.UI.InGame.PollutionThreshold airPollutionKey { private get; private set }`  
- `private Game.UI.InGame.PollutionThreshold noisePollutionKey { private get; private set }`  

## Constructors

- `public PollutionSection()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetPollution() : Game.Prefabs.PollutionData`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

## Nested types

- `Game.UI.InGame.PollutionSection+TypeHandle`  

