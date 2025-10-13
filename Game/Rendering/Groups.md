# Game.Rendering.BatchInstanceSystem+Groups

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class Groups : Game.GameSystemBase
{
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    public Colossal.Collections.NativeParallelQueue<Game.Rendering.BatchInstanceSystem+GroupActionData> m_GroupActionQueue;
    public Unity.Collections.NativeQueue<Game.Rendering.BatchInstanceSystem+VelocityData> m_VelocityQueue;
    public Unity.Collections.NativeQueue<Game.Rendering.BatchInstanceSystem+FadeData> m_FadeQueue;
    public Unity.Jobs.JobHandle m_Dependency;
    private Game.Rendering.BatchInstanceSystem+Groups+TypeHandle __TypeHandle;

    public Groups();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `public Colossal.Collections.NativeParallelQueue<Game.Rendering.BatchInstanceSystem+GroupActionData> m_GroupActionQueue`  

```csharp
public Colossal.Collections.NativeParallelQueue<Game.Rendering.BatchInstanceSystem+GroupActionData> m_GroupActionQueue;
```

- `public Unity.Collections.NativeQueue<Game.Rendering.BatchInstanceSystem+VelocityData> m_VelocityQueue`  

```csharp
public Unity.Collections.NativeQueue<Game.Rendering.BatchInstanceSystem+VelocityData> m_VelocityQueue;
```

- `public Unity.Collections.NativeQueue<Game.Rendering.BatchInstanceSystem+FadeData> m_FadeQueue`  

```csharp
public Unity.Collections.NativeQueue<Game.Rendering.BatchInstanceSystem+FadeData> m_FadeQueue;
```

- `public Unity.Jobs.JobHandle m_Dependency`  

```csharp
public Unity.Jobs.JobHandle m_Dependency;
```

- `private Game.Rendering.BatchInstanceSystem+Groups+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.BatchInstanceSystem+Groups+TypeHandle __TypeHandle;
```


## Constructors

- `public Groups()`  

```csharp
public Groups();
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

- `Game.Rendering.BatchInstanceSystem+Groups+TypeHandle`  

