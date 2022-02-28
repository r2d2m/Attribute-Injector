# Attribute Injector For Unity

[![Unity 2017+](https://img.shields.io/badge/unity-2019.4%2B-blue.svg)](https://unity3d.com/get-unity/download)
[![openupm](https://img.shields.io/npm/v/com.dbrizov.naughtyattributes?label=openupm&registry_uri=https://package.openupm.com)](https://openupm.com/packages/com.dbrizov.naughtyattributes/)
[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](https://github.com/muveso/Attribute-Injector/blob/main/LICENSE)

**Attribute Injector** is an attribute-based framework for creating and injecting inline codes into your projects.

A code injection built for use in [Unity3D](https://unity3d.com/). Implemented using [Mono.Cecil](http://www.mono-project.com/docs/tools+libraries/libraries/Mono.Cecil/).

*Attribute Injector* is a library that applies code injection to methods with additional attributes without the need to extend and create a new methods for each functionality.  You can ensure project integrity with very little attributes.

## Simple Usage

##### Create an attribute with injection :

```C#
[Injection]
public class SimpleLog : Attribute
{
    [Rise(When.OnEntry)]
    public void SomeMethod([Argument(Method.Name)] string name)
    {
        Debug.Log($"Entering method {name}");
    }
}
```

##### Use it :

```C#
[SimpleLog]
public void DoSomething() 
{ 
    Debug.Log("body of DoSomething method");
}

DoSomething(); //call the method anywhere...
```

##### Result :

```bash
Entering method 'DoSomething'
body of DoSomething method
```

## Requirements

Before install the addon, you should check the requirements.

- Supports only projects that can reference **netstandard3.5+** libraries. Make sure *PlayerSettings -> Api Compatibility Level* is set to **.NET 4.X**
- In order for the addon to work, you need to add **Mono Cecil** package.
- Works with Unity 2017+

For Mono Cecil installation:

1. In Unity, open **Window** -> **Package Manager**.

2. Press the **+** button, choose "**Add package from git URL...**"

3. Enter "com.unity.nuget.mono-cecil@1.10" and press **Add**.

## Download

### Git URL

Project supports Unity Package Manager. To install the project as a Git package do the following:

1. In Unity, open **Window** -> **Package Manager**.
2. Press the **+** button, choose "**Add package from git URL...**"
3. Enter "https://github.com/muveso/AttributeInjector.git#upm" and press **Add**.

### Unity Package

Alternatively, you can add the code directly to the project:

1. Clone the repo or download the latest release.
2. Add the **AttributeInjector** folder to your Unity project or import the .unitypackage


Contact : sefa@muveso.com




