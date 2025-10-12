# Colossal.TaskProgress

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IProgress<Colossal.ProgressTracker>`  

## Fields

- `private readonly System.Action<Colossal.ProgressTracker> m_Handler`  
- `private readonly System.Diagnostics.Stopwatch m_Stopwatch`  
- `private System.Int64 <updateFrequency>k__BackingField`  
- `private System.String m_SubTaskName`  
- `private Colossal.ProgressTracker+Group m_SubTaskGroup`  
- `public static const System.Int64 kUpdateFrequencyMs`  

## Properties

- `public System.Int64 updateFrequency { get; set }`  
- `public System.String subTaskName { get; set }`  
- `public Colossal.ProgressTracker+Group subTaskGroup { get; set }`  

## Constructors

- `public TaskProgress(System.Action<Colossal.ProgressTracker> handler)`  

## Methods

- `public GetSubProgress(System.String taskName = Dummy, Colossal.ProgressTracker+Group progressGroup = None) : Colossal.TaskProgress`  
- `public Report(Colossal.ProgressTracker value) : System.Void`  

