# Game.Audio.Radio.Radio+RuntimeRadioChannel

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IComparable<Game.Audio.Radio.Radio+RuntimeRadioChannel>`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class RuntimeRadioChannel : System.IComparable<Game.Audio.Radio.Radio+RuntimeRadioChannel>, Colossal.UI.Binding.IJsonWritable
{
    public System.String name;
    public System.String description;
    public System.String icon;
    public System.Int32 uiPriority;
    public System.String network;
    private Game.Audio.Radio.Radio+RuntimeProgram <currentProgram>k__BackingField;
    private Game.Audio.Radio.Radio+RuntimeProgram[] <schedule>k__BackingField;
    private readonly Game.Audio.Radio.Radio+RuntimeProgram kNoProgram;

    public Game.Audio.Radio.Radio+RuntimeProgram currentProgram { get; private set; }
    public Game.Audio.Radio.Radio+RuntimeProgram[] schedule { get; private set; }

    public RuntimeRadioChannel();

    private System.Void AddRuntimeProgram(Game.Audio.Radio.Radio+Program p, System.Int32 startSecs, System.Int32 endSecs, System.Collections.Generic.List<Game.Audio.Radio.Radio+RuntimeProgram> schedule, System.String path);
    private System.Void BuildRuntimePrograms(Game.Audio.Radio.Radio+Program[] programs, System.String path);
    public System.Int32 CompareTo(Game.Audio.Radio.Radio+RuntimeRadioChannel other);
    private Game.Audio.Radio.Radio+RuntimeProgram CreateRuntimeProgram(Game.Audio.Radio.Radio+Program p, System.Int32 startSecs, System.Int32 endSecs, System.String path);
    public System.Void Initialize(Game.Audio.Radio.Radio+RadioChannel radioChannel, System.String path);
    private System.Boolean IsValidTimestamp(System.Int32 start, System.Int32 end);
    private Game.Audio.Radio.Radio+RuntimeProgram ShallowCopyRuntimeProgram(Game.Audio.Radio.Radio+RuntimeProgram p, System.Int32 startSecs, System.Int32 endSecs);
    public System.Boolean Update(System.Int32 timeOfDaySeconds);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.String name`  

```csharp
public System.String name;
```

- `public System.String description`  

```csharp
public System.String description;
```

- `public System.String icon`  

```csharp
public System.String icon;
```

- `public System.Int32 uiPriority`  

```csharp
public System.Int32 uiPriority;
```

- `public System.String network`  

```csharp
public System.String network;
```

- `private Game.Audio.Radio.Radio+RuntimeProgram <currentProgram>k__BackingField`  

```csharp
private Game.Audio.Radio.Radio+RuntimeProgram <currentProgram>k__BackingField;
```

- `private Game.Audio.Radio.Radio+RuntimeProgram[] <schedule>k__BackingField`  

```csharp
private Game.Audio.Radio.Radio+RuntimeProgram[] <schedule>k__BackingField;
```

- `private readonly Game.Audio.Radio.Radio+RuntimeProgram kNoProgram`  

```csharp
private readonly Game.Audio.Radio.Radio+RuntimeProgram kNoProgram;
```


## Properties

- `public Game.Audio.Radio.Radio+RuntimeProgram currentProgram { get; private set }`  

```csharp
public Game.Audio.Radio.Radio+RuntimeProgram currentProgram { get; private set; }
```

- `public Game.Audio.Radio.Radio+RuntimeProgram[] schedule { get; private set }`  

```csharp
public Game.Audio.Radio.Radio+RuntimeProgram[] schedule { get; private set; }
```


## Constructors

- `public RuntimeRadioChannel()`  

```csharp
public RuntimeRadioChannel();
```


## Methods

- `private AddRuntimeProgram(Game.Audio.Radio.Radio+Program p, System.Int32 startSecs, System.Int32 endSecs, System.Collections.Generic.List<Game.Audio.Radio.Radio+RuntimeProgram> schedule, System.String path) : System.Void`  

```csharp
private System.Void AddRuntimeProgram(Game.Audio.Radio.Radio+Program p, System.Int32 startSecs, System.Int32 endSecs, System.Collections.Generic.List<Game.Audio.Radio.Radio+RuntimeProgram> schedule, System.String path);
```

- `private BuildRuntimePrograms(Game.Audio.Radio.Radio+Program[] programs, System.String path) : System.Void`  

```csharp
private System.Void BuildRuntimePrograms(Game.Audio.Radio.Radio+Program[] programs, System.String path);
```

- `public CompareTo(Game.Audio.Radio.Radio+RuntimeRadioChannel other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Audio.Radio.Radio+RuntimeRadioChannel other);
```

- `private CreateRuntimeProgram(Game.Audio.Radio.Radio+Program p, System.Int32 startSecs, System.Int32 endSecs, System.String path) : Game.Audio.Radio.Radio+RuntimeProgram`  

```csharp
private Game.Audio.Radio.Radio+RuntimeProgram CreateRuntimeProgram(Game.Audio.Radio.Radio+Program p, System.Int32 startSecs, System.Int32 endSecs, System.String path);
```

- `public Initialize(Game.Audio.Radio.Radio+RadioChannel radioChannel, System.String path) : System.Void`  

```csharp
public System.Void Initialize(Game.Audio.Radio.Radio+RadioChannel radioChannel, System.String path);
```

- `private IsValidTimestamp(System.Int32 start, System.Int32 end) : System.Boolean`  

```csharp
private System.Boolean IsValidTimestamp(System.Int32 start, System.Int32 end);
```

- `private ShallowCopyRuntimeProgram(Game.Audio.Radio.Radio+RuntimeProgram p, System.Int32 startSecs, System.Int32 endSecs) : Game.Audio.Radio.Radio+RuntimeProgram`  

```csharp
private Game.Audio.Radio.Radio+RuntimeProgram ShallowCopyRuntimeProgram(Game.Audio.Radio.Radio+RuntimeProgram p, System.Int32 startSecs, System.Int32 endSecs);
```

- `public Update(System.Int32 timeOfDaySeconds) : System.Boolean`  

```csharp
public System.Boolean Update(System.Int32 timeOfDaySeconds);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


