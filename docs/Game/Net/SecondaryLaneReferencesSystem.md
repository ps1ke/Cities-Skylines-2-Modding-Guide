# Game.Net.SecondaryLaneReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SecondaryLaneReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_LanesQuery;
    private Game.Net.SecondaryLaneReferencesSystem+TypeHandle __TypeHandle;

    public SecondaryLaneReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_LanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_LanesQuery;
```

- `private Game.Net.SecondaryLaneReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.SecondaryLaneReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SecondaryLaneReferencesSystem()`  

```csharp
public SecondaryLaneReferencesSystem();
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

- `Game.Net.SecondaryLaneReferencesSystem+UpdateLaneReferencesJob`  
- `Game.Net.SecondaryLaneReferencesSystem+TypeHandle`  

