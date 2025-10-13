# Game.Audio.Radio.Radio+ClipInfo

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ClipInfo
{
    public Colossal.IO.AssetDatabase.AudioAsset m_Asset;
    public Game.Audio.Radio.Radio+SegmentType m_SegmentType;
    public Unity.Entities.Entity m_Emergency;
    public Unity.Entities.Entity m_EmergencyTarget;
    public System.Threading.Tasks.Task<UnityEngine.AudioClip> m_LoadTask;
    public System.Int32 m_ResumeAtPosition;
    public System.Boolean m_Replaying;

}
```


## Fields

- `public Colossal.IO.AssetDatabase.AudioAsset m_Asset`  

```csharp
public Colossal.IO.AssetDatabase.AudioAsset m_Asset;
```

- `public Game.Audio.Radio.Radio+SegmentType m_SegmentType`  

```csharp
public Game.Audio.Radio.Radio+SegmentType m_SegmentType;
```

- `public Unity.Entities.Entity m_Emergency`  

```csharp
public Unity.Entities.Entity m_Emergency;
```

- `public Unity.Entities.Entity m_EmergencyTarget`  

```csharp
public Unity.Entities.Entity m_EmergencyTarget;
```

- `public System.Threading.Tasks.Task<UnityEngine.AudioClip> m_LoadTask`  

```csharp
public System.Threading.Tasks.Task<UnityEngine.AudioClip> m_LoadTask;
```

- `public System.Int32 m_ResumeAtPosition`  

```csharp
public System.Int32 m_ResumeAtPosition;
```

- `public System.Boolean m_Replaying`  

```csharp
public System.Boolean m_Replaying;
```


