# Colossal.Logging.UnityLogger

**Assembly:** `Colossal.Logging`  
**Namespace:** `Colossal.Logging`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Logging.ILog`, `System.IDisposable`  

## Code

```csharp
public sealed class UnityLogger : Colossal.Logging.ILog, System.IDisposable
{
    private System.Boolean m_NeedsAppend;
    private UnityEngine.ILogger unityLogger;
    private System.IO.FileStream m_Stream;
    private Colossal.Logging.UnityLogger+MultiStream m_StreamWriter;
    private Colossal.Logging.DateTimeFormatter m_DateTimeFormatter;
    private Colossal.Logging.Level m_Effectivenesslevel;
    private System.Boolean <showsErrorsInUI>k__BackingField;
    private Colossal.Logging.Level <showsStackTraceAboveLevels>k__BackingField;
    private System.String <logPath>k__BackingField;
    private System.String <name>k__BackingField;
    private System.Boolean <logStackTrace>k__BackingField;
    private System.Boolean <keepStreamOpen>k__BackingField;
    private System.Boolean <redirectToDefault>k__BackingField;
    private System.Boolean <disableBacktrace>k__BackingField;
    private Colossal.Indent <indent>k__BackingField;
    private static readonly Colossal.Logging.CustomLogHandler kCustomLogHandler;
    private static readonly System.Object _syncObject;

    public System.Boolean showsErrorsInUI { get; set; }
    public Colossal.Logging.Level showsStackTraceAboveLevels { get; set; }
    public System.String logPath { get; private set; }
    public System.String name { get; private set; }
    public System.Boolean logStackTrace { get; set; }
    public System.Boolean keepStreamOpen { get; set; }
    public System.Boolean redirectToDefault { get; set; }
    public System.Boolean disableBacktrace { get; set; }
    public static System.Boolean backtraceEnabled { get; set; }
    public Colossal.Indent indent { get; set; }
    public Colossal.Logging.Level effectivenessLevel { get; set; }
    public System.Boolean isDebugEnabled { get; }
    public System.Boolean isTraceEnabled { get; }
    public System.Boolean isVerboseEnabled { get; }
    public System.Boolean isInfoEnabled { get; }
    public System.Boolean isWarnEnabled { get; }
    public System.Boolean isErrorEnabled { get; }
    public System.Boolean isFatalEnabled { get; }
    public System.Boolean isValid { get; }
    public System.Boolean isOpen { get; }

    public UnityLogger(System.String name);

