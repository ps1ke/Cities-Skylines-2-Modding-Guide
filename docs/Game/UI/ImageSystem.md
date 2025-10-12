# Game.UI.ImageSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private static const System.String kPlaceholderIcon`  
- `private static const System.String kCitizenIcon`  
- `private static const System.String kTouristIcon`  
- `private static const System.String kCommuterIcon`  
- `private static const System.String kAnimalIcon`  
- `private static const System.String kPetIcon`  
- `private static const System.String kHealthcareIcon`  
- `private static const System.String kDeathcareIcon`  
- `private static const System.String kPoliceIcon`  
- `private static const System.String kGarbageIcon`  
- `private static const System.String kFireIcon`  
- `private static const System.String kPostIcon`  
- `private static const System.String kDeliveryIcon`  

## Properties

- `public System.String placeholderIcon { get }`  

## Constructors

- `public ImageSystem()`  

## Methods

- `public GetGroupIcon(Unity.Entities.Entity prefabEntity) : System.String`  
- `public static GetIcon(Game.Prefabs.PrefabBase prefab) : System.String`  
- `public GetIconOrGroupIcon(Unity.Entities.Entity prefabEntity) : System.String`  
- `public GetInstanceIcon(Unity.Entities.Entity instanceEntity) : System.String`  
- `public GetInstanceIcon(Unity.Entities.Entity instanceEntity, Unity.Entities.Entity prefabEntity) : System.String`  
- `public GetThumbnail(Unity.Entities.Entity prefabEntity) : System.String`  
- `public static GetThumbnail(Game.Prefabs.PrefabBase prefab) : System.String`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

