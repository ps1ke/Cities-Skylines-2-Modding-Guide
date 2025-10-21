# Game.UI.InGame.ScheduleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ScheduleSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
    private Unity.Entities.Entity m_NightRoutePolicy;
    private Unity.Entities.Entity m_DayRoutePolicy;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Game.UI.InGame.RouteSchedule <schedule>k__BackingField;

    protected System.String group { protected get; }
    private Game.UI.InGame.RouteSchedule schedule { private get; private set; }

    public ScheduleSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnProcess();
    private System.Void OnSetSchedule(System.Int32 newSchedule);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  

```csharp
private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
```

- `private Unity.Entities.Entity m_NightRoutePolicy`  

```csharp
private Unity.Entities.Entity m_NightRoutePolicy;
```

- `private Unity.Entities.Entity m_DayRoutePolicy`  

```csharp
private Unity.Entities.Entity m_DayRoutePolicy;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Game.UI.InGame.RouteSchedule <schedule>k__BackingField`  

```csharp
private Game.UI.InGame.RouteSchedule <schedule>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.UI.InGame.RouteSchedule schedule { private get; private set }`  

```csharp
private Game.UI.InGame.RouteSchedule schedule { private get; private set; }
```


## Constructors

- `public ScheduleSection()`  

```csharp
public ScheduleSection();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
```

- `private OnSetSchedule(System.Int32 newSchedule) : System.Void`  

```csharp
private System.Void OnSetSchedule(System.Int32 newSchedule);
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


