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
static async Task<object> WaitForDevice(Action cancel, CancellationToken token)
	{
		TaskCompletionSource<object> devicePaired = new TaskCompletionSource<object>();
		using (token.Register(delegate
		{
			devicePaired.TrySetCanceled();
		}))
		{
			Game.Input.InputManager.instance.EventDevicePaired += Handler;
			if (cancel != null)
			{
				cancel = (Action)Delegate.Combine(cancel, new Action(CancelHandler));
			}
			try
			{
				return await devicePaired.Task;
			}
			finally
			{
				Game.Input.InputManager.instance.EventDevicePaired -= Handler;
				if (cancel != null)
				{
					cancel = (Action)Delegate.Remove(cancel, new Action(CancelHandler));
				}
			}
		}
		void CancelHandler()
		{
			devicePaired.TrySetCanceled();
		}
		void Handler()
		{
			devicePaired.TrySetResult(null);
		}
	}
```

- `public static WaitForInput(UnityEngine.InputSystem.InputAction inputContinue, UnityEngine.InputSystem.InputAction inputCancel, System.Action cancel, System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.ValueTuple<System.Boolean, UnityEngine.InputSystem.InputDevice>>`  

```csharp
public static System.Threading.Tasks.Task<System.ValueTuple<System.Boolean, UnityEngine.InputSystem.InputDevice>> WaitForInput(UnityEngine.InputSystem.InputAction inputContinue, UnityEngine.InputSystem.InputAction inputCancel, System.Action cancel, System.Threading.CancellationToken token);
```

- `public static WaitForUser(System.Action cancel, System.Threading.CancellationToken token) : System.Threading.Tasks.Task<Colossal.PSI.Common.UserChangedFlags>`  

```csharp
static async Task<UserChangedFlags> WaitForUser(Action cancel, CancellationToken token)
	{
		TaskCompletionSource<UserChangedFlags> userSignedBackIn = new TaskCompletionSource<UserChangedFlags>();
		using (token.Register(delegate
		{
			userSignedBackIn.TrySetCanceled();
		}))
		{
			PlatformManager.instance.onUserUpdated += Handler;
			if (cancel != null)
			{
				cancel = (Action)Delegate.Combine(cancel, new Action(CancelHandler));
			}
			try
			{
				return await userSignedBackIn.Task;
			}
			finally
			{
				PlatformManager.instance.onUserUpdated -= Handler;
				if (cancel != null)
				{
					cancel = (Action)Delegate.Remove(cancel, new Action(CancelHandler));
				}
			}
		}
		void CancelHandler()
		{
			userSignedBackIn.TrySetCanceled();
		}
		void Handler(IPlatformServiceIntegration psi, UserChangedFlags flags)
		{
			if (PlatformManager.instance.IsPrincipalUserIntegration(psi) && flags.HasFlag(UserChangedFlags.UserSignedInAgain))
			{
				userSignedBackIn.TrySetResult(flags);
			}
		}
	}
```

- `public static WaitForWaitingState(UnityEngine.InputSystem.InputAction inputAction) : System.Threading.Tasks.Task`  

```csharp
static Task WaitForWaitingState(InputAction inputAction)
	{
		if (inputAction.phase == InputActionPhase.Waiting)
		{
			return Task.CompletedTask;
		}
		TaskCompletionSource<bool> taskCompletionSource = new TaskCompletionSource<bool>();
		System.Timers.Timer timer = new System.Timers.Timer(33.333333333333336);
		timer.Elapsed += delegate
		{
			if (inputAction.phase == InputActionPhase.Waiting)
			{
				taskCompletionSource.SetResult(result: true);
				timer.Stop();
				timer.Dispose();
			}
		};
		timer.AutoReset = true;
		timer.Start();
		return taskCompletionSource.Task;
	}
```


## Nested types

- `Game.SceneFlow.IScreenState+<>c__DisplayClass0_0`  
- `Game.SceneFlow.IScreenState+<>c__DisplayClass1_0`  
- `Game.SceneFlow.IScreenState+<>c__DisplayClass2_0`  
- `Game.SceneFlow.IScreenState+<>c__DisplayClass3_0`  
- `Game.SceneFlow.IScreenState+<WaitForDevice>d__2`  
- `Game.SceneFlow.IScreenState+<WaitForInput>d__1`  
- `Game.SceneFlow.IScreenState+<WaitForUser>d__3`  

