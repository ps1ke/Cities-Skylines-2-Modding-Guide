# Game.Serialization.LoadGameSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class LoadGameSystem : Game.GameSystemBase
{
    public Game.Serialization.LoadGameSystem+EventGameLoaded onOnSaveGameLoaded;
    private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_TaskCompletionSource;
    private Colossal.IO.AssetDatabase.AsyncReadDescriptor <dataDescriptor>k__BackingField;
    private Game.UpdateSystem m_UpdateSystem;
    private Colossal.Serialization.Entities.Context m_Context;

    public Colossal.IO.AssetDatabase.AsyncReadDescriptor dataDescriptor { get; set; }
    public Colossal.Serialization.Entities.Context context { get; set; }

    public LoadGameSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Threading.Tasks.Task RunOnce();
}
```


## Fields

- `public Game.Serialization.LoadGameSystem+EventGameLoaded onOnSaveGameLoaded`  

```csharp
public Game.Serialization.LoadGameSystem+EventGameLoaded onOnSaveGameLoaded;
```

- `private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_TaskCompletionSource`  

```csharp
private System.Threading.Tasks.TaskCompletionSource<System.Boolean> m_TaskCompletionSource;
```

- `private Colossal.IO.AssetDatabase.AsyncReadDescriptor <dataDescriptor>k__BackingField`  

```csharp
private Colossal.IO.AssetDatabase.AsyncReadDescriptor <dataDescriptor>k__BackingField;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Colossal.Serialization.Entities.Context m_Context`  

```csharp
private Colossal.Serialization.Entities.Context m_Context;
```


## Properties

- `public Colossal.IO.AssetDatabase.AsyncReadDescriptor dataDescriptor { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.AsyncReadDescriptor dataDescriptor { get; set; }
```

- `public Colossal.Serialization.Entities.Context context { get; set }`  

```csharp
public Colossal.Serialization.Entities.Context context { get; set; }
```


## Constructors

- `public LoadGameSystem()`  

```csharp
public LoadGameSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public RunOnce() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task RunOnce();
```


## Nested types

- `Game.Serialization.LoadGameSystem+EventGameLoaded`  
- `Game.Serialization.LoadGameSystem+<RunOnce>d__13`  

