# Game.Rendering.Legacy.Plane

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Legacy`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Mathematics.float3 m_Normal`  
- `private System.Single m_Distance`  

## Properties

- `public Unity.Mathematics.float3 normal { get; set }`  
- `public System.Single distance { get; set }`  
- `public Game.Rendering.Legacy.Plane flipped { get }`  

## Constructors

- `public Plane(Unity.Mathematics.float3 inNormal, Unity.Mathematics.float3 inPoint)`  
- `public Plane(Unity.Mathematics.float3 inNormal, System.Single d)`  
- `public Plane(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, Unity.Mathematics.float3 c)`  

## Methods

- `public ClosestPointOnPlane(Unity.Mathematics.float3 point) : Unity.Mathematics.float3`  
- `public Flip() : System.Void`  
- `public GetDistanceToPoint(Unity.Mathematics.float3 point) : System.Single`  
- `public GetSide(Unity.Mathematics.float3 point) : System.Boolean`  
- `public SameSide(Unity.Mathematics.float3 inPt0, Unity.Mathematics.float3 inPt1) : System.Boolean`  
- `public Set3Points(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, Unity.Mathematics.float3 c) : System.Void`  
- `public SetNormalAndPosition(Unity.Mathematics.float3 inNormal, Unity.Mathematics.float3 inPoint) : System.Void`  
- `public virtual ToString() : System.String`  
- `public Translate(Unity.Mathematics.float3 translation) : System.Void`  
- `public static Translate(Game.Rendering.Legacy.Plane plane, Unity.Mathematics.float3 translation) : Game.Rendering.Legacy.Plane`  

