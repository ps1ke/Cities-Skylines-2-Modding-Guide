# Game.Tools.GenerateNotificationsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GenerateNotificationsSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityArchetype m_DefaultArchetype;
    private Game.Tools.GenerateNotificationsSystem+TypeHandle __TypeHandle;

    public GenerateNotificationsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier1 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityArchetype m_DefaultArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DefaultArchetype;
```

- `private Game.Tools.GenerateNotificationsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.GenerateNotificationsSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GenerateNotificationsSystem()`  

```csharp
public GenerateNotificationsSystem();
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

- `Game.Tools.GenerateNotificationsSystem+GenerateIconsJob`  
- `Game.Tools.GenerateNotificationsSystem+TypeHandle`  

