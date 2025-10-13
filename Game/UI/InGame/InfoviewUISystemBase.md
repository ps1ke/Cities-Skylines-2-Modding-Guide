# Game.UI.InGame.InfoviewUISystemBase

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Code

```csharp
public abstract class InfoviewUISystemBase : Game.UI.UISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.UI.UIUpdateState m_UpdateState;
    private System.Boolean m_Clear;

    public Game.GameMode gameMode { get; }
    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    protected InfoviewUISystemBase();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    protected abstract System.Void PerformUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void RequestUpdate();
    protected System.Void ResetResults<T>(Unity.Collections.NativeArray<T> results);
}
```


## Fields

- `private Game.UI.UIUpdateState m_UpdateState`  

```csharp
private Game.UI.UIUpdateState m_UpdateState;
```

- `private System.Boolean m_Clear`  

```csharp
private System.Boolean m_Clear;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```

- `protected System.Boolean Modified { protected get }`  

```csharp
protected System.Boolean Modified { protected get; }
```


## Constructors

- `protected InfoviewUISystemBase()`  

```csharp
protected InfoviewUISystemBase();
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

- `protected abstract PerformUpdate() : System.Void`  

```csharp
protected abstract System.Void PerformUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `public RequestUpdate() : System.Void`  

```csharp
public System.Void RequestUpdate();
```

- `protected ResetResults<T>(Unity.Collections.NativeArray<T> results) : System.Void`  

```csharp
protected System.Void ResetResults<T>(Unity.Collections.NativeArray<T> results);
```


