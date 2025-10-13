# Colossal.IO.AssetDatabase.VirtualTexturing.PVTTileIndexer

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class PVTTileIndexer
{
    private static readonly System.Int32[] NbTilesPerLevelPerDimension;
    private static readonly System.Int32[] IndexOffsetPerLevel;
    private static const System.Int32 NB_LEVELS;

    public static System.Int32 GetUniversalTileIndex(System.Int32 column, System.Int32 row, System.Int32 level);
}
```


## Fields

- `private static readonly System.Int32[] NbTilesPerLevelPerDimension`  

```csharp
private static readonly System.Int32[] NbTilesPerLevelPerDimension;
```

- `private static readonly System.Int32[] IndexOffsetPerLevel`  

```csharp
private static readonly System.Int32[] IndexOffsetPerLevel;
```

- `private static const System.Int32 NB_LEVELS`  

```csharp
private static const System.Int32 NB_LEVELS;
```


## Methods

- `public static GetUniversalTileIndex(System.Int32 column, System.Int32 row, System.Int32 level) : System.Int32`  

```csharp
public static System.Int32 GetUniversalTileIndex(System.Int32 column, System.Int32 row, System.Int32 level);
```


