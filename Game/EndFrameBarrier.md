# Game.EndFrameBarrier

**Assembly:** Assembly-CSharp.dll (typical for Cities: Skylines 2 mods)  
**Namespace:** Game

**Type:** class

**Base:** SafeCommandBufferSystem

**Summary:** 
EndFrameBarrier is a runtime system that coordinates end-of-frame work for producer jobs and measures frame timing. It collects JobHandles submitted by producers, completes them at the end of the frame, and records the elapsed CPU time between frame boundaries using a Stopwatch. Use this system to ensure producer jobs are completed before the next frame and to gather simple per-frame timing information for profiling or logic that must run after producers finish.

---

## Fields

- `private System.Diagnostics.Stopwatch m_Stopwatch`  
A Stopwatch instance used to measure elapsed CPU time between frame boundaries. It is created in OnCreate, started and stopped in OnUpdate, and stopped again in OnDestroy. The stopwatch value is exposed via the currentElapsedTime and lastElapsedTime properties.

- `private Unity.Jobs.JobHandle <producerHandle>k__BackingField`  
Backing field for the producerHandle property. Holds the combined JobHandle of all producer jobs added via AddJobHandleForProducer. This combined handle is completed at the end of the frame to ensure all producer work has finished before proceeding.

## Properties

- `public Unity.Jobs.JobHandle producerHandle { get; private set }`  
Property exposing the combined JobHandle of producers. The setter is private; use AddJobHandleForProducer to append additional JobHandles. At the end of the frame OnUpdate completes this handle and then resets it to default(JobHandle).

- `public float lastElapsedTime { get; private set; }`  
Stores the elapsed time (in seconds) measured by the stopwatch for the most recent completed frame. Set in OnUpdate before the stopwatch is reset.

- `public float currentElapsedTime { get; }`  
Read-only computed property that returns the current stopwatch elapsed time in seconds ((float)m_Stopwatch.ElapsedTicks / (float)Stopwatch.Frequency). Useful for sampling the in-progress frame time when needed.

## Constructors

- `public EndFrameBarrier()`  
Default constructor. Marked with [Preserve] at the class methods where necessary to avoid stripping in build pipelines that do code stripping. The constructor itself does not perform initialization beyond the defaults; initialization of the stopwatch happens in OnCreate.

## Methods

- `protected override void OnCreate() : System.Void`  
Initializes the system and creates the Stopwatch instance used for timing.

```csharp
[Preserve]
    protected override void OnCreate()
    {
        base.OnCreate();
        m_Stopwatch = new Stopwatch();
    }
```             

- `protected override void OnDestroy() : System.Void`  
Stops the stopwatch and runs base teardown. Ensures the Stopwatch is not left running when the system is destroyed.

- `protected override void OnUpdate() : System.Void`  
Executed every frame. Responsibilities:
  - Stop the stopwatch and store the elapsed time into lastElapsedTime.
  - Reset the stopwatch to prepare for the next measurement window.
  - Complete the combined producerHandle (wait for all producer jobs added this frame).
  - Reset producerHandle to default to clear any previous state.
  - Start the stopwatch again to begin timing the next frame.
  - Call base.OnUpdate() to let the base SafeCommandBufferSystem perform its frame work (e.g., playing back command buffers).

This method is decorated with MethodImplOptions.NoInlining and [Preserve] in the source.

- `public new void AddJobHandleForProducer(JobHandle producerJob) : System.Void`  
Add a producer job handle to the combined producerHandle. Internally calls JobHandle.CombineDependencies to merge the existing producerHandle with the new producerJob so multiple producers can append their handles safely across the frame. Producers should call this to ensure their jobs are completed by the EndFrameBarrier at the end of the frame.

- `public EndFrameBarrier()`  
Parameterless constructor (present in the source and kept for completeness). Marked with [Preserve] in the source.

Notes and usage tips:
- Call AddJobHandleForProducer from producer code (main thread or jobs) to register work that must finish before the end-of-frame barrier completes.
- The barrier completes (producerHandle.Complete()) inside OnUpdate, so any dependent logic that must run after producers should query or rely on the barrier having completed for that frame.
- The stopwatch measures CPU time via Stopwatch ticks; currentElapsedTime provides a live measurement and lastElapsedTime provides the duration measured between the previous frame start/stop.
- Because OnUpdate calls base.OnUpdate() after completing producer jobs and restarting the stopwatch, the timing covers the period between consecutive calls to OnUpdate (i.e., roughly per-frame CPU time as measured by this stopwatch).