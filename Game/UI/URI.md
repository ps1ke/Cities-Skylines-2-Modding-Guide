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
public static string FromEntity(Entity entity)
	{
		return $"entity://{entity.Index}/{entity.Version}";
	}
```

- `public static FromInfoView(Unity.Entities.Entity entity) : System.String`  

```csharp
public static string FromInfoView(Entity entity)
	{
		return $"infoview://{entity.Index}/{entity.Version}";
	}
```

- `public static TryParseEntity(System.String input, Unity.Entities.Entity& entity) : System.Boolean`  

```csharp
public static bool TryParseEntity(string input, out Entity entity)
	{
		Match match = kEntityPattern.Match(input);
		if (match.Success)
		{
			entity = new Entity
			{
				Index = int.Parse(match.Groups[1].Value),
				Version = int.Parse(match.Groups[2].Value)
			};
			return true;
		}
		entity = Entity.Null;
		return false;
	}
```

- `public static TryParseInfoview(System.String input, Unity.Entities.Entity& entity) : System.Boolean`  

```csharp
public static bool TryParseInfoview(string input, out Entity entity)
	{
		Match match = kInfoviewPattern.Match(input);
		if (match.Success)
		{
			entity = new Entity
			{
				Index = int.Parse(match.Groups[1].Value),
				Version = int.Parse(match.Groups[2].Value)
			};
			return true;
		}
		entity = Entity.Null;
		return false;
	}
```


