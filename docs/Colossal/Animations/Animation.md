# Colossal.Animations.Animation

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Animations`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `Serializable`  

## Fields

- `public System.String name`  
- `public Colossal.Animations.AnimationType type`  
- `public Colossal.Animations.AnimationLayer layer`  
- `public System.Int32[] shapeIndices`  
- `public System.Int32[] boneIndices`  
- `public System.Int32 frameCount`  
- `public System.Int32 frameRate`  
- `public Unity.Mathematics.float3 positionMin`  
- `public Unity.Mathematics.float3 positionRange`  
- `public Colossal.Animations.Animation+Element[] elements`  
- `public System.Int32 elementsDiskDataSize`  

## Methods

- `public DecodeElement(System.Int32 index) : Colossal.Animations.Animation+ElementRaw`  
- `public SetElements(System.ReadOnlySpan<Colossal.Animations.Animation+ElementRaw> input) : System.Void`  

## Nested types

- `Colossal.Animations.Animation+Element`  
- `Colossal.Animations.Animation+ElementRaw`  

