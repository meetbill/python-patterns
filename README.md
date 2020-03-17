python-patterns
===============

A collection of design patterns and idioms in Python.

设计模式的分类
----------------

根据其目的（模式是用来做什么的）可分为创建型 (Creational)，结构型 (Structural) 和行为型 (Behavioral) 三种：

> * 创建型模式主要用于创建对象。
> * 结构型模式主要用于处理类或对象的组合。
> * 行为型模式主要用于描述对类或对象怎样交互和怎样分配职责。

> 函数和类上面区别？
```
没有区别，就像问人和走路有什么区别，猪和吃饭有什么区别，问得牛头不对马嘴的伪问题，函数和方法才可以比较。
类（对象）和模块才有可比性，必须要搞清楚原因，不然脑袋中有这个比较的想法那就不可能写得了oop。
```
> 面向过程和面向对象的区别
```
面向过程是 文件模块名.eat(狗的名字，shit)
oop是  狗.eat(shit)
```

Current Patterns
----------------

__Creational Patterns__:

| Pattern | Description |
|:-------:| ----------- |
| 抽象工厂模式 [abstract_factory](patterns/creational/abstract_factory.py) | use a generic function with specific factories |
| [borg](patterns/creational/borg.py) | a singleton with shared-state among instances |
| 建造者模式 [builder](patterns/creational/builder.py) | instead of using multiple constructors, builder object receives parameters and returns constructed objects |
| 工厂方法模式 [factory](patterns/creational/factory.py) | delegate a specialized function/method to create instances |
| [lazy_evaluation](patterns/creational/lazy_evaluation.py) | lazily-evaluated property pattern in Python |
| [pool](patterns/creational/pool.py) | preinstantiate and maintain a group of instances of the same type |
| 原型模式 [prototype](patterns/creational/prototype.py) | use a factory and clones of a prototype for new instances (if instantiation is expensive) |

__Structural Patterns__:

| Pattern | Description |
|:-------:| ----------- |
| [3-tier](patterns/structural/3-tier.py) | data<->business logic<->presentation separation (strict relationships) |
| 适配器模式 [adapter](patterns/structural/adapter.py) | adapt one interface to another using a white-list |
| 桥接模式 [bridge](patterns/structural/bridge.py) | a client-provider middleman to soften interface changes |
| 组合模式 [composite](patterns/structural/composite.py) | lets clients treat individual objects and compositions uniformly |
| 装饰模式 [decorator](patterns/structural/decorator.py) | wrap functionality with other functionality in order to affect outputs |
| 外观模式 [facade](patterns/structural/facade.py) | use one class as an API to a number of others |
| 享元模式 [flyweight](patterns/structural/flyweight.py) | transparently reuse existing instances of objects with similar/identical state |
| [front_controller](patterns/structural/front_controller.py) | single handler requests coming to the application |
| [mvc](patterns/structural/mvc.py) | model<->view<->controller (non-strict relationships) |
| 代理模式 [proxy](patterns/structural/proxy.py) | an object funnels operations to something else |

__Behavioral Patterns__:

