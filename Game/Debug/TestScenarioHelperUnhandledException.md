# Game.Debug.TestScenarioHelperUnhandledException

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Code

```csharp
public class TestScenarioHelperUnhandledException : UnityEngine.MonoBehaviour
{
    public TestScenarioHelperUnhandledException();

    private System.Collections.IEnumerator CoThrowUnhandledException();
    private System.Void Start();
}
```


## Constructors

- `public TestScenarioHelperUnhandledException()`  

```csharp
public TestScenarioHelperUnhandledException();
```


## Methods

- `private CoThrowUnhandledException() : System.Collections.IEnumerator`  

```csharp
private IEnumerator CoThrowUnhandledException()
	{
		yield return new WaitForSeconds(5f);
		throw new Exception("TestScenarioHelperUnhandledException");
	}
```

- `private Start() : System.Void`  

```csharp
private void Start()
	{
		StartCoroutine(CoThrowUnhandledException());
	}
```


## Nested types

- `Game.Debug.TestScenarioHelperUnhandledException+<CoThrowUnhandledException>d__1`  

