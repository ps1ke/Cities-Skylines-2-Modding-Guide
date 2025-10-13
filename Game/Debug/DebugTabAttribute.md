# Game.Debug.DebugTabAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `UnityEngine.Scripting.PreserveAttribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class DebugTabAttribute : UnityEngine.Scripting.PreserveAttribute
{
    public readonly System.String name;
    public readonly System.Int32 priority;

    public DebugTabAttribute(System.String name, System.Int32 priority);

}
```


## Fields

- `public readonly System.String name`  

```csharp
public readonly System.String name;
```

- `public readonly System.Int32 priority`  

```csharp
public readonly System.Int32 priority;
```


## Constructors

- `public DebugTabAttribute(System.String name, System.Int32 priority = 0)`  

```csharp
public DebugTabAttribute(string name, int priority = 0)
	{
		this.name = name;
		this.priority = priority;
	}
```


