# Game.SceneFlow.SaveHelpers

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class SaveHelpers
{
    public static const System.String kSaveLoadTaskName;

    public static System.Void DeleteSaveGame(Game.Assets.SaveGameMetadata saveGameMetadata);
    public static Colossal.IO.AssetDatabase.AssetDataPath GetAssetDataPath<T>(Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.String saveName);
}
```


## Fields

- `public static const System.String kSaveLoadTaskName`  

```csharp
public static const System.String kSaveLoadTaskName;
```


## Methods

- `public static DeleteSaveGame(Game.Assets.SaveGameMetadata saveGameMetadata) : System.Void`  

```csharp
public static System.Void DeleteSaveGame(Game.Assets.SaveGameMetadata saveGameMetadata);
```

- `public static GetAssetDataPath<T>(Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.String saveName) : Colossal.IO.AssetDatabase.AssetDataPath`  

```csharp
public static Colossal.IO.AssetDatabase.AssetDataPath GetAssetDataPath<T>(Colossal.IO.AssetDatabase.ILocalAssetDatabase database, System.String saveName);
```


