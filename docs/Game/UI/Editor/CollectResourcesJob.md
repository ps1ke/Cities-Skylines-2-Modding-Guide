# Game.UI.Editor.MapRequirementSystem+CollectResourcesJob

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> m_AreaChunks`  
- `public Unity.Entities.BufferTypeHandle<Game.Areas.MapFeatureElement> m_MapFeatureElementType`  
- `public Unity.Collections.NativeArray<System.Boolean> m_Results`  

## Methods

- `private Check(Unity.Entities.BufferAccessor<Game.Areas.MapFeatureElement> mapFeatureAccessor) : System.Void`  
- `public Execute() : System.Void`  

