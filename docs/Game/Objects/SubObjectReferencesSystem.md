# Game.Objects.SubObjectReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SubObjectReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ObjectQuery;
    private Game.Objects.SubObjectReferencesSystem+TypeHandle __TypeHandle;

    public SubObjectReferencesSystem();

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

- `private Game.Objects.SubObjectReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.SubObjectReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SubObjectReferencesSystem()`  

```csharp
public SubObjectReferencesSystem();
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

- `Game.Objects.SubObjectReferencesSystem+UpdateSubObjectReferencesJob`  
- `Game.Objects.SubObjectReferencesSystem+TypeHandle`  

