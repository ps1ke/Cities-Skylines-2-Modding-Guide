# Game.Settings.SettingsUIPlatformAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUIPlatformAttribute : System.Attribute
{
    private readonly Colossal.Platform m_Platforms;
    private readonly System.Boolean m_DebugConditional;

    public SettingsUIPlatformAttribute(Colossal.Platform platforms, System.Boolean debugConditional);

    public System.Boolean IsPlatformSet(UnityEngine.RuntimePlatform platform);
}
```


## Fields

- `private readonly Colossal.Platform m_Platforms`  

```csharp
private readonly Colossal.Platform m_Platforms;
```

- `private readonly System.Boolean m_DebugConditional`  

```csharp
private readonly System.Boolean m_DebugConditional;
```


## Constructors

- `public SettingsUIPlatformAttribute(Colossal.Platform platforms, System.Boolean debugConditional = False)`  

```csharp
public SettingsUIPlatformAttribute(Colossal.Platform platforms, System.Boolean debugConditional);
```


## Methods

- `public IsPlatformSet(UnityEngine.RuntimePlatform platform) : System.Boolean`  

```csharp
public System.Boolean IsPlatformSet(UnityEngine.RuntimePlatform platform);
```


