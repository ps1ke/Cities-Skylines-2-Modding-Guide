# Game.Net.NodeAlignSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NodeAlignSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_NodeQuery;
    private Game.Net.NodeAlignSystem+TypeHandle __TypeHandle;

    public NodeAlignSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_NodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_NodeQuery;
```

- `private Game.Net.NodeAlignSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.NodeAlignSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NodeAlignSystem()`  

```csharp
public NodeAlignSystem();
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

- `Game.Net.NodeAlignSystem+UpdateNodeRotationsJob`  
- `Game.Net.NodeAlignSystem+LineComparer`  
- `Game.Net.NodeAlignSystem+TypeHandle`  

