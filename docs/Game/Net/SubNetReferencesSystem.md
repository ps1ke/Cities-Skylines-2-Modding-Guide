# Game.Net.SubNetReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SubNetReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_SubNetQuery;
    private Game.Net.SubNetReferencesSystem+TypeHandle __TypeHandle;

    public SubNetReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_SubNetQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubNetQuery;
```

- `private Game.Net.SubNetReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.SubNetReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SubNetReferencesSystem()`  

```csharp
public SubNetReferencesSystem();
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

- `Game.Net.SubNetReferencesSystem+UpdateSubNetReferencesJob`  
- `Game.Net.SubNetReferencesSystem+TypeHandle`  