    private System.Void Close();
    private static UnityEngine.LogType ConvertLevel(Colossal.Logging.Level level);
    public Colossal.Logging.ILog Copy();
    public System.Void Critical(System.Exception exception);
    public System.Void Critical(System.Object message);
    public System.Void Critical(System.Exception exception, System.Object message);
    public System.Void Critical(UnityEngine.Object context, System.Object message);
    public System.Void Critical(UnityEngine.Object context, System.Exception exception);
    public System.Void Critical(UnityEngine.Object context, System.Exception exception, System.Object message);
    public System.Void CriticalFormat(System.String format, System.Object p1);
    public System.Void CriticalFormat(System.String format, System.Object p1, System.Object p2);
    public System.Void CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void CriticalFormat(System.String format, System.Object[] p);
    public System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1);
    public System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void CriticalFormat(System.Exception exception, System.String format, System.Object[] p);
    public System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
    public System.Void Debug(System.Exception exception);
    public System.Void Debug(System.Object message);
    public System.Void Debug(System.Exception exception, System.Object message);
    public System.Void Debug(UnityEngine.Object context, System.Object message);
    public System.Void Debug(UnityEngine.Object context, System.Exception exception);
    public System.Void Debug(UnityEngine.Object context, System.Exception exception, System.Object message);
    public System.Void DebugFormat(System.String format, System.Object p1);
    public System.Void DebugFormat(System.String format, System.Object p1, System.Object p2);
    public System.Void DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void DebugFormat(System.String format, System.Object[] p);
    public System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1);
    public System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void DebugFormat(System.Exception exception, System.String format, System.Object[] p);
    public System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
    public System.Void Dispose();
    public System.Void Emergency(System.Exception exception);
    public System.Void Emergency(System.Object message);
    public System.Void Emergency(System.Exception exception, System.Object message);
    public System.Void Emergency(UnityEngine.Object context, System.Object message);
    public System.Void Emergency(UnityEngine.Object context, System.Exception exception);
    public System.Void Emergency(UnityEngine.Object context, System.Exception exception, System.Object message);
    public System.Void EmergencyFormat(System.String format, System.Object p1);
    public System.Void EmergencyFormat(System.String format, System.Object p1, System.Object p2);
    public System.Void EmergencyFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void EmergencyFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void EmergencyFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void EmergencyFormat(System.String format, System.Object[] p);
    public System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1);
    public System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object[] p);
    public System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
    public System.Void Error(System.Exception exception);
    public System.Void Error(System.Object message);
    public System.Void Error(System.Exception exception, System.Object message);
    public System.Void Error(UnityEngine.Object context, System.Object message);
    public System.Void Error(UnityEngine.Object context, System.Exception exception);
    public System.Void Error(UnityEngine.Object context, System.Exception exception, System.Object message);
    public System.Void ErrorFormat(System.String format, System.Object p1);
    public System.Void ErrorFormat(System.String format, System.Object p1, System.Object p2);
    public System.Void ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void ErrorFormat(System.String format, System.Object[] p);
    public System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1);
    public System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void ErrorFormat(System.Exception exception, System.String format, System.Object[] p);
    public System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
    public System.Void Fatal(System.Exception exception);
    public System.Void Fatal(System.Object message);
    public System.Void Fatal(System.Exception exception, System.Object message);
    public System.Void Fatal(UnityEngine.Object context, System.Object message);
    public System.Void Fatal(UnityEngine.Object context, System.Exception exception);
    public System.Void Fatal(UnityEngine.Object context, System.Exception exception, System.Object message);
    public System.Void FatalFormat(System.String format, System.Object p1);
    public System.Void FatalFormat(System.String format, System.Object p1, System.Object p2);
    public System.Void FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void FatalFormat(System.String format, System.Object[] p);
    public System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1);
    public System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void FatalFormat(System.Exception exception, System.String format, System.Object[] p);
    public System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
    public System.Void Info(System.Exception exception);
    public System.Void Info(System.Object message);
    public System.Void Info(System.Exception exception, System.Object message);
    public System.Void Info(UnityEngine.Object context, System.Object message);
    public System.Void Info(UnityEngine.Object context, System.Exception exception);
    public System.Void Info(UnityEngine.Object context, System.Exception exception, System.Object message);
    public System.Void InfoFormat(System.String format, System.Object p1);
    public System.Void InfoFormat(System.String format, System.Object p1, System.Object p2);
    public System.Void InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void InfoFormat(System.String format, System.Object[] p);
    public System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1);
    public System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void InfoFormat(System.Exception exception, System.String format, System.Object[] p);
    public System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
    public System.Void Internal_WriteStream(UnityEngine.Object context, Colossal.Logging.Level level, System.String format, System.Exception exception, System.IO.TextWriter stdStream);
    public System.Boolean isLevelEnabled(Colossal.Logging.Level level);
    public System.Void Log(Colossal.Logging.Level level, System.String message, System.Exception exception);
    private System.Void Log(Colossal.Logging.Level level, System.String message, System.Exception exception, UnityEngine.Object context);
    private System.Void Open();
    public System.Void ReadSettings(Colossal.Logging.ILogSettingsProvider settingsProvider);
    public System.Void Trace(System.Exception exception);
    public System.Void Trace(System.Object message);
    public System.Void Trace(System.Exception exception, System.Object message);
    public System.Void Trace(UnityEngine.Object context, System.Object message);
    public System.Void Trace(UnityEngine.Object context, System.Exception exception);
    public System.Void Trace(UnityEngine.Object context, System.Exception exception, System.Object message);
    public System.Void TraceFormat(System.String format, System.Object p1);
    public System.Void TraceFormat(System.String format, System.Object p1, System.Object p2);
    public System.Void TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void TraceFormat(System.String format, System.Object[] p);
    public System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1);
    public System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void TraceFormat(System.Exception exception, System.String format, System.Object[] p);
    public System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
    public System.Void Verbose(System.Exception exception);
    public System.Void Verbose(System.Object message);
    public System.Void Verbose(System.Exception exception, System.Object message);
    public System.Void Verbose(UnityEngine.Object context, System.Object message);
    public System.Void Verbose(UnityEngine.Object context, System.Exception exception);
    public System.Void Verbose(UnityEngine.Object context, System.Exception exception, System.Object message);
    public System.Void VerboseFormat(System.String format, System.Object p1);
    public System.Void VerboseFormat(System.String format, System.Object p1, System.Object p2);
    public System.Void VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void VerboseFormat(System.String format, System.Object[] p);
    public System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1);
    public System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void VerboseFormat(System.Exception exception, System.String format, System.Object[] p);
    public System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
    public System.Void Warn(System.Exception exception);
    public System.Void Warn(System.Object message);
    public System.Void Warn(System.Exception exception, System.Object message);
    public System.Void Warn(UnityEngine.Object context, System.Object message);
    public System.Void Warn(UnityEngine.Object context, System.Exception exception);
    public System.Void Warn(UnityEngine.Object context, System.Exception exception, System.Object message);
    public System.Void WarnFormat(System.String format, System.Object p1);
    public System.Void WarnFormat(System.String format, System.Object p1, System.Object p2);
    public System.Void WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void WarnFormat(System.String format, System.Object[] p);
    public System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1);
    public System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void WarnFormat(System.Exception exception, System.String format, System.Object[] p);
    public System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
}
```


## Fields

- `private System.Boolean m_NeedsAppend`  

```csharp
private System.Boolean m_NeedsAppend;
```

- `private UnityEngine.ILogger unityLogger`  

```csharp
private UnityEngine.ILogger unityLogger;
```

- `private System.IO.FileStream m_Stream`  

```csharp
private System.IO.FileStream m_Stream;
```

- `private Colossal.Logging.UnityLogger+MultiStream m_StreamWriter`  

```csharp
private Colossal.Logging.UnityLogger+MultiStream m_StreamWriter;
```

- `private Colossal.Logging.DateTimeFormatter m_DateTimeFormatter`  

```csharp
private Colossal.Logging.DateTimeFormatter m_DateTimeFormatter;
```

- `private Colossal.Logging.Level m_Effectivenesslevel`  

```csharp
private Colossal.Logging.Level m_Effectivenesslevel;
```

- `private System.Boolean <showsErrorsInUI>k__BackingField`  

```csharp
private System.Boolean <showsErrorsInUI>k__BackingField;
```

- `private Colossal.Logging.Level <showsStackTraceAboveLevels>k__BackingField`  

```csharp
private Colossal.Logging.Level <showsStackTraceAboveLevels>k__BackingField;
```

- `private System.String <logPath>k__BackingField`  

```csharp
private System.String <logPath>k__BackingField;
```

- `private System.String <name>k__BackingField`  

```csharp
private System.String <name>k__BackingField;
```

- `private System.Boolean <logStackTrace>k__BackingField`  

```csharp
private System.Boolean <logStackTrace>k__BackingField;
```

- `private System.Boolean <keepStreamOpen>k__BackingField`  

```csharp
private System.Boolean <keepStreamOpen>k__BackingField;
```

- `private System.Boolean <redirectToDefault>k__BackingField`  

```csharp
private System.Boolean <redirectToDefault>k__BackingField;
```

- `private System.Boolean <disableBacktrace>k__BackingField`  

```csharp
private System.Boolean <disableBacktrace>k__BackingField;
```

- `private Colossal.Indent <indent>k__BackingField`  

```csharp
private Colossal.Indent <indent>k__BackingField;
```

- `private static readonly Colossal.Logging.CustomLogHandler kCustomLogHandler`  

```csharp
private static readonly Colossal.Logging.CustomLogHandler kCustomLogHandler;
```

- `private static readonly System.Object _syncObject`  

```csharp
private static readonly System.Object _syncObject;
```


## Properties

- `public System.Boolean showsErrorsInUI { get; set }`  

```csharp
public System.Boolean showsErrorsInUI { get; set; }
```

- `public Colossal.Logging.Level showsStackTraceAboveLevels { get; set }`  

```csharp
public Colossal.Logging.Level showsStackTraceAboveLevels { get; set; }
```

- `public System.String logPath { get; private set }`  

```csharp
public System.String logPath { get; private set; }
```

- `public System.String name { get; private set }`  

```csharp
public System.String name { get; private set; }
```

- `public System.Boolean logStackTrace { get; set }`  

```csharp
public System.Boolean logStackTrace { get; set; }
```

- `public System.Boolean keepStreamOpen { get; set }`  

```csharp
public System.Boolean keepStreamOpen { get; set; }
```

- `public System.Boolean redirectToDefault { get; set }`  

```csharp
public System.Boolean redirectToDefault { get; set; }
```

- `public System.Boolean disableBacktrace { get; set }`  

```csharp
public System.Boolean disableBacktrace { get; set; }
```

- `public static System.Boolean backtraceEnabled { get; set }`  

```csharp
public static System.Boolean backtraceEnabled { get; set; }
```

- `public Colossal.Indent indent { get; set }`  

```csharp
public Colossal.Indent indent { get; set; }
```

- `public Colossal.Logging.Level effectivenessLevel { get; set }`  

```csharp
public Colossal.Logging.Level effectivenessLevel { get; set; }
```

- `public System.Boolean isDebugEnabled { get }`  

```csharp
public System.Boolean isDebugEnabled { get; }
```

- `public System.Boolean isTraceEnabled { get }`  

```csharp
public System.Boolean isTraceEnabled { get; }
```

- `public System.Boolean isVerboseEnabled { get }`  

```csharp
public System.Boolean isVerboseEnabled { get; }
```

- `public System.Boolean isInfoEnabled { get }`  

```csharp
public System.Boolean isInfoEnabled { get; }
```

- `public System.Boolean isWarnEnabled { get }`  

```csharp
public System.Boolean isWarnEnabled { get; }
```

- `public System.Boolean isErrorEnabled { get }`  

```csharp
public System.Boolean isErrorEnabled { get; }
```

- `public System.Boolean isFatalEnabled { get }`  

```csharp
public System.Boolean isFatalEnabled { get; }
```

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```

