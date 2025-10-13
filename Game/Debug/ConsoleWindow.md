# Game.Debug.ConsoleWindow

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class ConsoleWindow
{
    private System.IO.TextWriter m_OldOutput;
    private System.IO.TextWriter m_OldError;
    private System.IO.StreamWriter m_Writer;
    private static const System.UInt32 ATTACH_PARENT_PROCESS;
    private static const System.UInt32 ERROR_ACCESS_DENIED;
    private static const System.UInt32 GENERIC_WRITE;
    private static const System.UInt32 GENERIC_READ;
    private static const System.UInt32 FILE_SHARE_READ;
    private static const System.UInt32 FILE_SHARE_WRITE;
    private static const System.UInt32 OPEN_EXISTING;
    private static const System.UInt32 FILE_ATTRIBUTE_NORMAL;
    private static const System.Int32 SC_CLOSE;
    private static const System.Int32 MF_BYCOMMAND;
    private static const System.UInt32 STD_OUTPUT_HANDLE;
    private static const System.UInt32 ENABLE_VIRTUAL_TERMINAL_PROCESSING;
    public static const System.UInt16 FOREGROUND_BLUE;
    public static const System.UInt16 FOREGROUND_GREEN;
    public static const System.UInt16 FOREGROUND_RED;
    public static const System.UInt16 FOREGROUND_INTENSITY;
    public static const System.UInt16 BACKGROUND_BLUE;
    public static const System.UInt16 BACKGROUND_GREEN;
    public static const System.UInt16 BACKGROUND_RED;
    public static const System.UInt16 BACKGROUND_INTENSITY;

    public ConsoleWindow(System.String title, System.Boolean attachConsole);

    private static System.Boolean AllocConsole();
    private static System.Boolean AttachConsole(System.UInt32 dwProcessId);
    private static System.IO.FileStream CreateFileStream(System.String name, System.UInt32 win32DesiredAccess, System.UInt32 win32ShareMode, System.IO.FileAccess dotNetFileAccess);
    private static System.IntPtr CreateFileW(System.String lpFileName, System.UInt32 dwDesiredAccess, System.UInt32 dwShareMode, System.IntPtr lpSecurityAttributes, System.UInt32 dwCreationDisposition, System.UInt32 dwFlagsAndAttributes, System.IntPtr hTemplateFile);
    private static System.Boolean DeleteMenu(System.IntPtr hMenu, System.UInt32 uPosition, System.UInt32 uFlags);
    public System.Void Dispose();
    private static System.Void EnableVirtualTerminal();
    private static System.Void EnableVirtualTerminal(System.IntPtr handle);
    private static System.Boolean FreeConsole();
    private static System.Boolean GetConsoleMode(System.IntPtr hConsoleHandle, System.UInt32& lpMode);
    private static System.IntPtr GetConsoleWindow();
    private static System.IntPtr GetStdHandle(System.UInt32 nStdHandle);
    private static System.IntPtr GetSystemMenu(System.IntPtr hWnd, System.Boolean bRevert);
    private System.Void InitializeInStream();
    private System.IntPtr InitializeOutStream();
    public static System.Void SetColor(System.UInt16 color);
    private static System.Boolean SetConsoleMode(System.IntPtr hConsoleHandle, System.UInt32 dwMode);
    private static System.Boolean SetConsoleTextAttribute(System.IntPtr hConsoleOutput, System.UInt16 attributes);
    private static System.Boolean SetConsoleTitle(System.String lpConsoleTitle);
    private static System.Void SetStdHandle(System.UInt32 nStdHandle, System.IntPtr handle);
    public System.Void SetTitle(System.String strName);
}
```


## Fields

- `private System.IO.TextWriter m_OldOutput`  

```csharp
private System.IO.TextWriter m_OldOutput;
```

- `private System.IO.TextWriter m_OldError`  

```csharp
private System.IO.TextWriter m_OldError;
```

- `private System.IO.StreamWriter m_Writer`  

```csharp
private System.IO.StreamWriter m_Writer;
```

- `private static const System.UInt32 ATTACH_PARENT_PROCESS`  

```csharp
private static const System.UInt32 ATTACH_PARENT_PROCESS;
```

- `private static const System.UInt32 ERROR_ACCESS_DENIED`  

```csharp
private static const System.UInt32 ERROR_ACCESS_DENIED;
```

- `private static const System.UInt32 GENERIC_WRITE`  

```csharp
private static const System.UInt32 GENERIC_WRITE;
```

- `private static const System.UInt32 GENERIC_READ`  

```csharp
private static const System.UInt32 GENERIC_READ;
```

- `private static const System.UInt32 FILE_SHARE_READ`  

```csharp
private static const System.UInt32 FILE_SHARE_READ;
```

- `private static const System.UInt32 FILE_SHARE_WRITE`  

```csharp
private static const System.UInt32 FILE_SHARE_WRITE;
```

- `private static const System.UInt32 OPEN_EXISTING`  

```csharp
private static const System.UInt32 OPEN_EXISTING;
```

- `private static const System.UInt32 FILE_ATTRIBUTE_NORMAL`  

```csharp
private static const System.UInt32 FILE_ATTRIBUTE_NORMAL;
```

- `private static const System.Int32 SC_CLOSE`  

```csharp
private static const System.Int32 SC_CLOSE;
```

- `private static const System.Int32 MF_BYCOMMAND`  

```csharp
private static const System.Int32 MF_BYCOMMAND;
```

- `private static const System.UInt32 STD_OUTPUT_HANDLE`  

```csharp
private static const System.UInt32 STD_OUTPUT_HANDLE;
```

- `private static const System.UInt32 ENABLE_VIRTUAL_TERMINAL_PROCESSING`  

```csharp
private static const System.UInt32 ENABLE_VIRTUAL_TERMINAL_PROCESSING;
```

- `public static const System.UInt16 FOREGROUND_BLUE`  

```csharp
public static const System.UInt16 FOREGROUND_BLUE;
```

- `public static const System.UInt16 FOREGROUND_GREEN`  

```csharp
public static const System.UInt16 FOREGROUND_GREEN;
```

- `public static const System.UInt16 FOREGROUND_RED`  

```csharp
public static const System.UInt16 FOREGROUND_RED;
```

- `public static const System.UInt16 FOREGROUND_INTENSITY`  

```csharp
public static const System.UInt16 FOREGROUND_INTENSITY;
```

- `public static const System.UInt16 BACKGROUND_BLUE`  

```csharp
public static const System.UInt16 BACKGROUND_BLUE;
```

- `public static const System.UInt16 BACKGROUND_GREEN`  

```csharp
public static const System.UInt16 BACKGROUND_GREEN;
```

- `public static const System.UInt16 BACKGROUND_RED`  

```csharp
public static const System.UInt16 BACKGROUND_RED;
```

- `public static const System.UInt16 BACKGROUND_INTENSITY`  

```csharp
public static const System.UInt16 BACKGROUND_INTENSITY;
```


## Constructors

- `public ConsoleWindow(System.String title, System.Boolean attachConsole = False)`  

```csharp
public ConsoleWindow(string title, bool attachConsole = false)
	{
		bool flag = true;
		if (attachConsole)
		{
			if (!AttachConsole(uint.MaxValue) && (long)Marshal.GetLastWin32Error() != 5)
			{
				flag = AllocConsole();
			}
			if (flag)
			{
				SetTitle(title);
				DeleteMenu(GetSystemMenu(GetConsoleWindow(), bRevert: false), 61536u, 0u);
			}
		}
		if (flag)
		{
			m_OldOutput = Console.Out;
			m_OldError = Console.Error;
			EnableVirtualTerminal(InitializeOutStream());
		}
	}
