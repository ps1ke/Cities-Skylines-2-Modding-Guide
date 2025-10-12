# Game.UI.InGame.ChirperUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem`  
- `private Game.UI.InGame.InfoviewsUISystem m_InfoviewsUISystem`  
- `private Game.UI.InGame.ChirpLinkSystem m_ChirpLinkSystem`  
- `private Game.UI.NameSystem m_NameSystem`  
- `private Unity.Entities.EntityQuery m_ChirpQuery`  
- `private Unity.Entities.EntityQuery m_ModifiedChirpQuery`  
- `private Unity.Entities.EntityQuery m_CreatedChirpQuery`  
- `private Unity.Entities.EntityQuery m_TimeDataQuery`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Colossal.UI.Binding.RawValueBinding m_ChirpsBinding`  
- `private Colossal.UI.Binding.RawEventBinding m_ChirpAddedBinding`  
- `private static const System.String kGroup`  
- `private static const System.Int32 kBrandIconSize`  

## Constructors

- `public ChirperUISystem()`  

## Methods

- `private AddLike(Unity.Entities.Entity entity) : System.Void`  
- `public BindChirp(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity chirpEntity, System.Boolean newChirp = False) : System.Void`  
- `private BindChirpLink(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, System.Int32 linkIndex) : System.Void`  
- `public BindChirpLink(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.UI.NameSystem+Name name) : System.Void`  
- `private BindChirpSender(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  
- `private GetAvatar(Unity.Entities.Entity chirpEntity) : System.String`  
- `public GetMessageID(Unity.Entities.Entity chirp) : System.String`  
- `private GetRandomIndex(Unity.Entities.Entity chirpEntity) : System.Int32`  
- `private GetSortedChirps(Unity.Entities.EntityQuery chirpQuery) : Unity.Collections.NativeArray<Unity.Entities.Entity>`  
- `private GetTicks(System.UInt32 frameIndex) : System.UInt32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private PublishAddedChirps() : System.Void`  
- `private RemoveLike(Unity.Entities.Entity entity) : System.Void`  
- `private SelectLink(System.String target) : System.Void`  
- `private UpdateChirps(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

## Nested types

- `Game.UI.InGame.ChirperUISystem+ChirpComparer`  

