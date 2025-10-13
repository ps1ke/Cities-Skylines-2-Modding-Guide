# Colossal.UI.Fatal.ExceptionExtensions

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI.Fatal`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class ExceptionExtensions
{
    private static readonly System.Text.RegularExpressions.Regex kStopCodeRegex;

    public static System.String ToStopCode(System.Exception ex);
}
```


## Fields

- `private static readonly System.Text.RegularExpressions.Regex kStopCodeRegex`  

```csharp
private static readonly System.Text.RegularExpressions.Regex kStopCodeRegex;
```


## Methods

- `public static ToStopCode(System.Exception ex) : System.String`  

```csharp
public static System.String ToStopCode(System.Exception ex);
```


