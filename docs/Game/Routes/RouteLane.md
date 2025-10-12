# Game.Routes.RouteLane

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `System.IEquatable<Game.Routes.RouteLane>`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_StartLane`  
- `public Unity.Entities.Entity m_EndLane`  
- `public System.Single m_StartCurvePos`  
- `public System.Single m_EndCurvePos`  

## Constructors

- `public RouteLane(Unity.Entities.Entity startLane, Unity.Entities.Entity endLane, System.Single startCurvePos, System.Single endCurvePos)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Equals(Game.Routes.RouteLane other) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

