---
description: >-
  https://docs.unity3d.com/ScriptReference/RuntimeInitializeOnLoadMethodAttribute.html
---

# RuntimeInitializeOnLoadMethod

Вызов статического метода на старта приложения.   
Может быть полезен для создания плагинов или единой точки входа в приложение.

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

Конкретную точку, когда вызовется можно уточнить аргументом.  
Ниже указаны варианты аргумента в порядке вызова:

1. SubsystemRegistration 
2. AfterAssembliesLoaded
3. BeforeSplashScreen
4. BeforeSceneLoad
5. AfterSceneLoad \(вызывается после всех Awake у скриптов находящихся на сцене\)

{% hint style="info" %}
Если атрибут указан без аргумента, то используется AfterSceneLoad.
{% endhint %}

{% hint style="info" %}
Порядок исполнения таких методов относительно друг друга неконтролируемый.
{% endhint %}

