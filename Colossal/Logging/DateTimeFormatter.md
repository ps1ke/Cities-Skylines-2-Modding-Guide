# Colossal.Logging.DateTimeFormatter

**Assembly:** `Colossal.Logging`  
**Namespace:** `Colossal.Logging`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class DateTimeFormatter
{
    private static System.Int64 klastTimeToTheSecond;
    private static System.Text.StringBuilder klastTimeBuf;
    private static System.Collections.Hashtable klastTimeString;

    public DateTimeFormatter();

    public System.String FormatDate(System.DateTime dateToFormat);
    public System.Void FormatDate(System.DateTime dateToFormat, System.IO.StreamWriter writer);
    private System.Void FormatDateWithoutMillis(System.DateTime dateToFormat, System.Text.StringBuilder buffer);
}
```


## Fields

- `private static System.Int64 klastTimeToTheSecond`  

```csharp
private static System.Int64 klastTimeToTheSecond;
```

- `private static System.Text.StringBuilder klastTimeBuf`  

```csharp
private static System.Text.StringBuilder klastTimeBuf;
```

- `private static System.Collections.Hashtable klastTimeString`  

```csharp
private static System.Collections.Hashtable klastTimeString;
```


## Constructors

- `public DateTimeFormatter()`  

```csharp
public DateTimeFormatter();
```


## Methods

- `public FormatDate(System.DateTime dateToFormat) : System.String`  

```csharp
public System.String FormatDate(System.DateTime dateToFormat);
```

- `public FormatDate(System.DateTime dateToFormat, System.IO.StreamWriter writer) : System.Void`  

```csharp
public System.Void FormatDate(System.DateTime dateToFormat, System.IO.StreamWriter writer);
```

- `private FormatDateWithoutMillis(System.DateTime dateToFormat, System.Text.StringBuilder buffer) : System.Void`  

```csharp
private System.Void FormatDateWithoutMillis(System.DateTime dateToFormat, System.Text.StringBuilder buffer);
```


