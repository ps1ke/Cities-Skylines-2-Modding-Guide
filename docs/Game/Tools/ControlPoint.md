# Game.Tools.ControlPoint

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Tools.ControlPoint>`  

## Fields

- `public Unity.Mathematics.float3 m_Position`  
- `public Unity.Mathematics.float3 m_HitPosition`  
- `public Unity.Mathematics.float2 m_Direction`  
- `public Unity.Mathematics.float3 m_HitDirection`  
- `public Unity.Mathematics.quaternion m_Rotation`  
- `public Unity.Entities.Entity m_OriginalEntity`  
- `public Unity.Mathematics.float2 m_SnapPriority`  
- `public Unity.Mathematics.int2 m_ElementIndex`  
- `public System.Single m_CurvePosition`  
- `public System.Single m_Elevation`  

## Constructors

- `public ControlPoint(Unity.Entities.Entity raycastEntity, Game.Common.RaycastHit raycastHit)`  

## Methods

- `public Equals(Game.Tools.ControlPoint other) : System.Boolean`  
- `public EqualsIgnoreHit(Game.Tools.ControlPoint other) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  