```


## Methods

- `private static AllocConsole() : System.Boolean`  

```csharp
private static System.Boolean AllocConsole();
```

- `private static AttachConsole(System.UInt32 dwProcessId) : System.Boolean`  

```csharp
private static System.Boolean AttachConsole(System.UInt32 dwProcessId);
```

- `private static CreateFileStream(System.String name, System.UInt32 win32DesiredAccess, System.UInt32 win32ShareMode, System.IO.FileAccess dotNetFileAccess) : System.IO.FileStream`  

```csharp
private static FileStream CreateFileStream(string name, uint win32DesiredAccess, uint win32ShareMode, FileAccess dotNetFileAccess)
	{
		SafeFileHandle safeFileHandle = new SafeFileHandle(CreateFileW(name, win32DesiredAccess, win32ShareMode, IntPtr.Zero, 3u, 128u, IntPtr.Zero), ownsHandle: true);
		if (!safeFileHandle.IsInvalid)
		{
			return new FileStream(safeFileHandle, dotNetFileAccess);
		}
		return null;
	}
```

- `private static CreateFileW(System.String lpFileName, System.UInt32 dwDesiredAccess, System.UInt32 dwShareMode, System.IntPtr lpSecurityAttributes, System.UInt32 dwCreationDisposition, System.UInt32 dwFlagsAndAttributes, System.IntPtr hTemplateFile) : System.IntPtr`  

```csharp
private static System.IntPtr CreateFileW(System.String lpFileName, System.UInt32 dwDesiredAccess, System.UInt32 dwShareMode, System.IntPtr lpSecurityAttributes, System.UInt32 dwCreationDisposition, System.UInt32 dwFlagsAndAttributes, System.IntPtr hTemplateFile);
```

- `private static DeleteMenu(System.IntPtr hMenu, System.UInt32 uPosition, System.UInt32 uFlags) : System.Boolean`  

```csharp
private static System.Boolean DeleteMenu(System.IntPtr hMenu, System.UInt32 uPosition, System.UInt32 uFlags);
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		Console.SetOut(m_OldOutput);
		Console.SetError(m_OldError);
		m_Writer.Dispose();
		FreeConsole();
	}
