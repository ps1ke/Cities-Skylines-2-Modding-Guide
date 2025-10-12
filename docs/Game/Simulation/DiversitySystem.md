# Game.Simulation.DiversitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_AtmosphereQuery`  
- `private Unity.Entities.EntityQuery m_AtmospherePrefabQuery`  
- `private Unity.Entities.EntityQuery m_BiomeQuery`  
- `private Unity.Entities.EntityQuery m_BiomePrefabQuery`  
- `private Unity.Entities.EntityQuery m_EditorContainerQuery`  

## Constructors

- `public DiversitySystem()`  

## Methods

- `public ApplyAtmospherePreset(Unity.Entities.Entity atmospherePrefab) : System.Void`  
- `public ApplyBiomePreset(Unity.Entities.Entity biomePrefab) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

