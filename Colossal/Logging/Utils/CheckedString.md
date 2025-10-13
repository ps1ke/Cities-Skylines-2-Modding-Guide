# Colossal.Logging.Utils.CheckedString

**Assembly:** `Colossal.Logging`  
**Namespace:** `Colossal.Logging.Utils`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class CheckedString
{
    public static System.String Combine(System.String path1, System.String path2);
    public static System.String EscapeFormat(System.String str);
    public static System.String Format(System.IFormatProvider provider, System.String format, System.Object arg0);
    public static System.String Format(System.IFormatProvider provider, System.String format, System.Object arg0, System.Object arg1);
    public static System.String Format(System.IFormatProvider provider, System.String format, System.Object arg0, System.Object arg1, System.Object arg2);
    public static System.String Format(System.IFormatProvider provider, System.String format, System.Object[] args);
    public static System.String GetFriendlyName(System.Type type);
    public static System.String MakeRandomString(System.Int32 count);
    public static System.String MakeUniqueFileName(System.String filename);
    private static System.String Namespace(System.Type type);
    private static System.String TypeName(System.Type type);
}
```


## Methods

- `public static Combine(System.String path1, System.String path2) : System.String`  

```csharp
public static System.String Combine(System.String path1, System.String path2);
```

- `public static EscapeFormat(System.String str) : System.String`  

```csharp
public static System.String EscapeFormat(System.String str);
```

- `public static Format(System.IFormatProvider provider, System.String format, System.Object arg0) : System.String`  

```csharp
public static System.String Format(System.IFormatProvider provider, System.String format, System.Object arg0);
```

- `public static Format(System.IFormatProvider provider, System.String format, System.Object arg0, System.Object arg1) : System.String`  

```csharp
public static System.String Format(System.IFormatProvider provider, System.String format, System.Object arg0, System.Object arg1);
```

- `public static Format(System.IFormatProvider provider, System.String format, System.Object arg0, System.Object arg1, System.Object arg2) : System.String`  

```csharp
public static System.String Format(System.IFormatProvider provider, System.String format, System.Object arg0, System.Object arg1, System.Object arg2);
```

- `public static Format(System.IFormatProvider provider, System.String format, System.Object[] args) : System.String`  

```csharp
public static System.String Format(System.IFormatProvider provider, System.String format, System.Object[] args);
```

- `public static GetFriendlyName(System.Type type) : System.String`  

```csharp
public static System.String GetFriendlyName(System.Type type);
```

- `public static MakeRandomString(System.Int32 count) : System.String`  

```csharp
public static System.String MakeRandomString(System.Int32 count);
```

- `public static MakeUniqueFileName(System.String filename) : System.String`  

```csharp
public static System.String MakeUniqueFileName(System.String filename);
```

- `private static Namespace(System.Type type) : System.String`  

```csharp
private static System.String Namespace(System.Type type);
```

- `private static TypeName(System.Type type) : System.String`  

```csharp
private static System.String TypeName(System.Type type);
```


