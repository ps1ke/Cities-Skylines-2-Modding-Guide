# Game.Audio.AudioManager+AudioSourcePool

**Assembly:** `Game`  
**Namespace:** `Game.Audio`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class AudioSourcePool
{
    private static System.Int32 s_InstanceCount;
    private static System.Int32 s_LoadedSize;
    private static System.Int32 s_PlayingSize;
    private static System.Int32 s_MaxLoadedSize;
    private static System.Collections.Generic.Stack<UnityEngine.AudioSource> s_Pool;
    private static System.Collections.Generic.Dictionary<UnityEngine.AudioClip, System.Int32> s_PlayingClips;
    private static System.Collections.Generic.List<UnityEngine.AudioClip> s_UnloadClips;

    public static System.Int32 memoryBudget { get; set; }

    internal static UnityEngine.AudioSource <Get>g__CreateAudioSource|12_0();
    private static System.Void AddClip(UnityEngine.AudioClip audioClip);
    public static UnityEngine.AudioSource Get();
    private static System.Int32 GetClipSize(UnityEngine.AudioClip audioClip);
    public static System.Void Play(UnityEngine.AudioSource audioSource);
    public static System.Void PlayDelayed(UnityEngine.AudioSource audioSource, System.Single delay);
    public static System.Void Release(UnityEngine.AudioSource audioSource);
    private static System.Void RemoveClip(UnityEngine.AudioClip audioClip);
    public static System.Void Reset();
    public static System.Void Stats(System.Int32& loadedSize, System.Int32& maxLoadedSize, System.Int32& loadedCount, System.Int32& playingSize, System.Int32& playingCount);
    private static System.Void UnloadClips();
}
```


## Fields

- `private static System.Int32 s_InstanceCount`  

```csharp
private static System.Int32 s_InstanceCount;
```

- `private static System.Int32 s_LoadedSize`  

```csharp
private static System.Int32 s_LoadedSize;
```

- `private static System.Int32 s_PlayingSize`  

```csharp
private static System.Int32 s_PlayingSize;
```

- `private static System.Int32 s_MaxLoadedSize`  

```csharp
private static System.Int32 s_MaxLoadedSize;
```

- `private static System.Collections.Generic.Stack<UnityEngine.AudioSource> s_Pool`  

```csharp
private static System.Collections.Generic.Stack<UnityEngine.AudioSource> s_Pool;
```

- `private static System.Collections.Generic.Dictionary<UnityEngine.AudioClip, System.Int32> s_PlayingClips`  

```csharp
private static System.Collections.Generic.Dictionary<UnityEngine.AudioClip, System.Int32> s_PlayingClips;
```

- `private static System.Collections.Generic.List<UnityEngine.AudioClip> s_UnloadClips`  

```csharp
private static System.Collections.Generic.List<UnityEngine.AudioClip> s_UnloadClips;
```


## Properties

- `public static System.Int32 memoryBudget { get; set }`  

```csharp
public static System.Int32 memoryBudget { get; set; }
```


## Methods

- `internal static <Get>g__CreateAudioSource|12_0() : UnityEngine.AudioSource`  

```csharp
internal static UnityEngine.AudioSource <Get>g__CreateAudioSource|12_0();
```

- `private static AddClip(UnityEngine.AudioClip audioClip) : System.Void`  

```csharp
private static System.Void AddClip(UnityEngine.AudioClip audioClip);
```

- `public static Get() : UnityEngine.AudioSource`  

```csharp
public static UnityEngine.AudioSource Get();
```

- `private static GetClipSize(UnityEngine.AudioClip audioClip) : System.Int32`  

```csharp
private static System.Int32 GetClipSize(UnityEngine.AudioClip audioClip);
```

- `public static Play(UnityEngine.AudioSource audioSource) : System.Void`  

```csharp
public static System.Void Play(UnityEngine.AudioSource audioSource);
```

- `public static PlayDelayed(UnityEngine.AudioSource audioSource, System.Single delay) : System.Void`  

```csharp
public static System.Void PlayDelayed(UnityEngine.AudioSource audioSource, System.Single delay);
```

- `public static Release(UnityEngine.AudioSource audioSource) : System.Void`  

```csharp
public static System.Void Release(UnityEngine.AudioSource audioSource);
```

- `private static RemoveClip(UnityEngine.AudioClip audioClip) : System.Void`  

```csharp
private static System.Void RemoveClip(UnityEngine.AudioClip audioClip);
```

- `public static Reset() : System.Void`  

```csharp
public static System.Void Reset();
```

- `public static Stats(System.Int32& loadedSize, System.Int32& maxLoadedSize, System.Int32& loadedCount, System.Int32& playingSize, System.Int32& playingCount) : System.Void`  

```csharp
public static System.Void Stats(System.Int32& loadedSize, System.Int32& maxLoadedSize, System.Int32& loadedCount, System.Int32& playingSize, System.Int32& playingCount);
```

- `private static UnloadClips() : System.Void`  

```csharp
private static System.Void UnloadClips();
```