- `public System.Boolean isOpen { get }`  

```csharp
public System.Boolean isOpen { get; }
```


## Constructors

- `public UnityLogger(System.String name)`  

```csharp
public UnityLogger(System.String name);
```


## Methods

- `private Close() : System.Void`  

```csharp
private System.Void Close();
```

- `private static ConvertLevel(Colossal.Logging.Level level) : UnityEngine.LogType`  

```csharp
private static UnityEngine.LogType ConvertLevel(Colossal.Logging.Level level);
```

- `public Copy() : Colossal.Logging.ILog`  

```csharp
public Colossal.Logging.ILog Copy();
```

- `public Critical(System.Exception exception) : System.Void`  

```csharp
public System.Void Critical(System.Exception exception);
```

- `public Critical(System.Object message) : System.Void`  

```csharp
public System.Void Critical(System.Object message);
```

- `public Critical(System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Critical(System.Exception exception, System.Object message);
```

- `public Critical(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public System.Void Critical(UnityEngine.Object context, System.Object message);
```

- `public Critical(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public System.Void Critical(UnityEngine.Object context, System.Exception exception);
```

- `public Critical(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Critical(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public CriticalFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void CriticalFormat(System.String format, System.Object p1);
```

- `public CriticalFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void CriticalFormat(System.String format, System.Object p1, System.Object p2);
```

