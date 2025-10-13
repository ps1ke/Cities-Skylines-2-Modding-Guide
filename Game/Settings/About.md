# Game.Settings.About

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

## Code

```csharp
public class About : Game.Settings.Setting, System.IEquatable<Game.Settings.Setting>
{
    public static const System.String kName;
    private static const System.String kGameGroup;
    private static const System.String kContentGroup;

    public System.String gameVersion { get; }
    public System.String gameConfiguration { get; }
    public System.String coreVersion { get; }
    public System.String uiVersion { get; }
    public System.String unityVersion { get; }
    public System.String cohtmlVersion { get; }
    public System.String atlVersion { get; }

    public About();

    internal static System.String <GetPageData>g__GetOwnershipCheckString|18_0(Colossal.PSI.Common.IDlc id);
    internal static System.String <GetPageData>g__GetOwnershipString|18_1(Colossal.PSI.Common.IDlc id);
    public virtual Game.UI.Menu.AutomaticSettings+SettingPageData GetPageData(System.String id, System.Boolean addPrefix);
    public virtual System.Void SetDefaults();
}
```


## Fields

- `public static const System.String kName`  

```csharp
public static const System.String kName;
```

- `private static const System.String kGameGroup`  

```csharp
private static const System.String kGameGroup;
```

- `private static const System.String kContentGroup`  

```csharp
private static const System.String kContentGroup;
```


## Properties

- `public System.String gameVersion { get }`  

```csharp
public System.String gameVersion { get; }
```

- `public System.String gameConfiguration { get }`  

```csharp
public System.String gameConfiguration { get; }
```

- `public System.String coreVersion { get }`  

```csharp
public System.String coreVersion { get; }
```

- `public System.String uiVersion { get }`  

```csharp
public System.String uiVersion { get; }
```

- `public System.String unityVersion { get }`  

```csharp
public System.String unityVersion { get; }
```

- `public System.String cohtmlVersion { get }`  

```csharp
public System.String cohtmlVersion { get; }
```

- `public System.String atlVersion { get }`  

```csharp
public System.String atlVersion { get; }
```


## Constructors

- `public About()`  

```csharp
public About();
```


## Methods

- `internal static <GetPageData>g__GetOwnershipCheckString|18_0(Colossal.PSI.Common.IDlc id) : System.String`  

```csharp
internal static System.String <GetPageData>g__GetOwnershipCheckString|18_0(Colossal.PSI.Common.IDlc id);
```

- `internal static <GetPageData>g__GetOwnershipString|18_1(Colossal.PSI.Common.IDlc id) : System.String`  

```csharp
internal static System.String <GetPageData>g__GetOwnershipString|18_1(Colossal.PSI.Common.IDlc id);
```

- `public virtual GetPageData(System.String id, System.Boolean addPrefix) : Game.UI.Menu.AutomaticSettings+SettingPageData`  

```csharp
public virtual Game.UI.Menu.AutomaticSettings+SettingPageData GetPageData(System.String id, System.Boolean addPrefix);
```

- `public virtual SetDefaults() : System.Void`  

```csharp
public virtual System.Void SetDefaults();
```


## Nested types

- `Game.Settings.About+<>c__DisplayClass18_0`  
- `Game.Settings.About+<>c__DisplayClass18_1`  

