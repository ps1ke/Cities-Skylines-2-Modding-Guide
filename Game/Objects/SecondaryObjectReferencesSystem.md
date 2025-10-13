# Game.Objects.SecondaryObjectReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SecondaryObjectReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ObjectQuery;
    private Game.Objects.SecondaryObjectReferencesSystem+TypeHandle __TypeHandle;

    public SecondaryObjectReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectQuery;
```

- `private Game.Objects.SecondaryObjectReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.SecondaryObjectReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SecondaryObjectReferencesSystem()`  

```csharp
public SecondaryObjectReferencesSystem();
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

- `Game.Objects.SecondaryObjectReferencesSystem+UpdateSecondaryObjectReferencesJob`  
- `Game.Objects.SecondaryObjectReferencesSystem+TypeHandle`  

