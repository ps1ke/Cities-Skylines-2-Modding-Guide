# Colossal.Atmosphere.Internal.JulianDateTime

**Assembly:** `Game`  
**Namespace:** `Colossal.Atmosphere.Internal`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class JulianDateTime
{
    public static System.DateTime ConvertToDateTime(System.Double date);
    public static System.Double ConvertToJulianDateTime(System.Int32 year, System.Int32 month, System.Int32 day, System.Int32 hour, System.Int32 minute, System.Int32 second, System.Int32 millisecond);
    public static System.Double ConvertToJulianDateTime(System.DateTime date);
    private static System.Double DateToJulianDate(System.Int32 year, System.Int32 month, System.Int32 day, System.Int32 hour, System.Int32 minute, System.Int32 second, System.Int32 millisecond);
    public static System.Boolean IsJulianDate(System.Int32 year, System.Int32 month, System.Int32 day);
    private static System.DateTime JulianDateToDate(System.Double julianDate);
}
```


## Methods

- `public static ConvertToDateTime(System.Double date) : System.DateTime`  

```csharp
public static System.DateTime ConvertToDateTime(System.Double date);
```

- `public static ConvertToJulianDateTime(System.Int32 year, System.Int32 month, System.Int32 day, System.Int32 hour, System.Int32 minute, System.Int32 second, System.Int32 millisecond) : System.Double`  

```csharp
public static System.Double ConvertToJulianDateTime(System.Int32 year, System.Int32 month, System.Int32 day, System.Int32 hour, System.Int32 minute, System.Int32 second, System.Int32 millisecond);
```

- `public static ConvertToJulianDateTime(System.DateTime date) : System.Double`  

```csharp
public static System.Double ConvertToJulianDateTime(System.DateTime date);
```

- `private static DateToJulianDate(System.Int32 year, System.Int32 month, System.Int32 day, System.Int32 hour, System.Int32 minute, System.Int32 second, System.Int32 millisecond) : System.Double`  

```csharp
private static System.Double DateToJulianDate(System.Int32 year, System.Int32 month, System.Int32 day, System.Int32 hour, System.Int32 minute, System.Int32 second, System.Int32 millisecond);
```

- `public static IsJulianDate(System.Int32 year, System.Int32 month, System.Int32 day) : System.Boolean`  

```csharp
public static System.Boolean IsJulianDate(System.Int32 year, System.Int32 month, System.Int32 day);
```

- `private static JulianDateToDate(System.Double julianDate) : System.DateTime`  

```csharp
private static System.DateTime JulianDateToDate(System.Double julianDate);
```


