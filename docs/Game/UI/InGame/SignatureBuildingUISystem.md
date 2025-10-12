# Game.UI.InGame.SignatureBuildingUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Unity.Entities.EntityQuery m_UnlockedSignatureBuildingQuery`  
- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Unity.Entities.Entity>> m_UnlockSignaturesBinding`  
- `private System.Boolean m_SkipUpdate`  
- `private System.Int32 m_LastListCount`  
- `private System.Boolean m_NeedTriggerUpdate`  
- `private static const System.String kGroup`  

## Constructors

- `public SignatureBuildingUISystem()`  

## Methods

- `public AddUnlockedSignature(Unity.Entities.Entity prefab) : System.Void`  
- `public ClearUnlockedSignature() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private RemoveUnlockedSignature() : System.Void`  
- `public SkipUpdate() : System.Void`  

