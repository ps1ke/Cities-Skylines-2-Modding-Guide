# Game.UI.InGame.LifePathUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Triggers.LifePathEventSystem m_LifePathEventSystem`  
- `private Game.UI.NameSystem m_NameSystem`  
- `private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem`  
- `private Game.UI.InGame.ChirperUISystem m_ChirperUISystem`  
- `private Unity.Entities.EntityQuery m_FollowedQuery`  
- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  
- `private System.Int32 m_FollowedVersion`  
- `private System.Int32 m_LifePathEntryVersion`  
- `private System.Int32 m_ChirpVersion`  
- `private Colossal.UI.Binding.RawValueBinding m_FollowedCitizensBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_LifePathDetailsBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_LifePathItemsBinding`  
- `private static const System.String kGroup`  

## Constructors

- `public LifePathUISystem()`  

## Methods

- `private <OnCreate>b__13_0(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen) : System.Void`  
- `private <OnCreate>b__13_1(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen) : System.Void`  
- `private BindFollowedCitizens(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private BindLifePathDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  
- `private BindLifePathEvent(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  
- `private BindLifePathItems(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen) : System.Void`  
- `private FollowCitizen(Unity.Entities.Entity citizen) : System.Void`  
- `private GetRandomIndex(Unity.Entities.Entity entity) : System.Int32`  
- `private GetSortedFollowedCitizens() : Unity.Collections.NativeArray<Unity.Entities.Entity>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private UnfollowCitizen(Unity.Entities.Entity citizen) : System.Void`  

## Nested types

- `Game.UI.InGame.LifePathUISystem+FollowedCitizenComparer`  

