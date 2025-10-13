# Game.Audio.Radio.Radio+RuntimeProgram

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class RuntimeProgram : Colossal.UI.Binding.IJsonWritable
{
    public System.String name;
    public System.String description;
    public System.Int32 startTime;
    public System.Int32 endTime;
    public System.Boolean loopProgram;
    public System.Boolean active;
    public System.Boolean hasEnded;
    private System.Int32 m_CurrentSegmentId;
    private System.Collections.Generic.List<Game.Audio.Radio.Radio+RuntimeSegment> m_Segments;

    public System.Int32 duration { get; }
    public Game.Audio.Radio.Radio+RuntimeSegment currentSegment { get; }
    public System.Collections.Generic.IReadOnlyList<Game.Audio.Radio.Radio+RuntimeSegment> segments { get; set; }

    public RuntimeProgram();

    public System.Void BuildRuntimeSegments(Game.Audio.Radio.Radio+Program program, System.String path);
    private Colossal.IO.AssetDatabase.AudioAsset[] GetClips(System.Int32 count, System.Func<System.Int32, System.Int32> rand, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AudioAsset> clips);
    public System.Boolean GoToNextSegment();
    public System.Void Reset();
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

- `public System.Int32 startTime`  

```csharp
public System.Int32 startTime;
```

- `public System.Int32 endTime`  

```csharp
public System.Int32 endTime;
```

- `public System.Boolean loopProgram`  

```csharp
public System.Boolean loopProgram;
```

- `public System.Boolean active`  

```csharp
public System.Boolean active;
```

- `public System.Boolean hasEnded`  

```csharp
public System.Boolean hasEnded;
```

- `private System.Int32 m_CurrentSegmentId`  

```csharp
private System.Int32 m_CurrentSegmentId;
```

- `private System.Collections.Generic.List<Game.Audio.Radio.Radio+RuntimeSegment> m_Segments`  

```csharp
private System.Collections.Generic.List<Game.Audio.Radio.Radio+RuntimeSegment> m_Segments;
```


## Properties

- `public System.Int32 duration { get }`  

```csharp
public System.Int32 duration { get; }
```

- `public Game.Audio.Radio.Radio+RuntimeSegment currentSegment { get }`  

```csharp
public Game.Audio.Radio.Radio+RuntimeSegment currentSegment { get; }
```

- `public System.Collections.Generic.IReadOnlyList<Game.Audio.Radio.Radio+RuntimeSegment> segments { get; set }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Audio.Radio.Radio+RuntimeSegment> segments { get; set; }
```


## Constructors

- `public RuntimeProgram()`  

```csharp
public RuntimeProgram();
```


## Methods

- `public BuildRuntimeSegments(Game.Audio.Radio.Radio+Program program, System.String path) : System.Void`  

```csharp
public System.Void BuildRuntimeSegments(Game.Audio.Radio.Radio+Program program, System.String path);
```

- `private GetClips(System.Int32 count, System.Func<System.Int32, System.Int32> rand, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AudioAsset> clips) : Colossal.IO.AssetDatabase.AudioAsset[]`  

```csharp
private Colossal.IO.AssetDatabase.AudioAsset[] GetClips(System.Int32 count, System.Func<System.Int32, System.Int32> rand, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AudioAsset> clips);
```

- `public GoToNextSegment() : System.Boolean`  

```csharp
public System.Boolean GoToNextSegment();
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.Audio.Radio.Radio+RuntimeProgram+<>c`  
- `Game.Audio.Radio.Radio+RuntimeProgram+<>c__DisplayClass19_0`  
- `Game.Audio.Radio.Radio+RuntimeProgram+<>c__DisplayClass19_1`  

