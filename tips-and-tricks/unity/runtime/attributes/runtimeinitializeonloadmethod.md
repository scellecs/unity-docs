# RuntimeInitializeOnLoadMethod

Вызов статического метода на старта приложения.   
Конкретную точку, когда вызовется можно уточнить аргументом.  
Ниже указаны варианты аргумента в порядке вызова:

1. SubsystemRegistration
2. AfterAssembliesLoaded
3. BeforeSplashScreen
4. BeforeSceneLoad
5. AfterSceneLoad

```csharp
using UnityEngine;

public static class ExampleClass 
{
    [RuntimeInitializeOnLoadMethod(RuntimeInitializeLoadType.SubsystemRegistration)]
    private static void Foo() 
    {
        Debug.Log(RuntimeInitializeLoadType.SubsystemRegistration);
    }
}
```

