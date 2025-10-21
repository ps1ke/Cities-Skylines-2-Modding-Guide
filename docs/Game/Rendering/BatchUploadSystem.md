# Game.Rendering.BatchUploadSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class BatchUploadSystem : Game.GameSystemBase
{
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;

    public BatchUploadSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```


## Constructors

- `public BatchUploadSystem()`  

```csharp
public BatchUploadSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Rendering.BatchUploadSystem+BatchUploadJob`  

