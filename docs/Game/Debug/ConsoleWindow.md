# Game.Debug.ConsoleWindow

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.IO.TextWriter m_OldOutput`  
- `private System.IO.TextWriter m_OldError`  
- `private System.IO.StreamWriter m_Writer`  
- `private static const System.UInt32 ATTACH_PARENT_PROCESS`  
- `private static const System.UInt32 ERROR_ACCESS_DENIED`  
- `private static const System.UInt32 GENERIC_WRITE`  
- `private static const System.UInt32 GENERIC_READ`  
- `private static const System.UInt32 FILE_SHARE_READ`  
- `private static const System.UInt32 FILE_SHARE_WRITE`  
- `private static const System.UInt32 OPEN_EXISTING`  
- `private static const System.UInt32 FILE_ATTRIBUTE_NORMAL`  
- `private static const System.Int32 SC_CLOSE`  
- `private static const System.Int32 MF_BYCOMMAND`  
- `private static const System.UInt32 STD_OUTPUT_HANDLE`  
- `private static const System.UInt32 ENABLE_VIRTUAL_TERMINAL_PROCESSING`  
- `public static const System.UInt16 FOREGROUND_BLUE`  
- `public static const System.UInt16 FOREGROUND_GREEN`  
- `public static const System.UInt16 FOREGROUND_RED`  
- `public static const System.UInt16 FOREGROUND_INTENSITY`  
- `public static const System.UInt16 BACKGROUND_BLUE`  
- `public static const System.UInt16 BACKGROUND_GREEN`  
- `public static const System.UInt16 BACKGROUND_RED`  
- `public static const System.UInt16 BACKGROUND_INTENSITY`  

## Constructors

- `public ConsoleWindow(System.String title, System.Boolean attachConsole = False)`  

## Methods

- `private static AllocConsole() : System.Boolean`  
- `private static AttachConsole(System.UInt32 dwProcessId) : System.Boolean`  
- `private static CreateFileStream(System.String name, System.UInt32 win32DesiredAccess, System.UInt32 win32ShareMode, System.IO.FileAccess dotNetFileAccess) : System.IO.FileStream`  
- `private static CreateFileW(System.String lpFileName, System.UInt32 dwDesiredAccess, System.UInt32 dwShareMode, System.IntPtr lpSecurityAttributes, System.UInt32 dwCreationDisposition, System.UInt32 dwFlagsAndAttributes, System.IntPtr hTemplateFile) : System.IntPtr`  
- `private static DeleteMenu(System.IntPtr hMenu, System.UInt32 uPosition, System.UInt32 uFlags) : System.Boolean`  
- `public Dispose() : System.Void`  
- `private static EnableVirtualTerminal() : System.Void`  
- `private static EnableVirtualTerminal(System.IntPtr handle) : System.Void`  
- `private static FreeConsole() : System.Boolean`  
- `private static GetConsoleMode(System.IntPtr hConsoleHandle, System.UInt32& lpMode) : System.Boolean`  
- `private static GetConsoleWindow() : System.IntPtr`  
- `private static GetStdHandle(System.UInt32 nStdHandle) : System.IntPtr`  
- `private static GetSystemMenu(System.IntPtr hWnd, System.Boolean bRevert) : System.IntPtr`  
- `private InitializeInStream() : System.Void`  
- `private InitializeOutStream() : System.IntPtr`  
- `public static SetColor(System.UInt16 color) : System.Void`  
- `private static SetConsoleMode(System.IntPtr hConsoleHandle, System.UInt32 dwMode) : System.Boolean`  
- `private static SetConsoleTextAttribute(System.IntPtr hConsoleOutput, System.UInt16 attributes) : System.Boolean`  
- `private static SetConsoleTitle(System.String lpConsoleTitle) : System.Boolean`  
- `private static SetStdHandle(System.UInt32 nStdHandle, System.IntPtr handle) : System.Void`  
- `public SetTitle(System.String strName) : System.Void`  

