# Game.UI.InGame.PollutionSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PollutionSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.PollutionThreshold <groundPollutionKey>k__BackingField;
    private Game.UI.InGame.PollutionThreshold <airPollutionKey>k__BackingField;
    private Game.UI.InGame.PollutionThreshold <noisePollutionKey>k__BackingField;
    private Unity.Entities.EntityQuery m_UIConfigQuery;
    private Game.UI.InGame.PollutionSection+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1774369403_0;
    private Unity.Entities.EntityQuery __query_1774369403_1;

    protected System.String group { protected get; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    private Game.UI.InGame.PollutionThreshold groundPollutionKey { private get; private set; }
    private Game.UI.InGame.PollutionThreshold airPollutionKey { private get; private set; }
    private Game.UI.InGame.PollutionThreshold noisePollutionKey { private get; private set; }

    public PollutionSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Game.Prefabs.PollutionData GetPollution();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.UI.InGame.PollutionThreshold <groundPollutionKey>k__BackingField`  

```csharp
private Game.UI.InGame.PollutionThreshold <groundPollutionKey>k__BackingField;
```

- `private Game.UI.InGame.PollutionThreshold <airPollutionKey>k__BackingField`  

```csharp
private Game.UI.InGame.PollutionThreshold <airPollutionKey>k__BackingField;
```

- `private Game.UI.InGame.PollutionThreshold <noisePollutionKey>k__BackingField`  

```csharp
private Game.UI.InGame.PollutionThreshold <noisePollutionKey>k__BackingField;
```

- `private Unity.Entities.EntityQuery m_UIConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_UIConfigQuery;
```

- `private Game.UI.InGame.PollutionSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.PollutionSection+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1774369403_0`  

```csharp
private Unity.Entities.EntityQuery __query_1774369403_0;
```

- `private Unity.Entities.EntityQuery __query_1774369403_1`  

```csharp
private Unity.Entities.EntityQuery __query_1774369403_1;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```

- `private Game.UI.InGame.PollutionThreshold groundPollutionKey { private get; private set }`  

```csharp
private Game.UI.InGame.PollutionThreshold groundPollutionKey { private get; private set; }
```

- `private Game.UI.InGame.PollutionThreshold airPollutionKey { private get; private set }`  

```csharp
private Game.UI.InGame.PollutionThreshold airPollutionKey { private get; private set; }
```

- `private Game.UI.InGame.PollutionThreshold noisePollutionKey { private get; private set }`  

```csharp
private Game.UI.InGame.PollutionThreshold noisePollutionKey { private get; private set; }
```


## Constructors

- `public PollutionSection()`  

```csharp
public PollutionSection();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetPollution() : Game.Prefabs.PollutionData`  

```csharp
private Game.Prefabs.PollutionData GetPollution();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
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

- `private Visible() : System.Boolean`  

```csharp
private System.Boolean Visible();
```


## Nested types

- `Game.UI.InGame.PollutionSection+TypeHandle`  

