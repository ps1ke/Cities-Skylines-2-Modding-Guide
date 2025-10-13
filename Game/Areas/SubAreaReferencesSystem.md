# Game.Areas.SubAreaReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SubAreaReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_SubAreaQuery;
    private Game.Areas.SubAreaReferencesSystem+TypeHandle __TypeHandle;

    public SubAreaReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_SubAreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubAreaQuery;
```

- `private Game.Areas.SubAreaReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.SubAreaReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SubAreaReferencesSystem()`  

```csharp
public SubAreaReferencesSystem();
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

- `Game.Areas.SubAreaReferencesSystem+UpdateSubAreaReferencesJob`  
- `Game.Areas.SubAreaReferencesSystem+TypeHandle`  

