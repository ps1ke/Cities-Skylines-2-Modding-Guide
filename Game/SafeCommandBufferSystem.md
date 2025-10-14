# Game.SafeCommandBufferSystem

**Assembly:**  
**Namespace:** Game

**Type:** class

**Base:** EntityCommandBufferSystem

**Summary:** A thin wrapper around Unity.Entities.EntityCommandBufferSystem that enforces a simple usage window for creating EntityCommandBuffer instances. The system has an internal flag (m_IsAllowed) which, when false, causes CreateCommandBuffer() to throw — preventing creation of command buffers outside the intended time. The intent is to help catch incorrect usage (creating buffers while the system is in its update/playback phase) and to make buffer creation explicit via AllowUsage().

---

## Fields

- `private bool m_IsAllowed`  
Flag controlling whether CreateCommandBuffer() is allowed to return a buffer. Initialized to true. On system update this flag is set to false to prevent creating command buffers during the system's update/playback phase; calling AllowUsage() sets it back to true.

## Properties

- None.  
This class exposes no public properties.

## Constructors

- `public SafeCommandBufferSystem()`  
Default constructor. Marked with [Preserve] to avoid IL2CPP stripping; performs no special initialization beyond the default field initialization.

## Methods

- `public void AllowUsage()`  
Re-enables creation of EntityCommandBuffer instances by setting m_IsAllowed = true. Call this from systems that need to produce command buffers before calling CreateCommandBuffer().

- `public new EntityCommandBuffer CreateCommandBuffer()`  
Returns an EntityCommandBuffer by delegating to the base EntityCommandBufferSystem.CreateCommandBuffer() only if m_IsAllowed is true. If m_IsAllowed is false, this method throws an Exception with the message "Trying to create EntityCommandBuffer when it's not allowed!", helping surface incorrect timing of buffer creation.

- `protected override void OnUpdate()`  
Called by the Unity ECS when the system updates. This override disables further creation of EntityCommandBuffer instances for the duration of the update/playback by setting m_IsAllowed = false, then calls base.OnUpdate().

```csharp
[Preserve]
protected override void OnUpdate()
{
    m_IsAllowed = false;
    base.OnUpdate();
}
```

Additional notes / recommended usage:
- Typical pattern: before scheduling work that will produce commands, call safeCommandBufferSystem.AllowUsage(), then call safeCommandBufferSystem.CreateCommandBuffer() to obtain a buffer. After the system's OnUpdate runs, CreateCommandBuffer() will be disabled until AllowUsage() is called again.
- The class uses [Preserve] on lifecycle methods/constructor to ensure it is not removed by code stripping (important for modding / IL2CPP builds).
- If you see the exception from CreateCommandBuffer(), it indicates a timing problem: command buffers are being created during the system's update/playback phase — adjust the caller to request a buffer earlier (e.g., during the scheduling phase) and use AllowUsage() appropriately.