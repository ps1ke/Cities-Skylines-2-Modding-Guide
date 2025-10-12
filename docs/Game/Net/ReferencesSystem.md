# Game.Net.ReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_EdgeQuery`  
- `private Unity.Entities.EntityQuery m_NodeQuery`  
- `private Unity.Entities.EntityQuery m_TempEdgeQuery`  
- `private Game.Net.ReferencesSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ReferencesSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Net.ReferencesSystem+UpdateNodeReferencesJob`  
- `Game.Net.ReferencesSystem+ValidateConnectedNodesJob`  
- `Game.Net.ReferencesSystem+UpdateEdgeReferencesJob`  
- `Game.Net.ReferencesSystem+ConnectedNodeValue`  
- `Game.Net.ReferencesSystem+RationalizeConnectedNodesJob`  
- `Game.Net.ReferencesSystem+AddConnectedNodeReferencesJob`  
- `Game.Net.ReferencesSystem+TypeHandle`  

