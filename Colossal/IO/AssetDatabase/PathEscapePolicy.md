# Colossal.IO.AssetDatabase.GdkCloudDataSource+PathEscapePolicy

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.IPathEscapePolicy`  

## Code

```csharp
public class PathEscapePolicy : Colossal.IO.AssetDatabase.IPathEscapePolicy
{
    private static readonly System.String kReservedPathCharacters;
    private static readonly System.String kReservedFileNameCharacters;

    public PathEscapePolicy();

    public System.String Escape(Colossal.IO.AssetDatabase.EscapeStrategy strategy, System.String input);
    public System.String GetReservedCharacters(Colossal.IO.AssetDatabase.EscapeStrategy strategy);
    public System.String Unescape(System.String input);
}
```


## Fields

- `private static readonly System.String kReservedPathCharacters`  

```csharp
private static readonly System.String kReservedPathCharacters;
```

- `private static readonly System.String kReservedFileNameCharacters`  

```csharp
private static readonly System.String kReservedFileNameCharacters;
```


## Constructors

- `public PathEscapePolicy()`  

```csharp
public PathEscapePolicy();
```


## Methods

- `public Escape(Colossal.IO.AssetDatabase.EscapeStrategy strategy, System.String input) : System.String`  

```csharp
public System.String Escape(Colossal.IO.AssetDatabase.EscapeStrategy strategy, System.String input);
```

- `public GetReservedCharacters(Colossal.IO.AssetDatabase.EscapeStrategy strategy) : System.String`  

```csharp
public System.String GetReservedCharacters(Colossal.IO.AssetDatabase.EscapeStrategy strategy);
```

- `public Unescape(System.String input) : System.String`  

```csharp
public System.String Unescape(System.String input);
```


## Nested types

- `Colossal.IO.AssetDatabase.GdkCloudDataSource+PathEscapePolicy+<>c`  

