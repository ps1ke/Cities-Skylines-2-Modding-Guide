# Game.Simulation.UpdateGroupSystem+UpdateGroupSizes

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Collections.NativeArray<System.Int32> m_MovingObjectUpdateGroupSizes`  
- `private Unity.Collections.NativeArray<System.Int32> m_TreeUpdateGroupSizes`  
- `private Unity.Collections.NativeArray<System.Int32> m_BuildingUpdateGroupSizes`  
- `private Unity.Collections.NativeArray<System.Int32> m_NetUpdateGroupSizes`  
- `private Unity.Collections.NativeArray<System.Int32> m_LaneUpdateGroupSizes`  
- `private Unity.Collections.NativeArray<System.Int32> m_CompanyUpdateGroupSizes`  
- `private Unity.Collections.NativeArray<System.Int32> m_HouseholdUpdateGroupSizes`  
- `private Unity.Collections.NativeArray<System.Int32> m_CitizenUpdateGroupSizes`  
- `private Unity.Collections.NativeArray<System.Int32> m_HouseholdPetUpdateGroupSizes`  

## Constructors

- `public UpdateGroupSizes(Unity.Collections.Allocator allocator)`  

## Methods

- `public Clear() : System.Void`  
- `public Dispose() : System.Void`  
- `public Get(Unity.Entities.ArchetypeChunk chunk, Game.Simulation.UpdateGroupSystem+UpdateGroupTypes types) : Unity.Collections.NativeArray<System.Int32>`  

