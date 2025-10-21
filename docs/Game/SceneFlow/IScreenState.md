# Game.SceneFlow.IScreenState

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IScreenState
{
    public abstract System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token);
    public static System.Threading.Tasks.Task<System.Object> WaitForDevice(System.Action cancel, System.Threading.CancellationToken token);
    public static System.Threading.Tasks.Task<System.ValueTuple<System.Boolean, UnityEngine.InputSystem.InputDevice>> WaitForInput(UnityEngine.InputSystem.InputAction inputContinue, UnityEngine.InputSystem.InputAction inputCancel, System.Action cancel, System.Threading.CancellationToken token);
    public static System.Threading.Tasks.Task<Colossal.PSI.Common.UserChangedFlags> WaitForUser(System.Action cancel, System.Threading.CancellationToken token);
    public static System.Threading.Tasks.Task WaitForWaitingState(UnityEngine.InputSystem.InputAction inputAction);
}
```


## Methods

- `public abstract Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public abstract System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token);
```

- `public static WaitForDevice(System.Action cancel, System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Object>`  

```csharp
public static System.Threading.Tasks.Task<System.Object> WaitForDevice(System.Action cancel, System.Threading.CancellationToken token);
```

- `public static WaitForInput(UnityEngine.InputSystem.InputAction inputContinue, UnityEngine.InputSystem.InputAction inputCancel, System.Action cancel, System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.ValueTuple<System.Boolean, UnityEngine.InputSystem.InputDevice>>`  

```csharp
public static System.Threading.Tasks.Task<System.ValueTuple<System.Boolean, UnityEngine.InputSystem.InputDevice>> WaitForInput(UnityEngine.InputSystem.InputAction inputContinue, UnityEngine.InputSystem.InputAction inputCancel, System.Action cancel, System.Threading.CancellationToken token);
```

- `public static WaitForUser(System.Action cancel, System.Threading.CancellationToken token) : System.Threading.Tasks.Task<Colossal.PSI.Common.UserChangedFlags>`  

```csharp
public static System.Threading.Tasks.Task<Colossal.PSI.Common.UserChangedFlags> WaitForUser(System.Action cancel, System.Threading.CancellationToken token);
```

- `public static WaitForWaitingState(UnityEngine.InputSystem.InputAction inputAction) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task WaitForWaitingState(UnityEngine.InputSystem.InputAction inputAction);
```


## Nested types

- `Game.SceneFlow.IScreenState+<>c__DisplayClass0_0`  
- `Game.SceneFlow.IScreenState+<>c__DisplayClass1_0`  
- `Game.SceneFlow.IScreenState+<>c__DisplayClass2_0`  
- `Game.SceneFlow.IScreenState+<>c__DisplayClass3_0`  
- `Game.SceneFlow.IScreenState+<WaitForDevice>d__2`  
- `Game.SceneFlow.IScreenState+<WaitForInput>d__1`  
- `Game.SceneFlow.IScreenState+<WaitForUser>d__3`  

