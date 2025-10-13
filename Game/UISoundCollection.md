# Game.UISoundCollection

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `UnityEngine.ScriptableObject`  

**Attributes:** `CreateAssetMenu`  

## Code

```csharp
public class UISoundCollection : UnityEngine.ScriptableObject
{
    public Game.UISoundCollection+SoundInfo[] m_Sounds;
    private System.Collections.Generic.Dictionary<System.String, Game.UISoundCollection+SoundInfo> m_SoundsDict;

    public UISoundCollection();

    private System.Void OnEnable();
    public System.Void PlaySound(System.Int32 soundIndex, System.Single volume);
    public System.Void PlaySound(System.String soundName, System.Single volume);
    private System.Void PlaySound(UnityEngine.AudioClip clip, System.Single volume);
    public System.Void RefreshSoundsDict();
}
```


## Fields

- `public Game.UISoundCollection+SoundInfo[] m_Sounds`  

```csharp
public Game.UISoundCollection+SoundInfo[] m_Sounds;
```

- `private System.Collections.Generic.Dictionary<System.String, Game.UISoundCollection+SoundInfo> m_SoundsDict`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.UISoundCollection+SoundInfo> m_SoundsDict;
```


## Constructors

- `public UISoundCollection()`  

```csharp
public UISoundCollection();
```


## Methods

- `private OnEnable() : System.Void`  

```csharp
private System.Void OnEnable();
```

- `public PlaySound(System.Int32 soundIndex, System.Single volume = 1) : System.Void`  

```csharp
public System.Void PlaySound(System.Int32 soundIndex, System.Single volume);
```

- `public PlaySound(System.String soundName, System.Single volume = 1) : System.Void`  

```csharp
public System.Void PlaySound(System.String soundName, System.Single volume);
```

- `private PlaySound(UnityEngine.AudioClip clip, System.Single volume) : System.Void`  

```csharp
private System.Void PlaySound(UnityEngine.AudioClip clip, System.Single volume);
```

- `public RefreshSoundsDict() : System.Void`  

```csharp
public System.Void RefreshSoundsDict();
```


## Nested types

- `Game.UISoundCollection+SoundInfo`  

