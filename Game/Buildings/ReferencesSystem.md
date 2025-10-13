# Game.Buildings.ReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_SpawnLocationQuery;
    private Game.Buildings.ReferencesSystem+TypeHandle __TypeHandle;

    public ReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_SpawnLocationQuery`  

```csharp
private Unity.Entities.EntityQuery m_SpawnLocationQuery;
```

- `private Game.Buildings.ReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.ReferencesSystem+TypeHandle __TypeHandle;
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

- `Game.Buildings.ReferencesSystem+UpdateBuildingReferencesJob`  
- `Game.Buildings.ReferencesSystem+TypeHandle`  

