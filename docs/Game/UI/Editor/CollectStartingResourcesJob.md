# Game.UI.Editor.MapRequirementSystem+CollectStartingResourcesJob

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeArray<Unity.Entities.Entity> m_StartingTiles`  
- `public Unity.Entities.BufferLookup<Game.Areas.MapFeatureElement> m_MapFeatureElements`  
- `public Unity.Collections.NativeArray<System.Boolean> m_Results`  

## Methods

- `private Check(Unity.Entities.Entity entity) : System.Void`  
- `public Execute() : System.Void`  

