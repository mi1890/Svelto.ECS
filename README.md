# Svelto C# Entity Component System framework 3.x
=====================================

Real ECS framework for c\#. Enables to write encapsulated, decoupled, maintainable, highly efficient, data oriented, cache friendly, code without pain. Although the framework is platform agnostic \(compatible with c\# 7 and .net standard 2.0\), it comes with several Unity extensions.

## Why using Svelto.ECS with Unity?
Svelto.ECS wasn't born just from the needs of a large team, but also as a result of years of reasoning behind software engineering applied to game development. Svelto.ECS hasn't been written just to develop faster code, it has been designed to help develop better code. Performance gains is just one of the benefits in using Svelto.ECS, as ECS is a great way to write cache-friendly code. Svelto.ECS has been developed with the idea of ECS being a paradigm and not just a pattern, letting the user shift completely away from Object Oriented Programming with consequent improvements of the code design and code maintainability. Svelto.ECS is the result of years of iteration of the ECS paradigm applied to real game development with the intent to be as foolproof as possible. Svelto.ECS has been designed to be used by a medium-size/large team working on long term projects where the cost of maintainability is relevant.

**Svelto.ECS is the only c# framework other than DOTS ECS to be fully compatible with Burst and Jobs.**

Svelto.ECS is compatible with Unity 2019.3.x cycle as long as it's not used with DOTS ECS. If DOTS ECS integration is necessary, Svelto.ECS will always target the last stable unity version using DOTS.

## Why using Svelto.ECS without Unity?
The question is just for fun! There are so many c# game engines out there (Stride, Monogame, FlatRedBall, WaveEngine, UnrealCLR, UniEngine just to mention some) and Svelto.ECS is compatible with all of them! 

## If you decide to use Svelto.ECS

Svelto.ECS is an Open Source Project provided as it is, no support is guaranteed other than the help given on the Svelto Discord channel. Issues will be fixed when possible. If you decide to adopt Svelto.ECS, it's assumed you are willing to partecipate to the development of the product if necessary.

## How to clone the repository:
The folders Svelto.ECS and Svelto.Common, where present, are submodules pointing to the relative repositories. If you find them empty, you need to update them through the submodule command. Check some instructions here: https://github.com/sebas77/Svelto.ECS.Vanilla.Example/wiki

## Svelto distributed as Unity Package through OpenUPM [![openupm](https://img.shields.io/npm/v/com.sebaslab.svelto.ecs?label=openupm&registry_uri=https://package.openupm.com)](https://openupm.com/packages/com.sebaslab.svelto.ecs/)

read this article for more information: http://www.sebaslab.com/distributing-svelto-through-openupm/ ~~or just install the package that comes from the link https://package-installer.glitch.me/v1/installer/OpenUPM/com.sebaslab.svelto.ecs?registry=https%3A%2F%2Fpackage.openupm.com~~

**Note on the System.Runtime.CompilerServices.Unsafe.dll dependency and the bit of a mess that Unity Package Dependency System is:**

Unity Package System has a big deficiency when it comes to dll dependency solving: two packages cannot point to the same dependency from different sources. Since Unity Collection removed the Unsafe.dll dependency, ~~I had to distribute my own package. This means that if you want to use Svelto from UPM, you will need Svelto unsafe dll to be the only unsafe dll in the project. Otherwise you just download the source code and solve dependencies manually.~~

For Unity Users: to solve the unsafe dependency you need to add the following scopedRegistries in manifest.json:
```
  {
    "scopedRegistries": [
        {
            "name": "package.openupm.com",
            "url": "https://package.openupm.com",
            "scopes": [
                "com.sebaslab.svelto.common",
                "com.sebaslab.svelto.ecs",
                "org.nuget.system.runtime.compilerservices.unsafe"
            ]
        }
    ],
    "dependencies": {
        "com.sebaslab.svelto.ecs": "3.2.6"
    }
}
```

## Svelto distributed as Nuget

I am not a Nuget expert, but thanks to our contributors, Svelto.ECS can be found at https://www.nuget.org/packages/Svelto.ECS/

## Official Examples (A.K.A. where is the documentation?)

Svelto doesn't have official documentation. The reason is that documentation is costly to mantain and...I reckon people don't need it, thanks to the highly documented and simple mini-examples. Please check and study them all regardless the platform you intend to use Svelto with.

