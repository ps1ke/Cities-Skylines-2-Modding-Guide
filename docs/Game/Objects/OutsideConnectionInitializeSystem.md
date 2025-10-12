# Game.Objects.OutsideConnectionInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_ExistingQuery`  
- `private Unity.Entities.EntityQuery m_CreatedQuery`  
- `private Game.Objects.OutsideConnectionInitializeSystem+TypeHandle __TypeHandle`  
- `private static const System.Single kNearbyMaxDistanceSqr`  

## Constructors

- `public OutsideConnectionInitializeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private static GetTransferType(Unity.Entities.Entity prefab, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionData) : Game.Prefabs.OutsideConnectionTransferType`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private static TryGetNearestConnectionRandomIndex(Unity.Collections.NativeList<Game.Objects.OutsideConnectionInitializeSystem+OutsideConnectionInfo> connections, Game.Prefabs.OutsideConnectionTransferType transferType, Unity.Mathematics.float3 position, Game.Common.RandomLocalizationIndex& randomIndex) : System.Boolean`  

## Nested types

- `Game.Objects.OutsideConnectionInitializeSystem+CollectOutsideConnectionsJob`  
- `Game.Objects.OutsideConnectionInitializeSystem+InitializeLocalizationJob`  
- `Game.Objects.OutsideConnectionInitializeSystem+OutsideConnectionInfo`  
- `Game.Objects.OutsideConnectionInitializeSystem+TypeHandle`  

