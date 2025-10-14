# Game.IGPUSystem

**Assembly:** Assembly-CSharp  
**Namespace:** Game

**Type:** interface

**Base:** — (none)

**Summary:** Interface representing a GPU-driven system used by the game to record or schedule GPU work during simulation. Implementors provide GPU commands into a UnityEngine.Rendering.CommandBuffer and expose whether the system is enabled and whether it operates asynchronously. This is intended for use during the game's simulation/GPU update step so mods can integrate custom GPU workloads safely.
---

## Fields

- This interface declares no fields.  
Interfaces do not define instance fields; state should be stored by concrete implementations if needed.

## Properties

- `public bool Enabled { get; }`  
Indicates whether this GPU system is currently active and should be invoked. Callers should check Enabled before calling OnSimulateGPU.

- `public bool IsAsync { get; set; }`  
If true, the implementation should attempt to run or schedule its GPU work asynchronously (e.g., using async compute or command buffer scheduling). The exact behavior is implementation-defined; callers can set or read this flag to control or observe asynchronous execution preferences.

## Constructors

- Interfaces do not define constructors.  
No public constructors — implementers should provide appropriate construction and initialization logic.

## Methods

- `void OnSimulateGPU(UnityEngine.Rendering.CommandBuffer cmd)`  
Called during the GPU simulation step. Implementations should record GPU commands into the provided CommandBuffer (cmd). The method should not assume it runs on the main thread unless documented by the caller; ensure any required synchronization, resource lifetime management, and proper use of Unity's CommandBuffer API. Typical responsibilities:
  - Record draw/dispatch/compute commands and resource state transitions into cmd.
  - Avoid blocking CPU work inside this call; if IsAsync is true, prefer scheduling GPU work that can run independently.
  - Ensure that any temporary GPU resources are created/registered appropriately with Unity and released when no longer needed.

Example usage notes:
  - The caller (game/mod) will provide a CommandBuffer and integrate it into the rendering pipeline (e.g., Graphics.ExecuteCommandBuffer or via a ScriptableRenderPass). Implementations should not execute the buffer themselves unless explicitly required.
  - If your implementation uses GPU fences or Graphics APIs that require explicit synchronization, coordinate with the rest of the rendering/submission pipeline to avoid race conditions or resource hazards.

```csharp
using UnityEngine.Rendering;

namespace Game;

public interface IGPUSystem
{
    bool Enabled { get; }

    bool IsAsync { get; set; }

    void OnSimulateGPU(CommandBuffer cmd);
}
```