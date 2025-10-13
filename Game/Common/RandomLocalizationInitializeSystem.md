# Game.Common.RandomLocalizationInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RandomLocalizationInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Game.Common.RandomLocalizationInitializeSystem+TypeHandle __TypeHandle;

    public RandomLocalizationInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Game.Common.RandomLocalizationInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Common.RandomLocalizationInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RandomLocalizationInitializeSystem()`  

```csharp
public RandomLocalizationInitializeSystem();
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

- `Game.Common.RandomLocalizationInitializeSystem+InitializeLocalizationJob`  
- `Game.Common.RandomLocalizationInitializeSystem+TypeHandle`  

