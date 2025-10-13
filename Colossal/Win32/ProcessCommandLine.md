# Colossal.Win32.ProcessCommandLine

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Win32`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ProcessCommandLine
{
    internal static System.String <Retrieve>g__ReadUnicodeString|4_0(Colossal.Win32.ProcessCommandLine+Win32Native+UnicodeString unicodeString, Colossal.Win32.ProcessCommandLine+<>c__DisplayClass4_0& , Colossal.Win32.ProcessCommandLine+<>c__DisplayClass4_1& );
    public static System.Collections.Generic.IReadOnlyList<System.String> CommandLineToArgs(System.String commandLine);
    public static System.String ErrorToString(System.Int32 error);
    private static System.Boolean ReadStructFromProcessMemory<TStruct>(System.IntPtr hProcess, System.IntPtr lpBaseAddress, TStruct& val);
    public static System.Int32 Retrieve(System.Diagnostics.Process process, System.String& parameterValue, Colossal.Win32.ProcessCommandLine+Parameter parameter);
}
```


## Methods

- `internal static <Retrieve>g__ReadUnicodeString|4_0(Colossal.Win32.ProcessCommandLine+Win32Native+UnicodeString unicodeString, Colossal.Win32.ProcessCommandLine+<>c__DisplayClass4_0& , Colossal.Win32.ProcessCommandLine+<>c__DisplayClass4_1& ) : System.String`  

```csharp
internal static System.String <Retrieve>g__ReadUnicodeString|4_0(Colossal.Win32.ProcessCommandLine+Win32Native+UnicodeString unicodeString, Colossal.Win32.ProcessCommandLine+<>c__DisplayClass4_0& , Colossal.Win32.ProcessCommandLine+<>c__DisplayClass4_1& );
```

- `public static CommandLineToArgs(System.String commandLine) : System.Collections.Generic.IReadOnlyList<System.String>`  

```csharp
public static System.Collections.Generic.IReadOnlyList<System.String> CommandLineToArgs(System.String commandLine);
```

- `public static ErrorToString(System.Int32 error) : System.String`  

```csharp
public static System.String ErrorToString(System.Int32 error);
```

- `private static ReadStructFromProcessMemory<TStruct>(System.IntPtr hProcess, System.IntPtr lpBaseAddress, TStruct& val) : System.Boolean`  

```csharp
private static System.Boolean ReadStructFromProcessMemory<TStruct>(System.IntPtr hProcess, System.IntPtr lpBaseAddress, TStruct& val);
```

- `public static Retrieve(System.Diagnostics.Process process, System.String& parameterValue, Colossal.Win32.ProcessCommandLine+Parameter parameter = CommandLine) : System.Int32`  

```csharp
public static System.Int32 Retrieve(System.Diagnostics.Process process, System.String& parameterValue, Colossal.Win32.ProcessCommandLine+Parameter parameter);
```


## Nested types

- `Colossal.Win32.ProcessCommandLine+Win32Native`  
- `Colossal.Win32.ProcessCommandLine+Parameter`  
- `Colossal.Win32.ProcessCommandLine+<>c__DisplayClass4_0`  
- `Colossal.Win32.ProcessCommandLine+<>c__DisplayClass4_1`  

