# Game.UI.InGame.LinesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LinesSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.TransportationOverviewUISystem m_TransportationOverviewUISystem;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <lines>k__BackingField;
    private Unity.Collections.NativeArray<System.Boolean> m_BoolResult;
    private Unity.Collections.NativeArray<System.Int32> m_PassengersResult;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_LinesResult;
    private Game.UI.InGame.LinesSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    protected System.Boolean displayForOutsideConnections { protected get; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> lines { private get; private set; }

    public LinesSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    private System.Void OnToggle(Unity.Entities.Entity entity, System.Boolean state);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private Game.UI.InGame.TransportationOverviewUISystem m_TransportationOverviewUISystem`  

```csharp
private Game.UI.InGame.TransportationOverviewUISystem m_TransportationOverviewUISystem;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <lines>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <lines>k__BackingField;
```

- `private Unity.Collections.NativeArray<System.Boolean> m_BoolResult`  

```csharp
private Unity.Collections.NativeArray<System.Boolean> m_BoolResult;
```

- `private Unity.Collections.NativeArray<System.Int32> m_PassengersResult`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_PassengersResult;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_LinesResult`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_LinesResult;
```

- `private Game.UI.InGame.LinesSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.LinesSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `protected System.Boolean displayForOutsideConnections { protected get }`  

```csharp
protected System.Boolean displayForOutsideConnections { protected get; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> lines { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> lines { private get; private set; }
```


## Constructors

- `public LinesSection()`  

```csharp
public LinesSection();
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
```

- `private OnToggle(Unity.Entities.Entity entity, System.Boolean state) : System.Void`  

```csharp
private System.Void OnToggle(Unity.Entities.Entity entity, System.Boolean state);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```

- `protected virtual Reset() : System.Void`  

```csharp
protected virtual System.Void Reset();
```


## Nested types

- `Game.UI.InGame.LinesSection+Result`  
- `Game.UI.InGame.LinesSection+LinesJob`  
- `Game.UI.InGame.LinesSection+TypeHandle`  

