# Game.Net.LaneObjectAction

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Net.LaneObjectAction>`  

## Fields

- `public Unity.Entities.Entity m_Lane`  
- `public Unity.Entities.Entity m_Remove`  
- `public Unity.Entities.Entity m_Add`  
- `public Unity.Mathematics.float2 m_CurvePosition`  

## Constructors

- `public LaneObjectAction(Unity.Entities.Entity lane, Unity.Entities.Entity remove)`  
- `public LaneObjectAction(Unity.Entities.Entity lane, Unity.Entities.Entity add, Unity.Mathematics.float2 curvePosition)`  
- `public LaneObjectAction(Unity.Entities.Entity lane, Unity.Entities.Entity remove, Unity.Entities.Entity add, Unity.Mathematics.float2 curvePosition)`  

## Methods

- `public CompareTo(Game.Net.LaneObjectAction other) : System.Int32`  
- `public virtual GetHashCode() : System.Int32`  

