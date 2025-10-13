# Colossal.Logging.ILog

**Assembly:** `Colossal.Logging`  
**Namespace:** `Colossal.Logging`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`  

## Code

```csharp
public abstract interface ILog : System.IDisposable
{
    public Colossal.Indent indent { get; set; }
    public System.String name { get; }
    public System.String logPath { get; }
    public System.Boolean showsErrorsInUI { get; set; }
    public Colossal.Logging.Level showsStackTraceAboveLevels { get; set; }
    public System.Boolean isDebugEnabled { get; }
    public System.Boolean isTraceEnabled { get; }
    public System.Boolean isVerboseEnabled { get; }
    public System.Boolean isInfoEnabled { get; }
    public System.Boolean isWarnEnabled { get; }
    public System.Boolean isErrorEnabled { get; }
    public System.Boolean isFatalEnabled { get; }
    public System.Boolean disableBacktrace { get; set; }
    public System.Boolean keepStreamOpen { get; set; }
    public System.Boolean redirectToDefault { get; set; }
    public Colossal.Logging.ILog+StackTraceScope stackTraceScoped { get; }
    public Colossal.Logging.Level effectivenessLevel { get; set; }
    public System.Boolean logStackTrace { get; set; }

    public abstract Colossal.Logging.ILog Copy();
    public abstract System.Void Critical(System.Exception exception);
    public abstract System.Void Critical(System.Object message);
    public abstract System.Void Critical(System.Exception exception, System.Object message);
    public abstract System.Void Critical(UnityEngine.Object context, System.Object message);
    public abstract System.Void Critical(UnityEngine.Object context, System.Exception exception);
    public abstract System.Void Critical(UnityEngine.Object context, System.Exception exception, System.Object message);
    public abstract System.Void CriticalFormat(System.String format, System.Object p1);
    public abstract System.Void CriticalFormat(System.String format, System.Object p1, System.Object p2);
    public abstract System.Void CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void CriticalFormat(System.String format, System.Object[] p);
    public abstract System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void CriticalFormat(System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public abstract System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public abstract System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void Debug(System.Exception exception);
    public abstract System.Void Debug(System.Object message);
    public abstract System.Void Debug(System.Exception exception, System.Object message);
    public abstract System.Void Debug(UnityEngine.Object context, System.Object message);
    public abstract System.Void Debug(UnityEngine.Object context, System.Exception exception);
    public abstract System.Void Debug(UnityEngine.Object context, System.Exception exception, System.Object message);
    public abstract System.Void DebugFormat(System.String format, System.Object p1);
    public abstract System.Void DebugFormat(System.String format, System.Object p1, System.Object p2);
    public abstract System.Void DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void DebugFormat(System.String format, System.Object[] p);
    public abstract System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void DebugFormat(System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public abstract System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public abstract System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void Emergency(System.Exception exception);
    public abstract System.Void Emergency(System.Object message);
    public abstract System.Void Emergency(System.Exception exception, System.Object message);
    public abstract System.Void Emergency(UnityEngine.Object context, System.Object message);
    public abstract System.Void Emergency(UnityEngine.Object context, System.Exception exception);
    public abstract System.Void Emergency(UnityEngine.Object context, System.Exception exception, System.Object message);
    public abstract System.Void EmergencyFormat(System.String format, System.Object[] p);
    public abstract System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void Error(System.Exception exception);
    public abstract System.Void Error(System.Object message);
    public abstract System.Void Error(System.Exception exception, System.Object message);
    public abstract System.Void Error(UnityEngine.Object context, System.Object message);
    public abstract System.Void Error(UnityEngine.Object context, System.Exception exception);
    public abstract System.Void Error(UnityEngine.Object context, System.Exception exception, System.Object message);
    public abstract System.Void ErrorFormat(System.String format, System.Object p1);
    public abstract System.Void ErrorFormat(System.String format, System.Object p1, System.Object p2);
    public abstract System.Void ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void ErrorFormat(System.String format, System.Object[] p);
    public abstract System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void ErrorFormat(System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public abstract System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public abstract System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void Fatal(System.Exception exception);
    public abstract System.Void Fatal(System.Object message);
    public abstract System.Void Fatal(System.Exception exception, System.Object message);
    public abstract System.Void Fatal(UnityEngine.Object context, System.Object message);
    public abstract System.Void Fatal(UnityEngine.Object context, System.Exception exception);
    public abstract System.Void Fatal(UnityEngine.Object context, System.Exception exception, System.Object message);
    public abstract System.Void FatalFormat(System.String format, System.Object p1);
    public abstract System.Void FatalFormat(System.String format, System.Object p1, System.Object p2);
    public abstract System.Void FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void FatalFormat(System.String format, System.Object[] p);
    public abstract System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void FatalFormat(System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public abstract System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public abstract System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void Info(System.Exception exception);
    public abstract System.Void Info(System.Object message);
    public abstract System.Void Info(System.Exception exception, System.Object message);
    public abstract System.Void Info(UnityEngine.Object context, System.Object message);
    public abstract System.Void Info(UnityEngine.Object context, System.Exception exception);
    public abstract System.Void Info(UnityEngine.Object context, System.Exception exception, System.Object message);
    public abstract System.Void InfoFormat(System.String format, System.Object p1);
    public abstract System.Void InfoFormat(System.String format, System.Object p1, System.Object p2);
    public abstract System.Void InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void InfoFormat(System.String format, System.Object[] p);
    public abstract System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void InfoFormat(System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public abstract System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public abstract System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void Internal_WriteStream(UnityEngine.Object context, Colossal.Logging.Level level, System.String format, System.Exception exception, System.IO.TextWriter stdStream);
    public abstract System.Boolean isLevelEnabled(Colossal.Logging.Level level);
    public abstract System.Void Log(Colossal.Logging.Level level, System.String message, System.Exception exception);
    public abstract System.Void ReadSettings(Colossal.Logging.ILogSettingsProvider provider);
    public virtual Colossal.Logging.ILog SetBacktraceEnabled(System.Boolean backtraceEnabled);
    public virtual Colossal.Logging.ILog SetEffectiveness(Colossal.Logging.Level effectivenessLevel);
    public virtual Colossal.Logging.ILog SetLogStackTrace(System.Boolean logStackTrace);
    public virtual Colossal.Logging.ILog SetRedirectToDefault(System.Boolean redirectToDefault);
    public virtual Colossal.Logging.ILog SetShowsErrorsInUI(System.Boolean showsErrorsInUI);
    public virtual Colossal.Logging.ILog SetShowsStackTraceAboveLevels(Colossal.Logging.Level showsStackTraceAboveLevels);
    public abstract System.Void Trace(System.Exception exception);
    public abstract System.Void Trace(System.Object message);
    public abstract System.Void Trace(System.Exception exception, System.Object message);
    public abstract System.Void Trace(UnityEngine.Object context, System.Object message);
    public abstract System.Void Trace(UnityEngine.Object context, System.Exception exception);
    public abstract System.Void Trace(UnityEngine.Object context, System.Exception exception, System.Object message);
    public abstract System.Void TraceFormat(System.String format, System.Object p1);
    public abstract System.Void TraceFormat(System.String format, System.Object p1, System.Object p2);
    public abstract System.Void TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void TraceFormat(System.String format, System.Object[] p);
    public abstract System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void TraceFormat(System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public abstract System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public abstract System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void Verbose(System.Exception exception);
    public abstract System.Void Verbose(System.Object message);
    public abstract System.Void Verbose(System.Exception exception, System.Object message);
    public abstract System.Void Verbose(UnityEngine.Object context, System.Object message);
    public abstract System.Void Verbose(UnityEngine.Object context, System.Exception exception);
    public abstract System.Void Verbose(UnityEngine.Object context, System.Exception exception, System.Object message);
    public abstract System.Void VerboseFormat(System.String format, System.Object p1);
    public abstract System.Void VerboseFormat(System.String format, System.Object p1, System.Object p2);
    public abstract System.Void VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void VerboseFormat(System.String format, System.Object[] p);
    public abstract System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void VerboseFormat(System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public abstract System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public abstract System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void Warn(System.Exception exception);
    public abstract System.Void Warn(System.Object message);
    public abstract System.Void Warn(System.Exception exception, System.Object message);
    public abstract System.Void Warn(UnityEngine.Object context, System.Object message);
    public abstract System.Void Warn(UnityEngine.Object context, System.Exception exception);
    public abstract System.Void Warn(UnityEngine.Object context, System.Exception exception, System.Object message);
    public abstract System.Void WarnFormat(System.String format, System.Object p1);
    public abstract System.Void WarnFormat(System.String format, System.Object p1, System.Object p2);
    public abstract System.Void WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void WarnFormat(System.String format, System.Object[] p);
    public abstract System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void WarnFormat(System.Exception exception, System.String format, System.Object[] p);
    public abstract System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1);
    public abstract System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object[] p);
    public abstract System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
    public abstract System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
    public abstract System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
    public abstract System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
    public abstract System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
    public abstract System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
}
```


## Properties

- `public Colossal.Indent indent { get; set }`  

```csharp
public Colossal.Indent indent { get; set; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.String logPath { get }`  

```csharp
public System.String logPath { get; }
```

- `public System.Boolean showsErrorsInUI { get; set }`  

```csharp
public System.Boolean showsErrorsInUI { get; set; }
```

- `public Colossal.Logging.Level showsStackTraceAboveLevels { get; set }`  

```csharp
public Colossal.Logging.Level showsStackTraceAboveLevels { get; set; }
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

- `public System.Boolean disableBacktrace { get; set }`  

```csharp
public System.Boolean disableBacktrace { get; set; }
```

- `public System.Boolean keepStreamOpen { get; set }`  

```csharp
public System.Boolean keepStreamOpen { get; set; }
```

- `public System.Boolean redirectToDefault { get; set }`  

```csharp
public System.Boolean redirectToDefault { get; set; }
```

- `public Colossal.Logging.ILog+StackTraceScope stackTraceScoped { get }`  

```csharp
public Colossal.Logging.ILog+StackTraceScope stackTraceScoped { get; }
```

- `public Colossal.Logging.Level effectivenessLevel { get; set }`  

```csharp
public Colossal.Logging.Level effectivenessLevel { get; set; }
```

- `public System.Boolean logStackTrace { get; set }`  

```csharp
public System.Boolean logStackTrace { get; set; }
```


## Methods

- `public abstract Copy() : Colossal.Logging.ILog`  

```csharp
public abstract Colossal.Logging.ILog Copy();
```

- `public abstract Critical(System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Critical(System.Exception exception);
```

- `public abstract Critical(System.Object message) : System.Void`  

```csharp
public abstract System.Void Critical(System.Object message);
```

- `public abstract Critical(System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Critical(System.Exception exception, System.Object message);
```

- `public abstract Critical(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public abstract System.Void Critical(UnityEngine.Object context, System.Object message);
```

- `public abstract Critical(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Critical(UnityEngine.Object context, System.Exception exception);
```

- `public abstract Critical(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Critical(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public abstract CriticalFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(System.String format, System.Object p1);
```

- `public abstract CriticalFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(System.String format, System.Object p1, System.Object p2);
```

- `public abstract CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract CriticalFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(System.String format, System.Object[] p);
```

- `public abstract CriticalFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public abstract CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract CriticalFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public abstract CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public abstract CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract CriticalFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public abstract CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public abstract CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void CriticalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract Debug(System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Debug(System.Exception exception);
```

- `public abstract Debug(System.Object message) : System.Void`  

```csharp
public abstract System.Void Debug(System.Object message);
```

- `public abstract Debug(System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Debug(System.Exception exception, System.Object message);
```

- `public abstract Debug(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public abstract System.Void Debug(UnityEngine.Object context, System.Object message);
```

- `public abstract Debug(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Debug(UnityEngine.Object context, System.Exception exception);
```

- `public abstract Debug(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Debug(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public abstract DebugFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void DebugFormat(System.String format, System.Object p1);
```

- `public abstract DebugFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void DebugFormat(System.String format, System.Object p1, System.Object p2);
```

- `public abstract DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void DebugFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract DebugFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void DebugFormat(System.String format, System.Object[] p);
```

- `public abstract DebugFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public abstract DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void DebugFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract DebugFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void DebugFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract DebugFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public abstract DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public abstract DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract DebugFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void DebugFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public abstract DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public abstract DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void DebugFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract Emergency(System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Emergency(System.Exception exception);
```

- `public abstract Emergency(System.Object message) : System.Void`  

```csharp
public abstract System.Void Emergency(System.Object message);
```

- `public abstract Emergency(System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Emergency(System.Exception exception, System.Object message);
```

- `public abstract Emergency(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public abstract System.Void Emergency(UnityEngine.Object context, System.Object message);
```

- `public abstract Emergency(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Emergency(UnityEngine.Object context, System.Exception exception);
```

- `public abstract Emergency(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Emergency(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public abstract EmergencyFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(System.String format, System.Object[] p);
```

- `public abstract EmergencyFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public abstract EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract EmergencyFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public abstract EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public abstract EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract EmergencyFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public abstract EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public abstract EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void EmergencyFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract Error(System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Error(System.Exception exception);
```

- `public abstract Error(System.Object message) : System.Void`  

```csharp
public abstract System.Void Error(System.Object message);
```

- `public abstract Error(System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Error(System.Exception exception, System.Object message);
```

- `public abstract Error(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public abstract System.Void Error(UnityEngine.Object context, System.Object message);
```

- `public abstract Error(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Error(UnityEngine.Object context, System.Exception exception);
```

- `public abstract Error(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Error(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public abstract ErrorFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(System.String format, System.Object p1);
```

- `public abstract ErrorFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(System.String format, System.Object p1, System.Object p2);
```

- `public abstract ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract ErrorFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(System.String format, System.Object[] p);
```

- `public abstract ErrorFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public abstract ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract ErrorFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public abstract ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public abstract ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract ErrorFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public abstract ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public abstract ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void ErrorFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract Fatal(System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Fatal(System.Exception exception);
```

- `public abstract Fatal(System.Object message) : System.Void`  

```csharp
public abstract System.Void Fatal(System.Object message);
```

- `public abstract Fatal(System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Fatal(System.Exception exception, System.Object message);
```

- `public abstract Fatal(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public abstract System.Void Fatal(UnityEngine.Object context, System.Object message);
```

- `public abstract Fatal(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Fatal(UnityEngine.Object context, System.Exception exception);
```

- `public abstract Fatal(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Fatal(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public abstract FatalFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void FatalFormat(System.String format, System.Object p1);
```

- `public abstract FatalFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void FatalFormat(System.String format, System.Object p1, System.Object p2);
```

- `public abstract FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void FatalFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract FatalFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void FatalFormat(System.String format, System.Object[] p);
```

- `public abstract FatalFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public abstract FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void FatalFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract FatalFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void FatalFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract FatalFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public abstract FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public abstract FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract FatalFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void FatalFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public abstract FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public abstract FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void FatalFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract Info(System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Info(System.Exception exception);
```

- `public abstract Info(System.Object message) : System.Void`  

```csharp
public abstract System.Void Info(System.Object message);
```

- `public abstract Info(System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Info(System.Exception exception, System.Object message);
```

- `public abstract Info(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public abstract System.Void Info(UnityEngine.Object context, System.Object message);
```

- `public abstract Info(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Info(UnityEngine.Object context, System.Exception exception);
```

- `public abstract Info(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Info(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public abstract InfoFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void InfoFormat(System.String format, System.Object p1);
```

- `public abstract InfoFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void InfoFormat(System.String format, System.Object p1, System.Object p2);
```

- `public abstract InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void InfoFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract InfoFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void InfoFormat(System.String format, System.Object[] p);
```

- `public abstract InfoFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public abstract InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void InfoFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract InfoFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void InfoFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract InfoFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public abstract InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public abstract InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract InfoFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void InfoFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public abstract InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public abstract InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void InfoFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract Internal_WriteStream(UnityEngine.Object context, Colossal.Logging.Level level, System.String format, System.Exception exception, System.IO.TextWriter stdStream) : System.Void`  

```csharp
public abstract System.Void Internal_WriteStream(UnityEngine.Object context, Colossal.Logging.Level level, System.String format, System.Exception exception, System.IO.TextWriter stdStream);
```

- `public abstract isLevelEnabled(Colossal.Logging.Level level) : System.Boolean`  

```csharp
public abstract System.Boolean isLevelEnabled(Colossal.Logging.Level level);
```

- `public abstract Log(Colossal.Logging.Level level, System.String message, System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Log(Colossal.Logging.Level level, System.String message, System.Exception exception);
```

- `public abstract ReadSettings(Colossal.Logging.ILogSettingsProvider provider) : System.Void`  

```csharp
public abstract System.Void ReadSettings(Colossal.Logging.ILogSettingsProvider provider);
```

- `public virtual SetBacktraceEnabled(System.Boolean backtraceEnabled) : Colossal.Logging.ILog`  

```csharp
public virtual Colossal.Logging.ILog SetBacktraceEnabled(System.Boolean backtraceEnabled);
```

- `public virtual SetEffectiveness(Colossal.Logging.Level effectivenessLevel) : Colossal.Logging.ILog`  

```csharp
public virtual Colossal.Logging.ILog SetEffectiveness(Colossal.Logging.Level effectivenessLevel);
```

- `public virtual SetLogStackTrace(System.Boolean logStackTrace) : Colossal.Logging.ILog`  

```csharp
public virtual Colossal.Logging.ILog SetLogStackTrace(System.Boolean logStackTrace);
```

- `public virtual SetRedirectToDefault(System.Boolean redirectToDefault) : Colossal.Logging.ILog`  

```csharp
public virtual Colossal.Logging.ILog SetRedirectToDefault(System.Boolean redirectToDefault);
```

- `public virtual SetShowsErrorsInUI(System.Boolean showsErrorsInUI) : Colossal.Logging.ILog`  

```csharp
public virtual Colossal.Logging.ILog SetShowsErrorsInUI(System.Boolean showsErrorsInUI);
```

- `public virtual SetShowsStackTraceAboveLevels(Colossal.Logging.Level showsStackTraceAboveLevels) : Colossal.Logging.ILog`  

```csharp
public virtual Colossal.Logging.ILog SetShowsStackTraceAboveLevels(Colossal.Logging.Level showsStackTraceAboveLevels);
```

- `public abstract Trace(System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Trace(System.Exception exception);
```

- `public abstract Trace(System.Object message) : System.Void`  

```csharp
public abstract System.Void Trace(System.Object message);
```

- `public abstract Trace(System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Trace(System.Exception exception, System.Object message);
```

- `public abstract Trace(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public abstract System.Void Trace(UnityEngine.Object context, System.Object message);
```

- `public abstract Trace(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Trace(UnityEngine.Object context, System.Exception exception);
```

- `public abstract Trace(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Trace(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public abstract TraceFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void TraceFormat(System.String format, System.Object p1);
```

- `public abstract TraceFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void TraceFormat(System.String format, System.Object p1, System.Object p2);
```

- `public abstract TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void TraceFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract TraceFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void TraceFormat(System.String format, System.Object[] p);
```

- `public abstract TraceFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public abstract TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void TraceFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract TraceFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void TraceFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract TraceFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public abstract TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public abstract TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract TraceFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void TraceFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public abstract TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public abstract TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void TraceFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract Verbose(System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Verbose(System.Exception exception);
```

- `public abstract Verbose(System.Object message) : System.Void`  

```csharp
public abstract System.Void Verbose(System.Object message);
```

- `public abstract Verbose(System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Verbose(System.Exception exception, System.Object message);
```

- `public abstract Verbose(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public abstract System.Void Verbose(UnityEngine.Object context, System.Object message);
```

- `public abstract Verbose(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Verbose(UnityEngine.Object context, System.Exception exception);
```

- `public abstract Verbose(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Verbose(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public abstract VerboseFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(System.String format, System.Object p1);
```

- `public abstract VerboseFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(System.String format, System.Object p1, System.Object p2);
```

- `public abstract VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract VerboseFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(System.String format, System.Object[] p);
```

- `public abstract VerboseFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public abstract VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract VerboseFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public abstract VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public abstract VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract VerboseFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public abstract VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public abstract VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void VerboseFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract Warn(System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Warn(System.Exception exception);
```

- `public abstract Warn(System.Object message) : System.Void`  

```csharp
public abstract System.Void Warn(System.Object message);
```

- `public abstract Warn(System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Warn(System.Exception exception, System.Object message);
```

- `public abstract Warn(UnityEngine.Object context, System.Object message) : System.Void`  

```csharp
public abstract System.Void Warn(UnityEngine.Object context, System.Object message);
```

- `public abstract Warn(UnityEngine.Object context, System.Exception exception) : System.Void`  

```csharp
public abstract System.Void Warn(UnityEngine.Object context, System.Exception exception);
```

- `public abstract Warn(UnityEngine.Object context, System.Exception exception, System.Object message) : System.Void`  

```csharp
public abstract System.Void Warn(UnityEngine.Object context, System.Exception exception, System.Object message);
```

- `public abstract WarnFormat(System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void WarnFormat(System.String format, System.Object p1);
```

- `public abstract WarnFormat(System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void WarnFormat(System.String format, System.Object p1, System.Object p2);
```

- `public abstract WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void WarnFormat(System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract WarnFormat(System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void WarnFormat(System.String format, System.Object[] p);
```

- `public abstract WarnFormat(System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1);
```

- `public abstract WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void WarnFormat(System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract WarnFormat(System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void WarnFormat(System.Exception exception, System.String format, System.Object[] p);
```

- `public abstract WarnFormat(UnityEngine.Object context, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1);
```

- `public abstract WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2);
```

- `public abstract WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract WarnFormat(UnityEngine.Object context, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void WarnFormat(UnityEngine.Object context, System.String format, System.Object[] p);
```

- `public abstract WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1) : System.Void`  

```csharp
public abstract System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1);
```

- `public abstract WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2) : System.Void`  

```csharp
public abstract System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2);
```

- `public abstract WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3) : System.Void`  

```csharp
public abstract System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3);
```

- `public abstract WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4) : System.Void`  

```csharp
public abstract System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4);
```

- `public abstract WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5) : System.Void`  

```csharp
public abstract System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object p1, System.Object p2, System.Object p3, System.Object p4, System.Object p5);
```

- `public abstract WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p) : System.Void`  

```csharp
public abstract System.Void WarnFormat(UnityEngine.Object context, System.Exception exception, System.String format, System.Object[] p);
```


## Nested types

- `Colossal.Logging.ILog+StackTraceScope`  

