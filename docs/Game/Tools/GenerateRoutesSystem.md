# Game.Tools.GenerateRoutesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GenerateRoutesSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier2 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_SubElementQuery;
    private Game.Tools.GenerateRoutesSystem+TypeHandle __TypeHandle;

    public GenerateRoutesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier2 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_SubElementQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubElementQuery;
```

- `private Game.Tools.GenerateRoutesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.GenerateRoutesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GenerateRoutesSystem()`  

```csharp
public GenerateRoutesSystem();
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

- `Game.Tools.GenerateRoutesSystem+CreateRoutesJob`  
- `Game.Tools.GenerateRoutesSystem+TypeHandle`  

