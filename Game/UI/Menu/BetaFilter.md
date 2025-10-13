# Game.UI.Menu.BetaFilter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class BetaFilter
{
    private static System.Collections.Generic.HashSet<System.String> s_Options;

    public static System.Collections.Generic.IReadOnlyCollection<System.String> options { get; }

    public static System.Void AddOption(System.String option);
    public static System.Void AddOptions(System.String[] options);
}
```


## Fields

- `private static System.Collections.Generic.HashSet<System.String> s_Options`  

```csharp
private static System.Collections.Generic.HashSet<System.String> s_Options;
```


## Properties

- `public static System.Collections.Generic.IReadOnlyCollection<System.String> options { get }`  

```csharp
public static System.Collections.Generic.IReadOnlyCollection<System.String> options { get; }
```


## Methods

- `public static AddOption(System.String option) : System.Void`  

```csharp
public static void AddOption(string option)
	{
		s_Options.Add(option);
	}
```

- `public static AddOptions(System.String[] options) : System.Void`  

```csharp
public static void AddOptions(params string[] options)
	{
		s_Options.UnionWith(options);
	}
```


