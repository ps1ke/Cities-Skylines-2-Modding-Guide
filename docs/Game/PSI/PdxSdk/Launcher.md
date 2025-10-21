# Game.PSI.PdxSdk.Launcher

**Assembly:** `Game`  
**Namespace:** `Game.PSI.PdxSdk`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class Launcher
{
    private static readonly System.String kLastSaveInfoPath;
    private static const System.String kLastSaveInfoFileName;

    public static System.Void DeleteLastSaveMetadata();
    private static System.String FormatMoney(System.Int32 money, System.Boolean unlimitedMoney);
    private static System.String LocalizedString(System.String id, System.String def);
    public static System.Void SaveLastSaveMetadata(Game.Assets.SaveInfo saveInfo);
}
```


## Fields

- `private static readonly System.String kLastSaveInfoPath`  

```csharp
private static readonly System.String kLastSaveInfoPath;
```

- `private static const System.String kLastSaveInfoFileName`  

```csharp
private static const System.String kLastSaveInfoFileName;
```


## Methods

- `public static DeleteLastSaveMetadata() : System.Void`  

```csharp
public static System.Void DeleteLastSaveMetadata();
```

- `private static FormatMoney(System.Int32 money, System.Boolean unlimitedMoney) : System.String`  

```csharp
private static System.String FormatMoney(System.Int32 money, System.Boolean unlimitedMoney);
```

- `private static LocalizedString(System.String id, System.String def) : System.String`  

```csharp
private static System.String LocalizedString(System.String id, System.String def);
```

- `public static SaveLastSaveMetadata(Game.Assets.SaveInfo saveInfo) : System.Void`  

```csharp
public static System.Void SaveLastSaveMetadata(Game.Assets.SaveInfo saveInfo);
```


## Nested types

- `Game.PSI.PdxSdk.Launcher+LocaleID`  
- `Game.PSI.PdxSdk.Launcher+SaveInfoData`  

