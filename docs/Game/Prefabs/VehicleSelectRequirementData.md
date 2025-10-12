# Game.Prefabs.VehicleSelectRequirementData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.Locked> m_LockedType`  
- `private Unity.Entities.BufferTypeHandle<Game.Prefabs.ObjectRequirementElement> m_ObjectRequirementType`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.ThemeData> m_ThemeData`  
- `private Unity.Entities.Entity m_DefaultTheme`  

## Constructors

- `public VehicleSelectRequirementData(Unity.Entities.SystemBase system)`  

## Methods

- `public CheckRequirements(Game.Prefabs.VehicleSelectRequirementData+Chunk& chunk, System.Int32 index, System.Boolean ignoreTheme = False) : System.Boolean`  
- `public GetChunk(Unity.Entities.ArchetypeChunk chunk) : Game.Prefabs.VehicleSelectRequirementData+Chunk`  
- `public Update(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem) : System.Void`  

## Nested types

- `Game.Prefabs.VehicleSelectRequirementData+Chunk`  

