# Game.Buildings.LocalEffectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_UpdatedProvidersQuery`  
- `private Unity.Entities.EntityQuery m_AllProvidersQuery`  
- `private Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds> m_SearchTree`  
- `private Unity.Jobs.JobHandle m_ReadDependencies`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private System.Boolean m_Loaded`  
- `private Game.Buildings.LocalEffectSystem+TypeHandle __TypeHandle`  

## Constructors

- `public LocalEffectSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddLocalEffectReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddLocalEffectWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public static AddToTempList(Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalModifierData> localModifiers, System.Boolean disabled) : System.Void`  
- `public static GetEffectBounds(Game.Objects.Transform transform, Game.Prefabs.LocalModifierData localModifier, Game.Buildings.LocalEffectSystem+EffectBounds& effectBounds) : System.Boolean`  
- `public static GetEffectBounds(Game.Objects.Transform transform, System.Single efficiency, Game.Prefabs.LocalModifierData localModifier, Game.Buildings.LocalEffectSystem+EffectBounds& effectBounds) : System.Boolean`  
- `private GetLoaded() : System.Boolean`  
- `public GetReadData(Unity.Jobs.JobHandle& dependencies) : Game.Buildings.LocalEffectSystem+ReadData`  
- `public GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Game.Buildings.LocalEffectSystem+EffectItem, Game.Buildings.LocalEffectSystem+EffectBounds>`  
- `public static InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.LocalModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalModifierData> localModifiers) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Buildings.LocalEffectSystem+EffectItem`  
- `Game.Buildings.LocalEffectSystem+EffectBounds`  
- `Game.Buildings.LocalEffectSystem+ReadData`  
- `Game.Buildings.LocalEffectSystem+UpdateLocalEffectsJob`  
- `Game.Buildings.LocalEffectSystem+TypeHandle`  

