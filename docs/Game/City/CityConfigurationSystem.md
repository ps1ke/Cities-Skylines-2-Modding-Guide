# Game.City.CityConfigurationSystem

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.String <cityName>k__BackingField`  
- `private System.String <overrideCityName>k__BackingField`  
- `private System.String m_LoadedCityName`  
- `private System.String <overrideThemeName>k__BackingField`  
- `private Unity.Entities.Entity <defaultTheme>k__BackingField`  
- `private Unity.Entities.Entity <loadedDefaultTheme>k__BackingField`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_RequiredContent`  
- `private System.Boolean <leftHandTraffic>k__BackingField`  
- `private System.Boolean <overrideLeftHandTraffic>k__BackingField`  
- `private System.Boolean m_LoadedLeftHandTraffic`  
- `private System.Boolean <naturalDisasters>k__BackingField`  
- `private System.Boolean <overrideNaturalDisasters>k__BackingField`  
- `private System.Boolean m_LoadedNaturalDisasters`  
- `private System.Boolean <overrideUnlockAll>k__BackingField`  
- `private System.Boolean m_UnlockAll`  
- `private System.Boolean m_LoadedUnlockAll`  
- `private System.Boolean <overrideUnlimitedMoney>k__BackingField`  
- `private System.Boolean m_UnlimitedMoney`  
- `private System.Boolean m_LoadedUnlimitedMoney`  
- `private System.Boolean <overrideUnlockMapTiles>k__BackingField`  
- `private System.Boolean m_UnlockMapTiles`  
- `private System.Boolean m_LoadedUnlockMapTiles`  
- `private System.Boolean <overrideLoadedOptions>k__BackingField`  
- `private System.Collections.Generic.HashSet<System.String> <usedMods>k__BackingField`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Prefabs.UnlockAllSystem m_UnlockAllSystem`  
- `private Game.Net.FlipTrafficHandednessSystem m_FlipTrafficHandednessSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Unity.Entities.EntityQuery m_ThemeQuery`  
- `private Unity.Entities.EntityQuery m_SubLaneQuery`  
- `public Unity.Mathematics.float3 m_CameraPivot`  
- `public Unity.Mathematics.float2 m_CameraAngle`  
- `public System.Single m_CameraZoom`  
- `public Unity.Entities.Entity m_CameraFollow`  
- `private static readonly Unity.Mathematics.float3 kDefaultCameraPivot`  
- `private static readonly Unity.Mathematics.float2 kDefaultCameraAngle`  
- `private static readonly System.Single kDefaultCameraZoom`  
- `private static readonly Unity.Entities.Entity kDefaultCameraFollow`  

## Properties

- `public System.String cityName { get; set }`  
- `public System.String overrideCityName { get; set }`  
- `public System.String overrideThemeName { get; set }`  
- `public Unity.Entities.Entity defaultTheme { get; set }`  
- `public Unity.Entities.Entity loadedDefaultTheme { get; set }`  
- `public Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& requiredContent { get }`  
- `public System.Boolean leftHandTraffic { get; set }`  
- `public System.Boolean overrideLeftHandTraffic { get; set }`  
- `public System.Boolean naturalDisasters { get; set }`  
- `public System.Boolean overrideNaturalDisasters { get; set }`  
- `public System.Boolean unlockAll { get; set }`  
- `public System.Boolean overrideUnlockAll { get; set }`  
- `public System.Boolean unlimitedMoney { get; set }`  
- `public System.Boolean overrideUnlimitedMoney { get; set }`  
- `public System.Boolean unlockMapTiles { get; set }`  
- `public System.Boolean overrideUnlockMapTiles { get; set }`  
- `public System.Boolean overrideLoadedOptions { get; set }`  
- `public System.Collections.Generic.HashSet<System.String> usedMods { get; private set }`  

## Constructors

- `public CityConfigurationSystem()`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PatchReferences(Game.Serialization.PrefabReferences& references) : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private ResetCameraProperties() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

