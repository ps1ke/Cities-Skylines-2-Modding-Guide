# Game.UI.DialogMessage

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class DialogMessage
{
    public static const System.String kBulldozer;
    public static const System.String kProgressLoss;
    public static const System.String kOverwriteSave;
    public static const System.String kOverwriteMap;
    public static const System.String kOverwriteAsset;
    public static const System.String kConfirmWipe;
    public static const System.String kDisableAchievements;

    public static System.String GetId(System.String value);
}
```


## Fields

- `public static const System.String kBulldozer`  

```csharp
public static const System.String kBulldozer;
```

- `public static const System.String kProgressLoss`  

```csharp
public static const System.String kProgressLoss;
```

- `public static const System.String kOverwriteSave`  

```csharp
public static const System.String kOverwriteSave;
```

- `public static const System.String kOverwriteMap`  

```csharp
public static const System.String kOverwriteMap;
```

- `public static const System.String kOverwriteAsset`  

```csharp
public static const System.String kOverwriteAsset;
```

- `public static const System.String kConfirmWipe`  

```csharp
public static const System.String kConfirmWipe;
```

- `public static const System.String kDisableAchievements`  

```csharp
public static const System.String kDisableAchievements;
```


## Methods

- `public static GetId(System.String value) : System.String`  

```csharp
public static string GetId(string value)
	{
		return "Common.DIALOG_MESSAGE[" + value + "]";
	}
```