- `public CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public CriticalFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void CriticalFormat(System.String format, System.Object[] p);
```

- `public CriticalFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public CriticalFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void CriticalFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public CriticalFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```

- `public Debug(System.Exception exception) : System.Void`  

```csharp
public System.Void Debug(System.Exception exception);
```

- `public Debug(System.Object message) : System.Void`  

```csharp
public System.Void Debug(System.Object message);
```

- `public Debug(System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Debug(System.Exception exception, System.Object message);
```

- `public Debug(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public System.Void Debug(UnityEngine.Object context, System.Object message);
```

- `public Debug(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public System.Void Debug(UnityEngine.Object context, System.Exception exception);
```

- `public Debug(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Debug(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public DebugFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void DebugFormat(System.String format, System.Object p1);
```

- `public DebugFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void DebugFormat(System.String format, System.Object p1, System.Object p2);
```

- `public DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public DebugFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void DebugFormat(System.String format, System.Object[] p);
```

- `public DebugFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public DebugFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void DebugFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public DebugFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public DebugFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Emergency(System.Exception exception) : System.Void`  

```csharp
public System.Void Emergency(System.Exception exception);
```

- `public Emergency(System.Object message) : System.Void`  

```csharp
public System.Void Emergency(System.Object message);
```

- `public Emergency(System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Emergency(System.Exception exception, System.Object message);
```