```

- `private static EnableVirtualTerminal() : System.Void`  

```csharp
private static void EnableVirtualTerminal(IntPtr handle)
	{
		if (handle != IntPtr.Zero && GetConsoleMode(handle, out var lpMode))
		{
			SetConsoleMode(handle, lpMode | 4);
		}
	}
```

- `private static EnableVirtualTerminal(System.IntPtr handle) : System.Void`  

```csharp
private static void EnableVirtualTerminal(IntPtr handle)
	{
		if (handle != IntPtr.Zero && GetConsoleMode(handle, out var lpMode))
		{
			SetConsoleMode(handle, lpMode | 4);
		}
	}
```

- `private static FreeConsole() : System.Boolean`  

```csharp
private static System.Boolean FreeConsole();
```

- `private static GetConsoleMode(System.IntPtr hConsoleHandle, System.UInt32& lpMode) : System.Boolean`  

```csharp
private static System.Boolean GetConsoleMode(System.IntPtr hConsoleHandle, System.UInt32& lpMode);
```

- `private static GetConsoleWindow() : System.IntPtr`  

```csharp
private static System.IntPtr GetConsoleWindow();
```

- `private static GetStdHandle(System.UInt32 nStdHandle) : System.IntPtr`  

```csharp
private static System.IntPtr GetStdHandle(System.UInt32 nStdHandle);
```

- `private static GetSystemMenu(System.IntPtr hWnd, System.Boolean bRevert) : System.IntPtr`  

```csharp
private static System.IntPtr GetSystemMenu(System.IntPtr hWnd, System.Boolean bRevert);
```

- `private InitializeInStream() : System.Void`  

```csharp
private void InitializeInStream()
	{
		FileStream fileStream = CreateFileStream("CONIN$", 2147483648u, 1u, FileAccess.Read);
		if (fileStream != null)
		{
			Console.SetIn(new StreamReader(fileStream));
		}
	}
```

- `private InitializeOutStream() : System.IntPtr`  

```csharp
private IntPtr InitializeOutStream()
	{
		FileStream fileStream = CreateFileStream("CONOUT$", 3221225472u, 2u, FileAccess.Write);
		if (fileStream != null)
		{
			m_Writer = new StreamWriter(fileStream)
			{
				AutoFlush = true
			};
			Console.SetOut(m_Writer);
			Console.SetError(m_Writer);
			return fileStream.SafeFileHandle.DangerousGetHandle();
		}
		return IntPtr.Zero;
	}
```

- `public static SetColor(System.UInt16 color) : System.Void`  

```csharp
public static void SetColor(ushort color)
	{
		SetConsoleTextAttribute(GetStdHandle(4294967285u), color);
	}
```

- `private static SetConsoleMode(System.IntPtr hConsoleHandle, System.UInt32 dwMode) : System.Boolean`  

```csharp
private static System.Boolean SetConsoleMode(System.IntPtr hConsoleHandle, System.UInt32 dwMode);
```

- `private static SetConsoleTextAttribute(System.IntPtr hConsoleOutput, System.UInt16 attributes) : System.Boolean`  

```csharp
private static System.Boolean SetConsoleTextAttribute(System.IntPtr hConsoleOutput, System.UInt16 attributes);
```

- `private static SetConsoleTitle(System.String lpConsoleTitle) : System.Boolean`  

```csharp
private static System.Boolean SetConsoleTitle(System.String lpConsoleTitle);
```

- `private static SetStdHandle(System.UInt32 nStdHandle, System.IntPtr handle) : System.Void`  

```csharp
private static System.Void SetStdHandle(System.UInt32 nStdHandle, System.IntPtr handle);
```

- `public SetTitle(System.String strName) : System.Void`  

```csharp
public void SetTitle(string strName)
	{
		SetConsoleTitle(strName);
	}
```


