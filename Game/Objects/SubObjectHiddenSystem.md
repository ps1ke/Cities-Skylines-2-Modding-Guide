# Game.Objects.SubObjectHiddenSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SubObjectHiddenSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_HiddenQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Game.Objects.SubObjectHiddenSystem+TypeHandle __TypeHandle;

    public SubObjectHiddenSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_HiddenQuery`  

```csharp
private Unity.Entities.EntityQuery m_HiddenQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Game.Objects.SubObjectHiddenSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.SubObjectHiddenSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SubObjectHiddenSystem()`  

```csharp
public SubObjectHiddenSystem();
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

- `Game.Objects.SubObjectHiddenSystem+FillTempMapJob`  
- `Game.Objects.SubObjectHiddenSystem+HiddenSubObjectJob`  
- `Game.Objects.SubObjectHiddenSystem+TypeHandle`  

