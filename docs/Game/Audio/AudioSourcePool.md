# Game.Audio.AudioManager+AudioSourcePool

**Assembly:** `Game`  
**Namespace:** `Game.Audio`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static System.Int32 s_InstanceCount`  
- `private static System.Int32 s_LoadedSize`  
- `private static System.Int32 s_PlayingSize`  
- `private static System.Int32 s_MaxLoadedSize`  
- `private static System.Collections.Generic.Stack<UnityEngine.AudioSource> s_Pool`  
- `private static System.Collections.Generic.Dictionary<UnityEngine.AudioClip, System.Int32> s_PlayingClips`  
- `private static System.Collections.Generic.List<UnityEngine.AudioClip> s_UnloadClips`  

## Properties

- `public static System.Int32 memoryBudget { get; set }`  

## Methods

- `internal static <Get>g__CreateAudioSource|12_0() : UnityEngine.AudioSource`  
- `private static AddClip(UnityEngine.AudioClip audioClip) : System.Void`  
- `public static Get() : UnityEngine.AudioSource`  
- `private static GetClipSize(UnityEngine.AudioClip audioClip) : System.Int32`  
- `public static Play(UnityEngine.AudioSource audioSource) : System.Void`  
- `public static PlayDelayed(UnityEngine.AudioSource audioSource, System.Single delay) : System.Void`  
- `public static Release(UnityEngine.AudioSource audioSource) : System.Void`  
- `private static RemoveClip(UnityEngine.AudioClip audioClip) : System.Void`  
- `public static Reset() : System.Void`  
- `public static Stats(System.Int32& loadedSize, System.Int32& maxLoadedSize, System.Int32& loadedCount, System.Int32& playingSize, System.Int32& playingCount) : System.Void`  
- `private static UnloadClips() : System.Void`  

