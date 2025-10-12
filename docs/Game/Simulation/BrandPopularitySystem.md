# Game.Simulation.BrandPopularitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_ModifiedQuery`  
- `private Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity> m_BrandPopularity`  
- `private Unity.Jobs.JobHandle m_Readers`  
- `private Game.Simulation.BrandPopularitySystem+TypeHandle __TypeHandle`  
- `public static const System.Int32 kUpdatesPerDay`  

## Constructors

- `public BrandPopularitySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public ReadBrandPopularity(Unity.Jobs.JobHandle& dependency) : Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity>`  

## Nested types

- `Game.Simulation.BrandPopularitySystem+BrandPopularity`  
- `Game.Simulation.BrandPopularitySystem+UpdateBrandPopularityJob`  
- `Game.Simulation.BrandPopularitySystem+TypeHandle`  