- `public Emergency(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public System.Void Emergency(UnityEngine.Object context, System.Object message);
```

- `public Emergency(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public System.Void Emergency(UnityEngine.Object context, System.Exception exception);
```

- `public Emergency(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Emergency(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public EmergencyFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void EmergencyFormat(System.String format, System.Object p1);
```

- `public EmergencyFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void EmergencyFormat(System.String format, System.Object p1, System.Object p2);
```

- `public EmergencyFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void EmergencyFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public EmergencyFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void EmergencyFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public EmergencyFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void EmergencyFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public EmergencyFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void EmergencyFormat(System.String format, System.Object[] p);
```

- `public EmergencyFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public EmergencyFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public EmergencyFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```

- `public Error(System.Exception exception) : System.Void`  

```csharp
public System.Void Error(System.Exception exception);
```

- `public Error(System.Object message) : System.Void`  

```csharp
public System.Void Error(System.Object message);
```

- `public Error(System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Error(System.Exception exception, System.Object message);
```

- `public Error(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public System.Void Error(UnityEngine.Object context, System.Object message);
```

- `public Error(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public System.Void Error(UnityEngine.Object context, System.Exception exception);
```

- `public Error(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Error(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public ErrorFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void ErrorFormat(System.String format, System.Object p1);
```

- `public ErrorFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void ErrorFormat(System.String format, System.Object p1, System.Object p2);
```

- `public ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public ErrorFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void ErrorFormat(System.String format, System.Object[] p);
```

- `public ErrorFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public ErrorFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void ErrorFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public ErrorFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```

- `public Fatal(System.Exception exception) : System.Void`  

```csharp
public System.Void Fatal(System.Exception exception);
```

- `public Fatal(System.Object message) : System.Void`  

```csharp
public System.Void Fatal(System.Object message);
```

- `public Fatal(System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Fatal(System.Exception exception, System.Object message);
```

- `public Fatal(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public System.Void Fatal(UnityEngine.Object context, System.Object message);
```

- `public Fatal(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public System.Void Fatal(UnityEngine.Object context, System.Exception exception);
```

- `public Fatal(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Fatal(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public FatalFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void FatalFormat(System.String format, System.Object p1);
```

- `public FatalFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void FatalFormat(System.String format, System.Object p1, System.Object p2);
```

- `public FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public FatalFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void FatalFormat(System.String format, System.Object[] p);
```

- `public FatalFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public FatalFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void FatalFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public FatalFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public FatalFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```

- `public Info(System.Exception exception) : System.Void`  

```csharp
public System.Void Info(System.Exception exception);
```

- `public Info(System.Object message) : System.Void`  

```csharp
public System.Void Info(System.Object message);
```

- `public Info(System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Info(System.Exception exception, System.Object message);
```

- `public Info(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public System.Void Info(UnityEngine.Object context, System.Object message);
```

- `public Info(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public System.Void Info(UnityEngine.Object context, System.Exception exception);
```

- `public Info(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Info(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public InfoFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void InfoFormat(System.String format, System.Object p1);
```

- `public InfoFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void InfoFormat(System.String format, System.Object p1, System.Object p2);
```

- `public InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public InfoFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void InfoFormat(System.String format, System.Object[] p);
```

- `public InfoFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public InfoFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void InfoFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public InfoFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public InfoFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```

- `public Internal_WriteStream(UnityEngine.Object context, Colossal.Logging.Level level, System.String format, System.Exception exception, System.IO.TextWriter stdStream) : System.Void`  

```csharp
public System.Void Internal_WriteStream(UnityEngine.Object context, Colossal.Logging.Level level, System.String format, System.Exception exception, System.IO.TextWriter stdStream);
```

- `public isLevelEnabled(Colossal.Logging.Level level) : System.Boolean`  

```csharp
public System.Boolean isLevelEnabled(Colossal.Logging.Level level);
```

- `public Log(Colossal.Logging.Level level, System.String message, System.Exception exception) : System.Void`  

```csharp
public System.Void Log(Colossal.Logging.Level level, System.String message, System.Exception exception);
```

- `private Log(Colossal.Logging.Level level, System.String message, System.Exception exception, UnityEngine.Object context) : System.Void`  

