# Game.Audio.Radio.Radio+RuntimeSegment

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class RuntimeSegment
{
    public Game.Audio.Radio.Radio+SegmentType type;
    public System.String[] tags;
    public System.Int32 clipsCap;
    private System.Int32 m_CapCount;
    private System.Int32 m_CurrentClipId;
    private System.Boolean <isSetUp>k__BackingField;
    private System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AudioAsset> m_Clips;
    private System.Double <durationMs>k__BackingField;

    public Colossal.IO.AssetDatabase.AudioAsset currentClip { get; }
    public System.Boolean isSetUp { get; private set; }
    public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AudioAsset> clips { get; set; }
    public System.Double durationMs { get; private set; }

    public RuntimeSegment();

    public System.Boolean GoToNextClip();
    public System.Boolean GoToPreviousClip();
    public System.Void Reset();
    public System.Void Setup(Game.Audio.Radio.Radio+OnDemandClips clipsCallback);
}
```


## Fields

- `public Game.Audio.Radio.Radio+SegmentType type`  

```csharp
public Game.Audio.Radio.Radio+SegmentType type;
```

- `public System.String[] tags`  

```csharp
public System.String[] tags;
```

- `public System.Int32 clipsCap`  

```csharp
public System.Int32 clipsCap;
```

- `private System.Int32 m_CapCount`  

```csharp
private System.Int32 m_CapCount;
```

- `private System.Int32 m_CurrentClipId`  

```csharp
private System.Int32 m_CurrentClipId;
```

- `private System.Boolean <isSetUp>k__BackingField`  

```csharp
private System.Boolean <isSetUp>k__BackingField;
```

- `private System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AudioAsset> m_Clips`  

```csharp
private System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AudioAsset> m_Clips;
```

- `private System.Double <durationMs>k__BackingField`  

```csharp
private System.Double <durationMs>k__BackingField;
```


## Properties

- `public Colossal.IO.AssetDatabase.AudioAsset currentClip { get }`  

```csharp
public Colossal.IO.AssetDatabase.AudioAsset currentClip { get; }
```

- `public System.Boolean isSetUp { get; private set }`  

```csharp
public System.Boolean isSetUp { get; private set; }
```

- `public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AudioAsset> clips { get; set }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AudioAsset> clips { get; set; }
```

- `public System.Double durationMs { get; private set }`  

```csharp
public System.Double durationMs { get; private set; }
```


## Constructors

- `public RuntimeSegment()`  

```csharp
public RuntimeSegment();
```


## Methods

- `public GoToNextClip() : System.Boolean`  

```csharp
public System.Boolean GoToNextClip();
```

- `public GoToPreviousClip() : System.Boolean`  

```csharp
public System.Boolean GoToPreviousClip();
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```

- `public Setup(Game.Audio.Radio.Radio+OnDemandClips clipsCallback = null) : System.Void`  

```csharp
public System.Void Setup(Game.Audio.Radio.Radio+OnDemandClips clipsCallback);
```


