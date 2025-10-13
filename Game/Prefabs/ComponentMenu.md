# Game.Prefabs.ComponentMenu

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class sealed public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public sealed class ComponentMenu : System.Attribute
{
    public readonly System.String menu;
    public readonly System.Type[] requiredPrefab;

    public ComponentMenu(System.Type[] requiredPrefab);
    public ComponentMenu(System.String menu, System.Type[] requiredPrefab);

}
```


## Fields

- `public readonly System.String menu`  

```csharp
public readonly System.String menu;
```

- `public readonly System.Type[] requiredPrefab`  

```csharp
public readonly System.Type[] requiredPrefab;
```


## Constructors

- `public ComponentMenu(System.Type[] requiredPrefab)`  

```csharp
public ComponentMenu(params Type[] requiredPrefab)
	{
		this.requiredPrefab = requiredPrefab;
	}
```

- `public ComponentMenu(System.String menu, System.Type[] requiredPrefab)`  

```csharp
public ComponentMenu(params Type[] requiredPrefab)
	{
		this.requiredPrefab = requiredPrefab;
	}
```


