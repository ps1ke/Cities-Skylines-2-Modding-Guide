# Game.Rendering.InterpolatedTransform

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IEmptySerializable`  

## Fields

- `public Unity.Mathematics.float3 m_Position`  
- `public Unity.Mathematics.quaternion m_Rotation`  
- `public Game.Objects.TransformFlags m_Flags`  

## Constructors

- `public InterpolatedTransform(Game.Objects.Transform transform)`  
- `public InterpolatedTransform(Game.Events.WeatherPhenomenon weatherPhenomenon)`  

## Methods

- `public ToTransform() : Game.Objects.Transform`  

