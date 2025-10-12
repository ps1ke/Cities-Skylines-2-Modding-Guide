# Game.UI.Editor.DiversityPanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Simulation.DiversitySystem m_DiversitySystem`  
- `private Unity.Entities.EntityQuery m_AtmosphereQuery`  
- `private Unity.Entities.EntityQuery m_BiomeQuery`  
- `private Game.Prefabs.AtmospherePrefab m_Atmosphere`  
- `private Game.Prefabs.BiomePrefab m_Biome`  

## Constructors

- `public DiversityPanelSystem()`  

## Methods

- `private <OnCreate>b__6_0() : Game.Prefabs.PrefabBase`  
- `private <OnCreate>b__6_1() : Game.Prefabs.PrefabBase`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `private SetAtmosphere(Game.Prefabs.PrefabBase prefab) : System.Void`  
- `private SetBiome(Game.Prefabs.PrefabBase prefab) : System.Void`  

