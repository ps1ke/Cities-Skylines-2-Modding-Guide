# Game.UI.InGame.UniqueAssetTrackingSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.UI.InGame.IUniqueAssetTrackingSystem`  

## Fields

- `private Unity.Entities.EntityQuery m_LoadedUniqueAssetQuery`  
- `private Unity.Entities.EntityQuery m_DeletedUniqueAssetQuery`  
- `private Unity.Entities.EntityQuery m_PlacedUniqueAssetQuery`  
- `private System.Boolean m_Loaded`  
- `private Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> <placedUniqueAssets>k__BackingField`  
- `private System.Action<Unity.Entities.Entity, System.Boolean> <EventUniqueAssetStatusChanged>k__BackingField`  

## Properties

- `public Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> placedUniqueAssets { get; private set }`  
- `public System.Action<Unity.Entities.Entity, System.Boolean> EventUniqueAssetStatusChanged { get; set }`  

## Constructors

- `public UniqueAssetTrackingSystem()`  

## Methods

- `private GetLoaded() : System.Boolean`  
- `public IsPlacedUniqueAsset(Unity.Entities.Entity entity) : System.Boolean`  
- `public IsUniqueAsset(Unity.Entities.Entity entity) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

