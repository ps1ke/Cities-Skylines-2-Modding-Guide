# Game.Debug.BaseDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class abstract public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public abstract class BaseDebugSystem : Game.GameSystemBase
{
    private System.Collections.Generic.List<Game.Debug.BaseDebugSystem+Option> <options>k__BackingField;

    public System.Collections.Generic.List<Game.Debug.BaseDebugSystem+Option> options { get; private set; }

    protected BaseDebugSystem();

    protected Game.Debug.BaseDebugSystem+Option AddOption(System.String displayName, System.Boolean defaultEnabled);
    protected virtual System.Void OnCreate();
    public virtual System.Void OnDisabled(UnityEngine.Rendering.DebugUI+Container container);
    public virtual System.Void OnEnabled(UnityEngine.Rendering.DebugUI+Container container);
    protected virtual System.Void OnUpdate();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private System.Collections.Generic.List<Game.Debug.BaseDebugSystem+Option> <options>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.Debug.BaseDebugSystem+Option> <options>k__BackingField;
```


## Properties

- `public System.Collections.Generic.List<Game.Debug.BaseDebugSystem+Option> options { get; private set }`  

```csharp
public System.Collections.Generic.List<Game.Debug.BaseDebugSystem+Option> options { get; private set; }
```


## Constructors

- `protected BaseDebugSystem()`  

```csharp
protected BaseDebugSystem();
```


## Methods

- `protected AddOption(System.String displayName, System.Boolean defaultEnabled) : Game.Debug.BaseDebugSystem+Option`  

```csharp
protected Game.Debug.BaseDebugSystem+Option AddOption(System.String displayName, System.Boolean defaultEnabled);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `public virtual OnDisabled(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
public virtual System.Void OnDisabled(UnityEngine.Rendering.DebugUI+Container container);
```

- `public virtual OnEnabled(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
public virtual System.Void OnEnabled(UnityEngine.Rendering.DebugUI+Container container);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Debug.BaseDebugSystem+Option`  