| Pattern | Description |
|:-------:| ----------- |
| 职责链模式 [chain_of_responsibility](patterns/behavioral/chain_of_responsibility.py) | apply a chain of successive handlers to try and process the data |
| [catalog](patterns/behavioral/catalog.py) | general methods will call different specialized methods based on construction parameter |
| [chaining_method](patterns/behavioral/chaining_method.py) | continue callback next object method |
| 命令模式 [command](patterns/behavioral/command.py) | bundle a command and arguments to call later |
| 迭代器模式 [iterator](patterns/behavioral/iterator.py) | traverse a container and access the container's elements |
| [iterator](patterns/behavioral/iterator_alt.py) (alt. impl.)| traverse a container and access the container's elements |
| 中介者模式 [mediator](patterns/behavioral/mediator.py) | an object that knows how to connect other objects and act as a proxy |
| 备忘录模式 [memento](patterns/behavioral/memento.py) | generate an opaque token that can be used to go back to a previous state |
| 观察者模式 [observer](patterns/behavioral/observer.py) | provide a callback for notification of events/changes to data |
| [publish_subscribe](patterns/behavioral/publish_subscribe.py) | a source syndicates events/data to 0+ registered listeners |
| [registry](patterns/behavioral/registry.py) | keep track of all subclasses of a given class |
| [specification](patterns/behavioral/specification.py) |  business rules can be recombined by chaining the business rules together using boolean logic |
| 状态模式 [state](patterns/behavioral/state.py) | logic is organized into a discrete number of potential states and the next state that can be transitioned to |
| 策略模式 [strategy](patterns/behavioral/strategy.py) | selectable operations over the same data |
| 模板方法模式 [template](patterns/behavioral/template.py) | an object imposes a structure but takes pluggable components |
| 访问者模式 [visitor](patterns/behavioral/visitor.py) | invoke a callback for all items of a collection |

__Design for Testability Patterns__:

| Pattern | Description |
|:-------:| ----------- |
| [dependency_injection](patterns/dependency_injection.py) | 3 variants of dependency injection |

__Fundamental Patterns__:

| Pattern | Description |
|:-------:| ----------- |
| [delegation_pattern](patterns/fundamental/delegation_pattern.py) | an object handles a request by delegating to a second object (the delegate) |

__Others__:

| Pattern | Description |
|:-------:| ----------- |
| [blackboard](patterns/other/blackboard.py) | architectural model, assemble different sub-system knowledge to build a solution, AI approach - non gang of four pattern |
| [graph_search](patterns/other/graph_search.py) | graphing algorithms - non gang of four pattern |
| [hsm](patterns/other/hsm/hsm.py) | hierarchical state machine - non gang of four pattern |


Videos
------
[Design Patterns in Python by Peter Ullrich](https://www.youtube.com/watch?v=bsyjSW46TDg)

[Sebastian Buczyński - Why you don't need design patterns in Python?](https://www.youtube.com/watch?v=G5OeYHCJuv0)

[You Don't Need That!](https://www.youtube.com/watch?v=imW-trt0i9I)

[Pluggable Libs Through Design Patterns](https://www.youtube.com/watch?v=PfgEU3W0kyU)


Contributing
------------
When an implementation is added or modified, please review the following guidelines:

##### Output
All files with example patterns have `### OUTPUT ###` section at the bottom
(migration to OUTPUT = """...""" is in progress).

Run `append_output.sh` (e.g. `./append_output.sh borg.py`) to generate/update it.

##### Docstrings
Add module level description in form of a docstring with links to corresponding references or other useful information.

Add "Examples in Python ecosystem" section if you know some. It shows how patterns could be applied to real-world problems.

[facade.py](patterns/structural/facade.py) has a good example of detailed description,
but sometimes the shorter one as in [template.py](patterns/behavioral/template.py) would suffice.

In some cases class-level docstring with doctest would also help (see [adapter.py](patterns/structural/adapter.py))
but readable OUTPUT section is much better.


##### Python 2 compatibility
To see Python 2 compatible versions of some patterns please check-out the [legacy](https://github.com/faif/python-patterns/tree/legacy) tag.

##### Update README
When everything else is done - update corresponding part of README.


##### Travis CI
Please run `tox` or `tox -e ci37` before submitting a patch to be sure your changes will pass CI.

You can also run `flake8` or `pytest` commands manually. Examples can be found in `tox.ini`.

## Contributing via issue triage [![Open Source Helpers](https://www.codetriage.com/faif/python-patterns/badges/users.svg)](https://www.codetriage.com/faif/python-patterns)

You can triage issues and pull requests which may include reproducing bug reports or asking for vital information, such as version numbers or reproduction instructions. If you would like to start triaging issues, one easy way to get started is to [subscribe to python-patterns on CodeTriage](https://www.codetriage.com/faif/python-patterns).
