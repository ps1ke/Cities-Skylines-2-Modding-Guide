# Game.Net.ReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_EdgeQuery;
    private Unity.Entities.EntityQuery m_NodeQuery;
    private Unity.Entities.EntityQuery m_TempEdgeQuery;
    private Game.Net.ReferencesSystem+TypeHandle __TypeHandle;

    public ReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_EdgeQuery;
```

- `private Unity.Entities.EntityQuery m_NodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_NodeQuery;
```

- `private Unity.Entities.EntityQuery m_TempEdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempEdgeQuery;
```

- `private Game.Net.ReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.ReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ReferencesSystem()`  

```csharp
public ReferencesSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Net.ReferencesSystem+UpdateNodeReferencesJob`  
- `Game.Net.ReferencesSystem+ValidateConnectedNodesJob`  
- `Game.Net.ReferencesSystem+UpdateEdgeReferencesJob`  
- `Game.Net.ReferencesSystem+ConnectedNodeValue`  
- `Game.Net.ReferencesSystem+RationalizeConnectedNodesJob`  
- `Game.Net.ReferencesSystem+AddConnectedNodeReferencesJob`  
- `Game.Net.ReferencesSystem+TypeHandle`  

