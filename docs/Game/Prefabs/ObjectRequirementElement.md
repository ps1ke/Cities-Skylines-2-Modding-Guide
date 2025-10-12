# Game.Prefabs.ObjectRequirementElement

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Fields

- `public Unity.Entities.Entity m_Requirement`  
- `public System.UInt16 m_Group`  
- `public Game.Prefabs.ObjectRequirementType m_Type`  
- `public Game.Prefabs.ObjectRequirementFlags m_RequireFlags`  
- `public Game.Prefabs.ObjectRequirementFlags m_ForbidFlags`  

## Constructors

- `public ObjectRequirementElement(Unity.Entities.Entity requirement, System.Int32 group, Game.Prefabs.ObjectRequirementType type = 0)`  
- `public ObjectRequirementElement(Game.Prefabs.ObjectRequirementFlags require, Game.Prefabs.ObjectRequirementFlags forbid, System.Int32 group, Game.Prefabs.ObjectRequirementType type = 0)`  

