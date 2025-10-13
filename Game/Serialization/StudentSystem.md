# Game.Serialization.StudentSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StudentSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_StudentQuery;
    private Game.Serialization.StudentSystem+TypeHandle __TypeHandle;

    public StudentSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_StudentQuery`  

```csharp
private Unity.Entities.EntityQuery m_StudentQuery;
```

- `private Game.Serialization.StudentSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.StudentSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public StudentSystem()`  

```csharp
public StudentSystem();
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

- `Game.Serialization.StudentSystem+StudentJob`  
- `Game.Serialization.StudentSystem+TypeHandle`  