### * **Mini Examples**: [https://github.com/sebas77/Svelto.MiniExamples](https://github.com/sebas77/Svelto.MiniExamples) \(including articles\)
* **Unit Tests**: [https://github.com/sebas77/Svelto.ECS.Tests](https://github.com/sebas77/Svelto.ECS.Tests)

After that, you can get all the help you need from the official chat:

**Official Discord Server \(join to get help from me for free!\)**

* [https://discord.gg/3qAdjDb](https://discord.gg/3qAdjDb) 

## Official Articles

**Framework articles:**

* [Svelto ECS 3.0 is finally here](https://www.sebaslab.com/whats-new-in-svelto-ecs-3-0/)  \(re-introducing svelto, this article is important for starters!\)
* [Introducing Svelto ECS 2.9](http://www.sebaslab.com/introducing-svelto-ecs-2-9/)  \(shows what's changed since 2.8\)
* [Introducing Svelto ECS 2.8](http://www.sebaslab.com/introducing-svelto-ecs-2-8/)  \(shows what's changed since 2.7\)
* [Svelto.ECS 2.7: what’s new and best practices](http://www.sebaslab.com/svelto-2-7-whats-new-and-best-practices/) \(shows what's changed since 2.5\)
* [Introducing Svelto ECS 2.5](http://www.sebaslab.com/svelto-ecs-2-5-and-allocation-0-code/) \(shows what's changed since 2.0\)
* [Svelto.ECS 2.0 is production ready](http://www.sebaslab.com/svelto-ecs-2-0-almost-production-ready/) \(shows what's changed since 1.0\)
* [Svelto ECS is now production ready](http://www.sebaslab.com/ecs-1-0/)

**Theory related articles (from the most recent to the oldest, read from the oldest if you are new to it):**

* [OOP abstraction layer in an ECS-centric application](https://www.sebaslab.com/oop-abstraction-layer-in-a-ecs-centric-application/)  \(this article is important for starters!\)
* [ECS abstraction layers and module encapsulation](https://www.sebaslab.com/ecs-abstraction-layers-and-modules-encapsulation/)
* [The Quest for Maintainable Code and The Path to ECS](http://www.sebaslab.com/the-quest-for-maintainable-code-and-the-path-to-ecs/)
* [The truth behind Inversion of Control – Part V – Entity Component System design to achieve true Inversion of Flow Control](http://www.sebaslab.com/the-truth-behind-inversion-of-control-part-v-drifting-away-from-ioc-containers/)
* [The truth behind Inversion of Control – Part IV – Dependency Inversion Principle](http://www.sebaslab.com/the-truth-behind-inversion-of-control-part-iv-dependency-inversion-principle/)
* [The truth behind Inversion of Control – Part III – Entity Component System Design](http://www.sebaslab.com/the-truth-behind-inversion-of-control-part-iii-entity-component-systems/)
* [The truth behind Inversion of Control – Part II – Inversion of Control](http://www.sebaslab.com/the-truth-behind-inversion-of-control-part-ii-inversion-of-control/)
* [The truth behind Inversion of Control – Part I – Dependency Injection](http://www.sebaslab.com/the-truth-behind-inversion-of-control-part-i-dependency-injection/)
* [Inversion of Control with Unity – part 2](http://www.sebaslab.com/ioc-container-for-unity3d-part-2/)
* [Inversion of Control with Unity – part 1](http://www.sebaslab.com/ioc-container-for-unity3d-part-1/)

**Practical articles**

* [Svelto.ECS Internals: How to avoid boxing when using structs with reflection](https://www.sebaslab.com/casting-a-struct-into-an-interface-inside-a-generic-method-without-boxing/)
* [Svelto ECS 3.0 Internals: profiling the Entity Collection](https://www.sebaslab.com/svelto-ecs-3-0-internals-the-entity-collection/)
* [Svelto ECS 3.0 Internals: Support Native Memory Natively](https://www.sebaslab.com/svelto-ecs-3-0-internals-support-native-memory-natively/)
* [Svelto MiniExamples: GUI and Services Layer with Unity](https://www.sebaslab.com/svelto-miniexamples-gui-and-services-layer/)
* [Svelto Mini (Unity) Examples: Doofuses Must Eat](https://www.sebaslab.com/svelto-mini-examples-doofuses-must-eat/)
* [Svelto Mini Examples: The Unity Survival Example](http://www.sebaslab.com/learning-svelto-ecs-by-example-the-unity-survival-example/)
* [Learning Svelto.ECS by example – The Vanilla Example](http://www.sebaslab.com/learning-svelto-ecs-by-example-the-vanilla-example/)
* [Porting a boid simulation from UnityECS/Jobs to Svelto.ECS/Tasks](https://www.sebaslab.com/porting-a-boid-simulation-from-unityecs-to-svelto-ecs/)
* [Svelto.ECS+Tasks to write Data Oriented, Cache Friendly, Multi-Threaded code](http://www.sebaslab.com/svelto-ecs-svelto-tasks-to-write-data-oriented-cache-friendly-multi-threaded-code-in-unity/)

Note: I included the IoC articles just to show how I shifted over the years from using an IoC container to use an ECS framework and the rationale behind its adoption.

## Users Generated Content \(I removed all the outdated articles, so this is a call for new ones!\)

* [A Beginner’s Guide to Svelto.ECS (3.0) with Unity by Jiheh Ritterling](https://jiheh.medium.com/a-beginners-guide-to-svelto-ecs-3-0-with-unity-e9dbc88a2145)

**Svelto Extensions**

* [Svelto.ECS.Schema - Schema and State Machine extensions for Svelto.ECS](https://github.com/cathei/Svelto.ECS.Schema)
* [Automatic way to control svelto engines order without having to pass in a string using attributes](https://gist.github.com/dragonslaya84/88e6bb998eda8fe4ee912f01d67feec9)
* [Foundation for a possible platform agnostic Svelto.ECS inspector](https://github.com/akrogame/svelto-ecs-inspector)
* [Being able to swap entities between a subset of compound tags to another subset of compound tags](https://gist.github.com/jlreymendez/c2f441aaf6ac7b5f233ecd990314e9cc)

## In case of bugs

Best option is to fork and clone [https://github.com/sebas77/Svelto.ECS.Tests](https://github.com/sebas77/Svelto.ECS.Tests), add new tests to reproduce the problem and request a pull. I will then fix the issue. Also feel free to contact me on Discord.

## [The Github wiki page](https://github.com/sebas77/Svelto.ECS/wiki)

Completely outdated and could even mislead. Feel free to update it if you have a good understanding of Svelto! I decided I won't update it anymore as it's better for me to focus on other parts of Svelto development. If you need any help, you will need to join the aforementioned discord server.

## I like the project, how can I help?

Hey, thanks a lot for considering this. You can help in several ways. The simplest is to talk about Svelto.ECS and spread the word, the more we are, the better it is for the community. Then you can help with the documentation, updating the wiki or writing your own articles. Svelto.ECS has all the features needed to make a game with the ECS pattern, but some areas are lacking: *A visual debugger and more unit tests are needed*. Other platforms other than Unity could get some love too: Stride Game, Godot, monogame, FNA or whatever supports c#. Porting to other languages, especially c++, would be awesome but probably pointless. Please check the lane dedicated to the community tasks list here: https://github.com/users/sebas77/projects/3 and let me know if you want to take something on!

## Svelto Framework is used to develop the following products\(\*\):

![image](https://user-images.githubusercontent.com/945379/123062411-65ee3600-d404-11eb-8dca-d30c28ed909d.png)
![Gamecraft](https://steamcdn-a.akamaihd.net/steamcommunity/public/images/clans/35037633/e05ca4fc6f20f1e6150a6ace1d12fe8cd145fa0d.png)
![Robocraft Infinity](https://i.ytimg.com/vi/m_4fpgHwoBs/maxresdefault.jpg) 
![Cardlife](https://i.ytimg.com/vi/q2jaUZjnNyg/maxresdefault.jpg)

\*If you want your products made with Svelto here, just send me an email or whatever, I'll be super happy to add them.

_**Note: Dear Svelto Users : Although I am committed to help you and write articles as much as I can, I will never be able to keep all the documentation up to date. If you are a happy svelto user and you want to contribute, please feel free to update the github wiki! 🙏👊**_


