# Game.UI.URI

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class URI
{
    private static readonly System.Text.RegularExpressions.Regex kEntityPattern;
    private static readonly System.Text.RegularExpressions.Regex kInfoviewPattern;

    public static System.String FromEntity(Unity.Entities.Entity entity);
    public static System.String FromInfoView(Unity.Entities.Entity entity);
    public static System.Boolean TryParseEntity(System.String input, Unity.Entities.Entity& entity);
    public static System.Boolean TryParseInfoview(System.String input, Unity.Entities.Entity& entity);
}
```


## Fields

- `private static readonly System.Text.RegularExpressions.Regex kEntityPattern`  

```csharp
private static readonly System.Text.RegularExpressions.Regex kEntityPattern;
```

- `private static readonly System.Text.RegularExpressions.Regex kInfoviewPattern`  

```csharp
private static readonly System.Text.RegularExpressions.Regex kInfoviewPattern;
```


## Methods

- `public static FromEntity(Unity.Entities.Entity entity) : System.String`  

```csharp
public static System.String FromEntity(Unity.Entities.Entity entity);
```

- `public static FromInfoView(Unity.Entities.Entity entity) : System.String`  

```csharp
public static System.String FromInfoView(Unity.Entities.Entity entity);
```

- `public static TryParseEntity(System.String input, Unity.Entities.Entity& entity) : System.Boolean`  

```csharp
public static System.Boolean TryParseEntity(System.String input, Unity.Entities.Entity& entity);
```

- `public static TryParseInfoview(System.String input, Unity.Entities.Entity& entity) : System.Boolean`  

```csharp
public static System.Boolean TryParseInfoview(System.String input, Unity.Entities.Entity& entity);
```