```csharp
private System.Void Log(Colossal.Logging.Level level, System.String message, System.Exception exception, UnityEngine.Object context);
```

- `private Open() : System.Void`  

```csharp
private System.Void Open();
```

- `public ReadSettings(Colossal.Logging.ILogSettingsProvider settingsProvider) : System.Void`  

```csharp
public System.Void ReadSettings(Colossal.Logging.ILogSettingsProvider settingsProvider);
```

- `public Trace(System.Exception exception) : System.Void`  

```csharp
public System.Void Trace(System.Exception exception);
```

- `public Trace(System.Object message) : System.Void`  

```csharp
public System.Void Trace(System.Object message);
```

- `public Trace(System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Trace(System.Exception exception, System.Object message);
```

- `public Trace(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public System.Void Trace(UnityEngine.Object context, System.Object message);
```

- `public Trace(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public System.Void Trace(UnityEngine.Object context, System.Exception exception);
```

- `public Trace(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Trace(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public TraceFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void TraceFormat(System.String format, System.Object p1);
```

- `public TraceFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void TraceFormat(System.String format, System.Object p1, System.Object p2);
```

- `public TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public TraceFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void TraceFormat(System.String format, System.Object[] p);
```

- `public TraceFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public TraceFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void TraceFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public TraceFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public TraceFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```

- `public Verbose(System.Exception exception) : System.Void`  

```csharp
public System.Void Verbose(System.Exception exception);
```

- `public Verbose(System.Object message) : System.Void`  

```csharp
public System.Void Verbose(System.Object message);
```

- `public Verbose(System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Verbose(System.Exception exception, System.Object message);
```

- `public Verbose(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public System.Void Verbose(UnityEngine.Object context, System.Object message);
```

- `public Verbose(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public System.Void Verbose(UnityEngine.Object context, System.Exception exception);
```

- `public Verbose(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Verbose(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public VerboseFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void VerboseFormat(System.String format, System.Object p1);
```

- `public VerboseFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void VerboseFormat(System.String format, System.Object p1, System.Object p2);
```

- `public VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public VerboseFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void VerboseFormat(System.String format, System.Object[] p);
```

- `public VerboseFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public VerboseFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void VerboseFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public VerboseFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```

- `public Warn(System.Exception exception) : System.Void`  

```csharp
public System.Void Warn(System.Exception exception);
```

- `public Warn(System.Object message) : System.Void`  

```csharp
public System.Void Warn(System.Object message);
```

- `public Warn(System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Warn(System.Exception exception, System.Object message);
```

- `public Warn(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public System.Void Warn(UnityEngine.Object context, System.Object message);
```

- `public Warn(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public System.Void Warn(UnityEngine.Object context, System.Exception exception);
```

- `public Warn(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public System.Void Warn(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public WarnFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void WarnFormat(System.String format, System.Object p1);
```

- `public WarnFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void WarnFormat(System.String format, System.Object p1, System.Object p2);
```

- `public WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public WarnFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void WarnFormat(System.String format, System.Object[] p);
```

- `public WarnFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public WarnFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void WarnFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public WarnFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public WarnFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```


## Events

- `OnException` : `System.Action<System.Exception, UnityEngine.Object>`  

```csharp
public event System.Action<System.Exception, UnityEngine.Object> OnException;
```

- `OnMessage` : `System.Action<Colossal.Logging.ILog, Colossal.Logging.Level, System.String, System.Exception, UnityEngine.Object>`  

```csharp
public event System.Action<Colossal.Logging.ILog, Colossal.Logging.Level, System.String, System.Exception, UnityEngine.Object> OnMessage;
```

- `OnErrorOrHigher` : `System.Action<Colossal.Logging.ILog, Colossal.Logging.Level, System.String, System.Exception, UnityEngine.Object>`  

```csharp
public event System.Action<Colossal.Logging.ILog, Colossal.Logging.Level, System.String, System.Exception, UnityEngine.Object> OnErrorOrHigher;
```

- `OnWarnOrHigher` : `System.Action<Colossal.Logging.ILog, Colossal.Logging.Level, System.String, System.Exception, UnityEngine.Object>`  

```csharp
public event System.Action<Colossal.Logging.ILog, Colossal.Logging.Level, System.String, System.Exception, UnityEngine.Object> OnWarnOrHigher;
```


## Nested types

- `Colossal.Logging.UnityLogger+MultiStream`  

