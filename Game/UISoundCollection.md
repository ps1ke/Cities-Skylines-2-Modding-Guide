# Game.UISoundCollection

**Assembly:** Assembly-CSharp  
**Namespace:** Game

**Type:** class (ScriptableObject)

**Base:** UnityEngine.ScriptableObject

**Summary:** A ScriptableObject that groups UI sound clips with per-clip volume settings and provides simple lookup/playback helpers. Intended to be authored in the editor (CreateAssetMenu) so designers can create named UI sound collections. Keeps an internal dictionary mapping sound names to SoundInfo for fast lookup by name at runtime.
---

## Fields

- `public SoundInfo[] m_Sounds`  
Holds the array of serializable SoundInfo entries that are edited in the inspector. Each SoundInfo contains a name, an AudioClip, and a per-clip volume multiplier. If this array is null when the asset is enabled, it is initialized to an empty array.

- `private System.Collections.Generic.Dictionary<string, SoundInfo> m_SoundsDict`  
Runtime dictionary built from m_Sounds that maps each SoundInfo.m_Name to the corresponding SoundInfo for quick lookup by name. Built/cleared in OnEnable and RefreshSoundsDict().

- Nested type: `public class SoundInfo` (Serializable)  
  - `public string m_Name` — the lookup name/key for this sound.  
  - `public AudioClip m_Clip` — the audio clip to play.  
  - `[Range(0f,1f)] public float m_Volume = 1f` — per-clip volume multiplier applied when playing this clip.

## Properties

- None.

## Constructors

- `public UISoundCollection()`  
No explicit constructor is defined in source; the default parameterless constructor is used. Initialization of runtime structures occurs in Unity's OnEnable callback rather than a constructor.

## Methods

- `private void OnEnable()`  
Initializes the m_Sounds array if null, creates a new dictionary instance for m_SoundsDict, and populates it by calling RefreshSoundsDict(). This is used to ensure editor-created assets and deserialized assets have a valid runtime dictionary.

- `public void PlaySound(int soundIndex, float volume = 1f)`  
Plays the sound at the provided index in the m_Sounds array (if the index is valid). The final playback volume is volume * SoundInfo.m_Volume. If the index is out of range, nothing happens.

- `public void PlaySound(string soundName, float volume = 1f)`  
Looks up the named SoundInfo in m_SoundsDict and, if found, plays its clip. The final playback volume is volume * SoundInfo.m_Volume. If the name is not found, nothing happens.

- `private void PlaySound([Colossal.Annotations.NotNull] AudioClip clip, float volume)`  
Internal helper that actually requests playback from the global audio system. It checks Camera.main is present and then calls AudioManager.instance?.PlayUISound(clip, volume). If there is no Camera.main or no AudioManager.instance, the call is skipped.

- `public void RefreshSoundsDict()`  
Clears m_SoundsDict and repopulates it from m_Sounds by assigning each entry under its m_Name key. Useful to call if the m_Sounds array has been modified at runtime or in editor code and you need to rebuild the lookup dictionary.

```csharp
private void OnEnable()
{
    if (m_Sounds == null)
    {
        m_Sounds = new SoundInfo[0];
    }
    m_SoundsDict = new Dictionary<string, SoundInfo>();
    RefreshSoundsDict();
}
```

Additional notes and usage tips:
- The class is decorated with CreateAssetMenu(menuName = "Colossal/UI/UISoundCollection"), so create instances via Assets -> Create -> Colossal -> UI -> UISoundCollection in the Unity editor.
- SoundInfo.m_Name must be unique within a UISoundCollection for reliable name-based lookup; RefreshSoundsDict will overwrite duplicate keys with the last occurrence.
- Playback depends on AudioManager.instance and Camera.main; calling PlaySound from contexts where the main camera is not available will result in no sound.
- Volume handling: the optional method parameter volume is multiplied by the per-clip m_Volume, so you can have global adjustments while preserving per-clip tuning.