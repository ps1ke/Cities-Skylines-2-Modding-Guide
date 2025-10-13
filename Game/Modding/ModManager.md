# Game.Modding.ModManager

**Assembly:** `Game`  
**Namespace:** `Game.Modding`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerable<Game.Modding.ModManager+ModInfo>`, `System.Collections.IEnumerable`, `System.IDisposable`  

## Code

```csharp
public class ModManager : System.Collections.Generic.IEnumerable<Game.Modding.ModManager+ModInfo>, System.Collections.IEnumerable, System.IDisposable
{
    private readonly System.Collections.Generic.List<Game.Modding.ModManager+ModInfo> m_ModsInfos;
    private System.Boolean m_Disabled;
    private System.Boolean m_Initialized;
    private System.Boolean m_IsInProgress;
    private System.Boolean <restartRequired>k__BackingField;
    private static Colossal.Logging.ILog log;
    private static const System.String kBurstSuffix;

    public System.Boolean isInitialized { get; }
    public System.Boolean restartRequired { get; private set; }

    private ModManager();
    public ModManager(System.Boolean disabled);

    private System.Void <RequireRestart>b__27_0();
    private System.Void <RequireRestart>b__27_1(System.Int32 msg);
    public System.Void AddUIModule(Colossal.IO.AssetDatabase.UIModuleAsset uiModule);
    public static System.Boolean AreModsEnabled();
    public System.Void Dispose();
    public System.Collections.Generic.IEnumerator<Game.Modding.ModManager+ModInfo> GetEnumerator();
    public static System.String[] GetModsEnabled();
    public System.Void Initialize(Game.UpdateSystem updateSystem);
    private System.Void InitializeMods(Game.UpdateSystem updateSystem);
    private System.Void InitializeUIModules();
    public System.String[] ListModsEnabled();
    private System.Void RegisterMods();
    public System.Void RemoveUIModule(Colossal.IO.AssetDatabase.UIModuleAsset uiModule);
    public System.Void RequireRestart();
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
    public System.Boolean TryGetExecutableAsset(Game.Modding.IMod mod, Colossal.IO.AssetDatabase.ExecutableAsset& asset);
    public System.Boolean TryGetExecutableAsset(System.Reflection.Assembly assembly, Colossal.IO.AssetDatabase.ExecutableAsset& asset);
}
```


## Fields

- `private readonly System.Collections.Generic.List<Game.Modding.ModManager+ModInfo> m_ModsInfos`  

```csharp
private readonly System.Collections.Generic.List<Game.Modding.ModManager+ModInfo> m_ModsInfos;
```

- `private System.Boolean m_Disabled`  

```csharp
private System.Boolean m_Disabled;
```

- `private System.Boolean m_Initialized`  

```csharp
private System.Boolean m_Initialized;
```

- `private System.Boolean m_IsInProgress`  

```csharp
private System.Boolean m_IsInProgress;
```

- `private System.Boolean <restartRequired>k__BackingField`  

```csharp
private System.Boolean <restartRequired>k__BackingField;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static const System.String kBurstSuffix`  

```csharp
private static const System.String kBurstSuffix;
```


## Properties

- `public System.Boolean isInitialized { get }`  

```csharp
public System.Boolean isInitialized { get; }
```

- `public System.Boolean restartRequired { get; private set }`  

```csharp
public System.Boolean restartRequired { get; private set; }
```


## Constructors

- `private ModManager()`  

```csharp
private ModManager();
```

- `public ModManager(System.Boolean disabled)`  

```csharp
public ModManager(System.Boolean disabled);
```


## Methods

- `private <RequireRestart>b__27_0() : System.Void`  

```csharp
private System.Void <RequireRestart>b__27_0();
```

- `private <RequireRestart>b__27_1(System.Int32 msg) : System.Void`  

```csharp
private System.Void <RequireRestart>b__27_1(System.Int32 msg);
```

- `public AddUIModule(Colossal.IO.AssetDatabase.UIModuleAsset uiModule) : System.Void`  

```csharp
public System.Void AddUIModule(Colossal.IO.AssetDatabase.UIModuleAsset uiModule);
```

- `public static AreModsEnabled() : System.Boolean`  

```csharp
public static System.Boolean AreModsEnabled();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Game.Modding.ModManager+ModInfo>`  

```csharp
public System.Collections.Generic.IEnumerator<Game.Modding.ModManager+ModInfo> GetEnumerator();
```

- `public static GetModsEnabled() : System.String[]`  

```csharp
public static System.String[] GetModsEnabled();
```

- `public Initialize(Game.UpdateSystem updateSystem) : System.Void`  

```csharp
public System.Void Initialize(Game.UpdateSystem updateSystem);
```

- `private InitializeMods(Game.UpdateSystem updateSystem) : System.Void`  

```csharp
private System.Void InitializeMods(Game.UpdateSystem updateSystem);
```

- `private InitializeUIModules() : System.Void`  

```csharp
private System.Void InitializeUIModules();
```

- `public ListModsEnabled() : System.String[]`  

```csharp
public System.String[] ListModsEnabled();
```

- `private RegisterMods() : System.Void`  

```csharp
private System.Void RegisterMods();
```

- `public RemoveUIModule(Colossal.IO.AssetDatabase.UIModuleAsset uiModule) : System.Void`  

```csharp
public System.Void RemoveUIModule(Colossal.IO.AssetDatabase.UIModuleAsset uiModule);
```

- `public RequireRestart() : System.Void`  

```csharp
public System.Void RequireRestart();
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```

- `public TryGetExecutableAsset(Game.Modding.IMod mod, Colossal.IO.AssetDatabase.ExecutableAsset& asset) : System.Boolean`  

```csharp
public System.Boolean TryGetExecutableAsset(Game.Modding.IMod mod, Colossal.IO.AssetDatabase.ExecutableAsset& asset);
```

- `public TryGetExecutableAsset(System.Reflection.Assembly assembly, Colossal.IO.AssetDatabase.ExecutableAsset& asset) : System.Boolean`  

```csharp
public System.Boolean TryGetExecutableAsset(System.Reflection.Assembly assembly, Colossal.IO.AssetDatabase.ExecutableAsset& asset);
```


## Nested types

- `Game.Modding.ModManager+ModInfo`  
- `Game.Modding.ModManager+<>c`  
- `Game.Modding.ModManager+<>c__DisplayClass16_0`  
- `Game.Modding.ModManager+<>c__DisplayClass18_0`  
- `Game.Modding.ModManager+<>c__DisplayClass22_0`  

