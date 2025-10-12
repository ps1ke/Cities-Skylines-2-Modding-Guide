# Game.SceneFlow.IScreenState

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** interface abstract public  


## Methods

- `public abstract Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public static WaitForDevice(System.Action cancel, System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Object>`  
- `public static WaitForInput(UnityEngine.InputSystem.InputAction inputContinue, UnityEngine.InputSystem.InputAction inputCancel, System.Action cancel, System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.ValueTuple<System.Boolean, UnityEngine.InputSystem.InputDevice>>`  
- `public static WaitForUser(System.Action cancel, System.Threading.CancellationToken token) : System.Threading.Tasks.Task<Colossal.PSI.Common.UserChangedFlags>`  
- `public static WaitForWaitingState(UnityEngine.InputSystem.InputAction inputAction) : System.Threading.Tasks.Task`  

## Nested types

- `Game.SceneFlow.IScreenState+<>c__DisplayClass0_0`  
- `Game.SceneFlow.IScreenState+<>c__DisplayClass1_0`  
- `Game.SceneFlow.IScreenState+<>c__DisplayClass2_0`  
- `Game.SceneFlow.IScreenState+<>c__DisplayClass3_0`  
- `Game.SceneFlow.IScreenState+<WaitForDevice>d__2`  
- `Game.SceneFlow.IScreenState+<WaitForInput>d__1`  
- `Game.SceneFlow.IScreenState+<WaitForUser>d__3`  

