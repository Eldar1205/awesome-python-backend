
# Python Learning for Backend/Data Engineers from zero to hero

This document is an index for online reading materials in order to learn Python and backend development/engineering concepts from scratch and develop a mastery sufficient for Senior/Principal Backend Engineers and Data Engineers.

If you wish to contribute a change, please create a feature branch from 'main' branch and submit a pull request.
<br>

  - **[Environment setup & installations](#environment-setup---installations)**
  - **[General tutorials & guides](#general-tutorials---guides)**
  - **[Important Standard Library Modules](#important-standard-library-modules)**
  - **[Topics Index](#topics-index)**
	  * [QoL libraries](#qol-libraries)
	  * [Unit Testing](#unit-testing)
	  * [Code Quality and Linting](#code-quality-and-linting)
	  * [Tips & Tricks](#tips---tricks)
	  * [Documentation](#documentation)
	  * [Distributed Programming Frameworks](#distributed-programming-frameworks)
<br>
## Environment setup & installations

**First start by setting up a Python development environment - either interactive mode with**  ***Jupyter***  **-or- an IDE where you can write code and then execute once done.**

_Tip:_ if you work on a personal PC not meant solely for development purposes you can use a VM to install whatever is required to develop Python in an isolated environment. To run a VM on Windows PC we recommend [Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/quick-create-virtual-machine) (requires Windows Pro on your PC), it works best for running a Windows VM, for running a Linux VM we recommend [Oracle Virtual Box](https://www.virtualbox.org/) but Hyper-V works as well, for personal development it's a matter of preference, you can read more [here](https://www.makeuseof.com/tag/virtualbox-vs-vmware-vs-hyper-v/).

1. Python Installation
	1. [Windows] [Python installation](https://www.python.org/downloads/) - for Windows make sure to have both Python and its scripts in your PATH environment variables, they'll be in your Python installation directory, example:
	[![image](https://www.linkpicture.com/q/pythoninstall.png)](https://www.linkpicture.com/view.php?img=LPic63e011b7d882d1226923044)
	 2. [Linux] {Github credit: m3et} If you are using Ubuntu 16.10 or newer, then you can easily install Python 3.10 with the following commands:<br>
`$ sudo apt-get update`
`$ sudo apt-get install python3.10` <br>
If you're using another version of Ubuntu (e.g. the latest LTS release) or you want to use a more current Python, we recommend to use the [deadsnakes PPA](https://launchpad.net/~deadsnakes/+archive/ubuntu/ppa) to install Python 3.10:<br>
`$ sudo apt-get install software-properties-common`
`$ sudo add-apt-repository ppa:deadsnakes/ppa`
`$ sudo apt-get update`<br>
`$ sudo apt-get install python3.10`<br>
`#You can specify the exact python version if needed`<br>
To verify which version of Python 3 you have installed, open a command prompt and run:<br>
`$ python3 --version`
<br>
2. Understand virtual environments: [Real Python reference](https://realpython.com/python-virtual-environments-a-primer/) & [Official docs reference](https://docs.python.org/3/tutorial/venv.html)
3. [JupyterLab and Jupyter Notebook](https://jupyter.org/) are notebook style editors for Python where you can write code, save data, write free text explanations, etc.
	1. [Windows] [Python & Jupyter Notebook Windows installation guide](https://medium.com/@kswalawage/install-python-and-jupyter-notebook-to-windows-10-64-bit-66db782e1d02)
4. [PyCharm IDE](https://www.jetbrains.com/pycharm/) - PyCharm is a very popular IDE for Python from JetBrains, the same company that delivers IntelliJ IDE.
5. Python in VS Code - VS Code is a general purpose extremely popular IDE based almost entirely on extensions & plugins: [VS Code reference](https://code.visualstudio.com/docs/languages/python) & [Real Python reference](https://realpython.com/python-development-visual-studio-code/).
6. {Github credit: lironsoffer} [Google Colab](https://colab.research.google.com/) - online Python notebook style editor by Google. Provides access to free GPU.
7. {Github credit: lironsoffer} [Dataspell](https://www.jetbrains.com/dataspell/) - a relatively new IDE from JetBrains which supports running notebooks cells (.ipynb files). Has features of traditional IDE as opposed to Jupyter Notebooks and JupyterLabs.

## General tutorials & guides

**With a development environment ready you can now learn how to write Python code.**

1. [W3Schools](https://www.w3schools.com/python/default.asp) - beginners
2. [Real Python](https://realpython.com/start-here/) - intermediate, in depth, articles referencing useful open source packages
3. [Python official docs tutorial](https://docs.python.org/3/tutorial/index.html) - exhaustive, most in depth, tutorial for must and should know built-in Python capabilities
4. {Github credit: lironsoffer}[Automate the boring stuff](https://automatetheboringstuff.com/) - beginner-intermediate. Task oriented online book.
5. [GeekForGeeks](https://www.geeksforgeeks.org/python-programming-language/?ref=shm) - beginner-intermediate, website with short tutorials in many subjects. Contains many examples and a "try it out" widget.

_Tip:_ start from going over <u>W3Schools</u> and what it has to offer, it's basic, then for every topic you wish to learn start with some exercise from <u>Automate the boring stuff</u> and read some <u>Real Python</u> article if exists, and if needed read Python official docs; Real Python is more accessible.

## Important Standard Library Modules

**Python ships with some standard modules, some are useful and even essential for day-to-day backend development.**

_Tip:_ to learn a moduleGoogle "python \<module name\>" and you'll usually find a good Real Python article and many additional useful references. Read official Python docs last.

Python official module docs: [https://docs.python.org/3/py-modindex.html](https://docs.python.org/3/py-modindex.html)

1. _builtins_ module - primary module auto-imported to every scope
2. _enum_ module - support for enums
3. _abc_ module - implementing Abstract Classes
4. _random_ module - enable randomized algorithms
5. _datetime_ module - working with date, times, and time differences
6. _decimal_ module - working with precise decimal floating point arithmetic
7. _uuid_ module - Python's built-in uuid/guid type
8. _re_ module - working with regular expressions
9. _math_ module - math constants (e.g. PI), functions, etc.
10. _itertools_ module - efficient looping with iterators
	1. **cycle** - infinite cyclic iterations
	2. **repeat** - infinite/bounded repetitions of a value
	3. **chain / chain.from\_iterable** - concat any number of iteratables
	4. **compress** - filter iterable by matching indicators iterable
	5. **filterfalse** - filter iterable by predicate
	\* can also use comprehensions to achieve the same
	6. **groupby** - group's iterables items by key function
	7. **islice** - behaves as Sequences' slicing syntax
	8. **zip\_longest** - like zip only pads the shorter iterable to match the longer one
	9. **product** - cartesian product of any number of iterables (returns iterable of tuples)
\* can also use nested comprehensions to achieve the same
	10. **combinations\_with\_replacements** - returns an iterable with every pair (left, right) of items from the input iterable such that left \<= right
11. _functools_ module - higher order functions
	1. **partial / partialmethod** - fixes some arguments of a function and returns the resulting function
	2. **reduce** - aggregates an iterable's items projected by a function
	3. **\*\* singledispatch / singledispatchmethod** - generic method with implementations per type
12. _operator_ module - Python operators/keywords as functions for functional programming
13. _array_ module - efficient arrays of numeric values
14. _collections.abc_ module - abstract classes for implementing custom collections
	\* Note to use Generic versions with type-hints
15. _collections_ module - specialized built-in collections
	1. **dequeue** - queue/stack
	2. **ChainMap** - efficient view of multiple dictionaries as single mapping
	3. **Counter** - histograms of keys
	4. **defaultdict** - dictionary with default value factory
	5. **UserDict, UserList, UserString** - simpler subclassing of dict, list, string
	\* Note to use Generic versions with type-hints
16. _typing_ module - for type hints support, specialized strongly typed classes and using advanced typing features
	1. **TypedDict** , [a dictionary with typed values](https://dafoster.net/projects/typeddict/)
17. _contextlib_ module - for implementing context managers which can be bound to "with" statements, stack them, suppress exceptions, etc.
18. \*\* _dataclasses_ module - for creating idiomatic data classes
19. _asyncio_ module - support for async IO, futures, coroutines and tasks
20. _contextvars_ module - support for async flows local state represented as contexts
21. \*\* _json_ module - working with JSON representations
22. _\*\* pickle_ module - binary serialization
23. _logging_ module - logging capabilities built-in, used by most third-party libs to emit logs
24. _\*\* unittest_ module - unit testing framework built-in
25. _unittest.mock_ module - mocking capabilities for tests, designed for unit tests
26. _secrets_ module - cryptography classes & algorithms
27. _pathlib_ module - utilities for file system paths, particularly useful **Path** type
28. _ipaddress_ module - provides types representing IP addresses, e.g. **IPv4Address**

\*\* better third-party module below

## Topics Index

**Learning materials can also be indexed by topics common to backend development in any prog. language/platform. The index doesn't include specific technologies, e.g. SQL databases, MongoDB, GraphQL, Google APIs, etc.; it includes topics all backend software engineers can find useful.**

DISCLAIMER: All below async references were added taking into consideration only the _asyncio_ built-in module. I'm currently looking into _trio_ and _AnyIO_ as alternatives.

1. <u>Packages & Modules</u> - split Python code into multiple files & packaging reusable Python code into a single package: [Real Python reference](https://realpython.com/python-import/) & [Official docs reference](https://docs.python.org/3/tutorial/modules.html)
	1. Example _asyncio_ module source code, look at [\_\_init\_\_.py](https://github.com/python/cpython/tree/3.9/Lib/asyncio)
	2. Packaging modules to distribute [benefit from Python Wheels](https://realpython.com/python-wheels/)
2. <u>Descriptors</u> - reusable logic wrapping attributes access, generalizing properties which are defined using getter/setter/deleter methods: [Official docs reference](https://docs.python.org/3/howto/descriptor.html)
3. <u>Decorators</u> - wraps method invocations with custom logic, or decorate classes for customization: [Real Python reference](https://realpython.com/primer-on-python-decorators/)
4. {Github credit: lironsoffer} <u>Magic (Dunder) Methods</u> - special builtin methods in python. Identified by two prefix and suffix underscores in the method name, e.g. \_\_str\_\_ magic method: [Real Python reference](https://realpython.com/operator-function-overloading/) & [Official docs reference](https://docs.python.org/3/reference/datamodel.html#special-method-names)
5. <u>Static typing</u> - Python type hints: [Real Python reference](https://realpython.com/python-type-checking/) & [Official docs reference](https://docs.python.org/3/library/typing.html)
	1. **Union**
	2. **Optional**
	3. [**Generic**](https://mypy.readthedocs.io/en/stable/generics.html) (generic constraints, covariance, contravariance, etc.)
	4. [**Protocol**](https://mypy.readthedocs.io/en/stable/protocols.html) (essentially define interfaces for static type check purposes, can support runtime _isinstance_ and _issubclass_ checks using a [decorator](https://docs.python.org/3/library/typing.html#typing.runtime_checkable))
	* [_MyPy_](https://mypy.readthedocs.io/en/stable/introduction.html) is best for static type checks, and the docs are very useful to learn how to use type hints 
6. <u>Exceptions</u> - [Official docs built-in exceptions reference](https://docs.python.org/3/library/exceptions.html)
	1. Tip: Derive from _BaseException_ instead of _Exception_ in order to implement an exception type that won't be caught by general purpose _except: Exception_ blocks. This technique is used for cancellations exceptions raised by async/await libraries; general purpose exception handling shouldn't handle cancellations.
7. <u>Weak references</u> - reference an object such that the reference doesn't keep it alive: [Official docs reference](https://docs.python.org/3/tutorial/stdlib2.html#weak-references)
8. <u>Concurrency & Multithreading</u> - using a thread pool, locking, producer-consumer patterns, thread locals, async IO, async generators & comprehensions, futures, async context variables, async synchronization primitives: [Real Python Concurrency reference](https://realpython.com/python-concurrency/) & [Real Python asyncio reference](https://realpython.com/async-io-python/) & [Official docs asyncio reference](https://docs.python.org/3/library/asyncio.html)
9. <u>Json</u> - fast library for working with JSON, supports dataclasses serialization - [_orjson_](https://github.com/ijl/orjson)
10. <u>Data Models</u> - represent system entities as typed data models designed for static type checks - [_pydantic_](https://pydantic-docs.helpmanual.io/):
	1. Data models validations support. including support for built-in Python types as well as additional _pydantic_ useful types mentioned in b) and c) and simple support for custom data validations for many scenarios
	2. Provides several QoL value objects to use as fields of data models, most useful IMO: **HttpUrl** , **EmailStr** , **Json[T], SecretStr (a string hidden from logs)**
	3. Provides constrained types such that values follow some restrictions like strings/lists of certain length, most useful IMO: **constr, conint, PositiveInt, conlist, conset**
	4. Supports reusable models configurations via inheritance from custom **BaseModel** and reusable validations using **validator** helper
	5. Data models JSON support - serialization and deserialization, including support for 3rd party JSON libraries e.g. [_orjson_](https://pydantic-docs.helpmanual.io/usage/exporting_models/#custom-json-deserialisation)
	6. Support for converting custom classes (e.g. ORM objects) to data models
	7. Support for Python's built-in _dataclasses_ module, essentially extending it
	8. Has [_MyPy_](https://pydantic-docs.helpmanual.io/usage/mypy/)[plugin](https://pydantic-docs.helpmanual.io/usage/mypy/) to cover static type check scenarios for creating models using the _pydantic_ syntax
	9. [Integrates with](https://pydantic-docs.helpmanual.io/hypothesis_plugin/)[_hypothesis_](https://pydantic-docs.helpmanual.io/hypothesis_plugin/)[library](https://pydantic-docs.helpmanual.io/hypothesis_plugin/) for theory testing of data models
	10. Code generation based on JSON schema, JSON data, YAML data, OpenAPI 3
	\* There's an alternative 3rd party called [_attrs_](https://www.attrs.org/en/stable/), comparisons can be found online
11. {Github credit: lironsoffer} <u>Data Manipulation</u> - some libraries are used to manipulate/transform data
	1. [NumPy](https://numpy.org/) **-** a Python library used for working with arrays
	2. [Pandas](https://pandas.pydata.org/docs/user_guide/10min.html) - fast, powerful, flexible and simple data analysis & manipulation library
	3. [Scipy](https://scipy.org/) - a scientific computation library that uses NumPy underneath
12. <u>App Settings / Configuration</u> - representation and access to application settings & configurations, e.g. connection strings, services URLs, anything that shouldn't be hard coded and should be accessible to system code in a configurable manner.
	1. Extensive support using [_dynaconf_](https://www.dynaconf.com/) supporting multi-environment, many formats, external config stores (e.g. Redis), unit tests and more
	2. Basic support from [_pydantic_](https://pydantic-docs.helpmanual.io/usage/settings/) library above, can be extended to support [multi-environment](https://rednafi.github.io/digressions/python/2020/06/03/python-configs.html) and custom loaders can make it leverage _dynaconf_
13. <u>File System</u>
	1. file system access using async IO - [_aiofiles_](https://pythonrepo.com/repo/Tinche-aiofiles-python-files)
	2. Path object: [Real Python reference](https://realpython.com/python-pathlib/)
14. <u>Http Client</u> - sending HTTP requests using async IO, popular alternatives:
	1. [_httpx_](https://www.python-httpx.org/)
		1. Supports: HTTP/2, client certificate, full request & response hooks, env variables config, [OAuth2 extension](https://colin-b.github.io/httpx_auth/)
		2. Doesn't support: websockets
	2. [_aiohttp_](https://docs.aiohttp.org/en/stable/)
		1. Supports: web sockets, client certificate, partial request & response hooks (allowed modifications: requests headers, enables Authentication flows), OAuth2 ([via another package](https://docs.authlib.org/en/v0.12.1/client/aiohttp.html))
		2. Doesn't support: HTTP/2, env variables config
	* Recommended _httpx_ for richer feature set, for web sockets client use [_websockets_](https://websockets.readthedocs.io/en/stable/) 
15. <u>SQL ORM</u> - object relational mapper for working with SQL databases - [_SQLAlchemy_](https://www.sqlalchemy.org/)
	1. [Integrates with](https://docs.sqlalchemy.org/en/14/orm/extensions/mypy.html)[_MyPy_](https://docs.sqlalchemy.org/en/14/orm/extensions/mypy.html) for type checking _SQLAlchemy_ models
	2. [Integrates with](https://pydantic-docs.helpmanual.io/usage/models/#orm-mode-aka-arbitrary-class-instances)[_pydantic_](https://pydantic-docs.helpmanual.io/usage/models/#orm-mode-aka-arbitrary-class-instances) to map _SQLAlchemy_ models to/from _pydantic_ models
	3. [Integrates with](https://fastapi.tiangolo.com/tutorial/sql-databases/)[_FastAPI_](https://fastapi.tiangolo.com/tutorial/sql-databases/) to expose CRUD API on top of SQL databases
	4. [Integrates with](https://flask-sqlalchemy.palletsprojects.com/en/2.x/)[_Flask_](https://flask-sqlalchemy.palletsprojects.com/en/2.x/) to expose CRUD API on top of SQL databases
	5. _Django_ has a built-in ORM, so no _SQLAlchemy_ integration
16. <u>Fault tolerance</u> - I/O can fail, e.g. services can return HTTP error responses, SQL queries/commands can fail. There are known ways to handle failures:
	1. <u>Retry policies</u> - retrying failed API requests, SQL queries/commands, etc. based on some retry policy - [_tenacity_](https://tenacity.readthedocs.io/en/latest/), type hints support [incomplete](https://github.com/jd/tenacity/issues/230). There's also [_aioretry_](https://github.com/kaelzhang/python-aioretry) which requires implementing the retry policy yourself but supports type hints.
	2. <u>Circuit Breaker</u> - block execution of logic if it failed too many times recently, e.g. if SQL queries started failing due to overload on the SQL database, don't submit new queries for a while and let the database recover - [_pybreaker_](https://github.com/danielfm/pybreaker)
17. <u>Binary Serialization</u> - [_MessagePack_](https://msgpack.org/) is a very efficient general purpose format - [_msgpack_](https://github.com/msgpack/msgpack-python)
18. <u>Logging</u> - logging capabilities for Python: [Real Python reference](https://realpython.com/python-logging/)
	1. Logging setup helper library - [_daiquiri_](https://daiquiri.readthedocs.io/en/latest/)
	2. Structured logging - emit logs as messages + key-value pairs - [_structlog_](https://www.structlog.org/en/stable/why.html)
19. <u>DI Container</u> - enable DI design principle with auto-wiring of dependencies - [_lagom_](https://lagom-di.readthedocs.io/en/latest/)
	1. Built-in integration with FastAPI & Flask, including per-request injectables
	2. There's also [_rodi_](https://github.com/Neoteroi/rodi) which is inspired by .Net built-in DI container, less features and less Github activity (commits/contributors/etc.) but simpler to use
20. <u>CLI</u> - create applications with command-line interface - [_typer_](https://typer.tiangolo.com/)
	1. Async main/command tip below "Sync to Async decorator"
21. <u>Web frameworks</u> - build web services/applications that either provide HTML pages/components via Server Side Rendering (SSR) and templating, or RESTful HTTP APIs, or both. There are some popular alternatives:
	1. [_FastAPI_](https://fastapi.tiangolo.com/) - modern, specialized for type hints, supports explicit async IO and auto-generates Swagger UI (API spec)
	2. [_Flask_](https://flask.palletsprojects.com/en/2.0.x/) _-_ exists since 2010, no explicit async IO support
	 3. [_Django_](https://www.djangoproject.com/) - a very extensive framework with many many features, essentially an ecosystem, well documented, [limited explicit async IO support](https://docs.djangoproject.com/en/3.2/topics/async/)
	 \* Comparisons exist online, _FastAPI_ is mostly preferred due to explicit async IO
	 \*  Useful [web frameworks reference](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Web_frameworks) on how to evaluate them 
 22. <u>Background tasks scheduling</u> - run background workers such that work can be scheduled (one-time or periodic):
	 1. [_apscheduler_](https://github.com/agronholm/apscheduler) is a scheduler for a single worker with flexible jobs store choices
	 2. [_arq_](https://arq-docs.helpmanual.io/#) is a lightweight distributed task queue built on top of [_Redis_](https://redis.io/) 
	 * See [Distributed programming frameworks](#distributed-programming-frameworks) section for more complete and heavyweight solutions.
22. <u>gRPC Client & Server</u> - communication using gRPC protocol which is more suited than RESTful HTTP for communication between services that are part of the same system since performance is better and describing contracts using RPC (remote procedure call) is simpler conceptually compared to RESTful HTTP contracts describing resources with URLS and verbs as actions - [Real Python reference](https://realpython.com/python-microservices-grpc/) & [Official Google docs reference](https://grpc.io/docs/languages/python/)
23. <u>GraphQL</u> - data query language for web services - [_graphene_](https://graphene-python.org/)
	1. [Integrates with](https://github.com/graphql-python/graphene-pydantic)[_pydantic_](https://github.com/graphql-python/graphene-pydantic)to query over _pydantic_ models
	2. [Integrates with](https://github.com/ciscorn/starlette-graphene3)[_FastAPI_](https://github.com/ciscorn/starlette-graphene3) to expose GraphQL API, usually over _pydantic_ models
	3. [Integrates with](https://towardsdatascience.com/graphql-with-python-flask-560d083ffa01)[_Flask_](https://towardsdatascience.com/graphql-with-python-flask-560d083ffa01) to expose GraphQL API over whatever data you choose
	4. [Integrates with](https://docs.graphene-python.org/projects/django/en/latest/)[_Django_](https://docs.graphene-python.org/projects/django/en/latest/) to expose GraphQL API over _Django_ models
24. <u>Event Sourcing</u> - represent persistent entities as changesets logs and incorporate pub-sub notifications for entities' changes to update representations of the entities in additional data stores, update search indexes, notify other systems, etc. - [_eventsourcing_](https://eventsourcing.readthedocs.io/en/v9.1.1/)
25. <u>Reactive Extensions</u> - building asynchronous event-based programs using observable collections as a concept for working with streams of asynchronous data, useful approach for implementing custom data pipelines in your Python service - [_RxPY_](https://github.com/ReactiveX/RxPY)
26. <u>Docker</u> - Docker containers are amazing for microservices and have become the de-facto standard for building & deploying them: [Docker official docs reference](https://docs.docker.com/)
	1. [Docker with Python in VS Code reference](https://code.visualstudio.com/docs/containers/quickstart-python)
	2. [Real Python Docker tutorials reference](https://realpython.com/tutorials/docker/)

### QoL libraries

**For day-to-day development there are some Quality of Life libraries that can speed up development, make us more productive, spare us bugs, etc.**

Comprehensive useful Python libraries & frameworks index: [https://github.com/vinta/awesome-python](https://github.com/vinta/awesome-python)

1. nameof() operator for names refactoring support - [_python-varname_](https://github.com/pwwang/python-varname)
2. URL type - [_yarl_](https://pypi.org/project/yarl/)
\* _pydantic_ also ships a [URL type](https://pydantic-docs.helpmanual.io/usage/types/#urls), however it's not useful for constructing URLs as _yarl_
3. Async IO enhancements:
	1. fast implementation for the _asyncio_ module event loop - [_uvloop_](https://github.com/MagicStack/uvloop)
	2. async versions of built-in functions - [_asyncstdlib_](https://asyncstdlib.readthedocs.io/en/latest/), especially important _aclosing_ to properly cleanup after async generators, see [this discussion](https://vorpus.org/blog/some-thoughts-on-asynchronous-api-design-in-a-post-asyncawait-world/#cleanup-in-generators-and-async-generators) for details.
	3. async general purpose utilities - [_aiomisc_](https://aiomisc.readthedocs.io/en/latest/)
		1. [Decorator support](https://aiomisc.readthedocs.io/en/latest/timeout.html) for **asyncio.waitfor** function
		2. Wait for any awaitable using [**select**](https://aiomisc.readthedocs.io/en/latest/utils.html#select)
		3. Turn a sync func into an async func using [**awaitable**](https://aiomisc.readthedocs.io/en/latest/utils.html#awaitable)
		4. Async timer using [**PeriodicCallback**](https://aiomisc.readthedocs.io/en/latest/utils.html#periodic-callback) / [Cron scheduling](https://aiomisc.readthedocs.io/en/latest/utils.html#cron-callback)
	4. async caching decorator, prevents [dog-piling](https://en.wikipedia.org/wiki/Cache_stampede), flexible yet simple - [_py-memoize_](https://memoize.readthedocs.io/en/latest/)
4. Collections:
	1. Immutable dictionary - [_immutables_](https://github.com/MagicStack/immutables)
	2. Bidirectional dictionary - [_bidict_](https://bidict.readthedocs.io/en/main/)
	3. Multivalue dictionary - [_multidict_](https://pypi.org/project/multidict/)
	4. Sorted collections (set, list, dict) - [_sortedcontainers_](https://github.com/grantjenks/python-sortedcontainers)
5. Functional Programming enhancements:
	1. Higher order functions & iterables - [_toolz_](https://toolz.readthedocs.io/en/latest/heritage.html) & [_more-itertools_](https://more-itertools.readthedocs.io/en/stable/api.html)
	2. LINQ for Python, inspired by C# LINQ - [_py-linq_](https://viralogic.github.io/py-enumerable/)
	3. Piping syntax: [_pipe_](https://github.com/JulienPalard/Pipe), [useful reference](https://towardsdatascience.com/write-clean-python-code-using-pipes-1239a0f3abf5)
	4. Pattern matching capabilities - [_pampy_](https://github.com/santinic/pampy) is simple and very popular
	5. Typeclasses polymorphism (better alternative for **singledispatch** ) - [_classes_](https://classes.readthedocs.io/en/latest/index.html)
	6. Type-safe alternative to throwing exceptions by returning Result objects - [_result_](https://github.com/dbrgn/result)
6. Augment static type checks with very efficient randomized runtime checks that support [type annotations](https://docs.python.org/3/library/typing.html#typing.Annotated) with custom validations - for cases where static type checks aren't sufficient, e.g. you want to assert type annotations not statically checked, or you are developing a Python library (its users might not perform static type checks when calling your library's classes/functions/etc.) - [_beartype_](https://github.com/beartype/beartype)
7. bject-object mapper for converting between similar classes - [_object-mapper_](https://github.com/marazt/object-mapper) or [_odin_](https://pythonhosted.org/odin/ref/mapping/classes.html)

### Unit Testing

**Automated Testing is about verifying your system code works as expected with test code that will execute your system code and assert expectations on its behavior.**
**Unit Testing in particular is about automatic testing for small atomic code entities that have some API encapsulating implementation details, usually a class but not necessarily.**

1. VS Code extension to run & debug tests in VS Code - [_Python Test Explorer_](https://marketplace.visualstudio.com/items?itemName=LittleFoxTeam.vscode-python-test-adapter)
2. Recommended test framework is _pytest_: [Real Python reference](https://realpython.com/pytest-python-testing/) & [Library docs reference](https://docs.pytest.org/en/6.2.x/)
3. Write async tests to test async system code - [_pytest-asyncio_](https://github.com/pytest-dev/pytest-asyncio)
4. Mocking - _unittests.mock_ & _pytest-mock_: [Useful article](https://changhsinlee.com/pytest-mock/) & [Real Python reference](https://realpython.com/python-mock-library/) & [Library docs reference](https://github.com/pytest-dev/pytest-mock)
\* Issue: no type hints for the mocked class/function.
5. Fake data generator - [_faker_](https://faker.readthedocs.io/en/master/)
	1. If you use _pydantic_, there's [_pydantic-factories_](https://pythonrepo.com/repo/Goldziher-pydantic-factories-python-machine-learning) to build fake models
6. Improved assertions syntax (fluent syntax) - [_assertpy_](https://github.com/assertpy/assertpy)
7. Test coverage reports - [_pytest-cov_](https://pytest-cov.readthedocs.io/en/latest/)
8. BDD testing - [_pytest-bdd_](https://pytest-bdd.readthedocs.io/en/latest/)
9. Theory testing - [_hypothesis_](https://hypothesis.readthedocs.io/en/latest/index.html) library
10. Parameterized tests using fixtures as parameters values' providers - [_pytest-lazy-fixture_](https://pypi.org/project/pytest-lazy-fixture/)
11. Setup mock return values (or raised exceptions) with fluent syntax by matching arguments - [_nextmock_](https://github.com/pilagod/nextmock)
12. Mock **datetime** - [_freezegun_](https://github.com/spulec/freezegun)
13. Mocking HTTP client
	1. Mocking _aiohttp_ - [_aioresponses_](https://github.com/pnuckowski/aioresponses)
	2. Mocking _httpx -_ [_respx_](https://lundberg.github.io/respx/)

<u>Versioning & Environments Management</u>

**When there's multiple Python versions / multiple virtual environments / many 3rd party packages, maintenance becomes complex and there are tools to simplify it.**

1. Package managers:
	1. [_Poetry_](https://python-poetry.org/) - Virtual envs package management solution similar to _npm_
	2. {Github credit: lironsoffer} [pyenv](https://github.com/pyenv/pyenv) - Python versioning manager

### Code Quality and Linting

**To maintain high quality code it's useful to maintain coding standards and there are tools that can help with and even handle maintaining those standards.**

1. Static type checker - [_MyPy_](https://mypy.readthedocs.io/en/stable/introduction.html)
2. Style guide enforcement - [_Flake8_](https://flake8.pycqa.org/en/latest/). Useful extensions:
	1. [_flake8-builtins_](https://github.com/gforcada/flake8-builtins) - checks for accidental use of builtin functions as names
	2. [_flake8-comprehensions_](https://github.com/adamchainz/flake8-comprehensions) - checks for misuse or lack of use of comprehensions
	3. [_flake8-logging-format_](https://github.com/globality-corp/flake8-logging-format) - ensures logs use extra arguments and exception()
	4. [_flake8-mutable_](https://github.com/ebeweber/flake8-mutable) - checks for mutable default parameter values Python issue
	5. [_pep8-naming_](https://github.com/PyCQA/pep8-naming) - checks that names follow Python standards defined in PEP8
	6. [_flake8-pytest-style_](https://github.com/m-burst/flake8-pytest-style) - check that pytest unit tests are written according to style
	7. [_flake8-simplify_](https://github.com/MartinThoma/flake8-simplify) _-_ checks for general Python best practices for simpler code
3. Code formatter - [_Black_](https://github.com/psf/black)
4. Import statements sorting - [_isort_](https://github.com/PyCQA/isort)
5. [VS Code Python Linting](https://code.visualstudio.com/docs/python/linting) - so VS Code will run _MyPy_, _Flake8_ (and others)
6. [VS Code _Black_ and _isort_](https://cereblanco.medium.com/setup-black-and-isort-in-vscode-514804590bf9)
7. [Github action for Python Code Quality and Linting](https://github.com/marketplace/actions/python-code-quality-and-lint)

### Tips & Tricks

**Some useful tips & tricks that can't be classified as some stand-alone topic.**

1. Delete a virtual environment in 3 steps executed from a cmd on an active environment:
	1. command: pip freeze \> requirements.txt
	2. command: pip uninstall -r requirements.txt -y
	3. command: deactivate
	4. action: delete the environment's folder
2. [Centralize imports in a reusable imports file](https://stackoverflow.com/questions/59781313/is-possible-to-reuse-import-code-in-python)
3. Mark parameters as positional only so their names can be used in keyword arguments: [Official docs reference](https://docs.python.org/3/whatsnew/3.8.html#positional-only-parameters)
4. [Efficient string concat](https://waymoot.org/home/python_string/) - converse memory that would be used in loop of string concat ops
5. Sync to Async decorator - let's say a function is expected to not be async when invoked, and we want to implement it as async so it blocks until completion when invoked as a sync function, then we can apply a general decorator. Code [here](https://github.com/pallets/click/issues/85#issuecomment-503464628).
\* There's an issue with type-hints to express the decorator receiving a sync callable and returning an async callable, solved in Python 3.10: [Parameter Specific Variables](https://docs.python.org/3.10/whatsnew/3.10.html).
6. Get a function's caller info: code of "findCaller" method in [Python's logging source code](https://github.com/python/cpython/blob/3.9/Lib/logging/__init__.py)
2. [Translate (some) LINQ to Python](https://www.c-sharpcorner.com/blogs/linq-in-python-for-c-sharp) instead of using _py-linq_ library above
3. [Correctly executing sync/async generators](https://vorpus.org/blog/some-thoughts-on-asynchronous-api-design-in-a-post-asyncawait-world/#cleanup-in-generators-and-async-generators) so a _finally_ clause runs explicitly
4. [Multi-core async IO](https://www.youtube.com/watch?v=0kXaLh8Fz3k&t=630s) (multiple event loops)
5. [Fork-join pattern with pool executors](https://rednafi.github.io/digressions/python/2020/04/21/python-concurrent-futures.html), can read about Fork-join concurrency pattern [here](https://en.wikipedia.org/wiki/Fork%E2%80%93join_model).
6. [Limiting concurrency for large number of async IO tasks](https://www.artificialworlds.net/blog/2017/05/31/python-3-large-numbers-of-tasks-with-limited-concurrency/)
7. [Limiting concurrency for outgoing HTTP requests sent with _aiohttp_](https://pawelmhm.github.io/asyncio/python/aiohttp/2016/04/22/asyncio-aiohttp.html)

### Documentation

**Documenting modules/classes/functions/etc. enables other team members (and you in the future) to understand what some API in the code does without having to inspect how it's implemented. When developing open-source the documentation is a must and needs to be available as professional online docs and not just in-code docs.**

1. Python Documentation guide: [Real Python reference](https://realpython.com/documenting-python-code/#documentation-tools-and-resources)
2. [NumPy Docstrings guidelines](https://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_numpy.html) - recommended standard docstrings style, not only one
3. Enforce docstrings style - [_pydocstyle_](https://www.pydocstyle.org/en/stable/index.html)
	1. [_Flake8_ plugin for _pydocstyle_ ](https://pypi.org/project/flake8-docstrings/)
4. [Professional documentation with _reStructuredText_](https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html) (to publish PDF/HTML/etc.)
5. Markdown files are [supported as is in VS Code](https://code.visualstudio.com/docs/languages/markdown), e.g. Git README.md files
	1. Useful VS Code extension - [_Markdown All in One_](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
	2. [Github markdown quick tutorial](https://guides.github.com/features/mastering-markdown/)

### Distributed programming frameworks

**In many cases the backend architecture needs to include highly scalable distributed services where clusters of service instances can efficiently communicate between each other, persist data, recover from crashes, load balance work, etc.**
**Good frameworks can make it simpler to implement them by providing useful abstractions for distributed programming/computing and persisting durable state.**

The frameworks were chosen for their wide adoption, great features, accessible documentation and supporting modern Python features such as async-await, type hints, etc.
\* Most frameworks build on some data store that's referenced without explanations.
\* General purpose containers orchestrators are great alternatives, e.g. [_Kubernetes_](https://kubernetes.io/)

1. [_Celery_](https://docs.celeryproject.org/en/stable/getting-started/introduction.html) - a distributed task queue & scheduling framework which provides workers that execute RPC jobs consumed from a flexible choice of message brokers (usually [_RabbitMQ_](http://www.rabbitmq.com/) or [_Redis_](https://redis.io/)) with job results persisted to a flexible choice of stores.
Features:
	1. Periodic tasks
	2. Workflows
	3. Custom objects serialization (e.g. can use _pydantic_ models as messages)
	4. Interception for many events using signals APIs
	5. Instrumentation: Monitoring, logging & visualization capabilities
	6. Admin CLI, REST API & Web UI
	7. **No async-await syntax support**, can use [_gevent_](http://gevent.org/) for implicit non-blocking I/O
	8. **No official Windows support**, [there are workarounds](https://stackoverflow.com/questions/37255548/how-to-run-celery-on-windows)
\* [Useful production ready deployment reference](https://medium.com/koko-networks/a-complete-guide-to-production-ready-celery-configuration-5777780b3166)
2. [_Faust_](https://faust.readthedocs.io/en/latest/introduction.html) - a microservices framework which provides abstractions for stream processing with stateful agents that process infinite streams of messages built on top of [_Kafka_](https://kafka.apache.org/) for pub-sub and queue based messaging (extensible), [_RocksDB_](https://rocksdb.org/) as local persistent tables store and (optionally) [_Redis_](https://redis.io/) as distributed cache. Co-founded by [_Celery_](https://docs.celeryproject.org/en/latest/index.html) founder. 
Features:
	1. Queue channels - single consumer per message
	2. Client mode - can send messages to a cluster
	3. Startup tasks
	4. Periodic tasks
	5. Cluster scope synchronization via [leader election](https://en.wikipedia.org/wiki/Leader_election)
	6. Custom objects serialization (e.g. can use _pydantic_ models as messages)
	7. Interception for many events using sensor APIs
	8. Instrumentation: Monitoring, logging & visualization capabilities
	9. Admin CLI & Web UI
	10. Integration testing support (runs locally with everything in-memory)
	11. E2E testing support in staging/production deployments
	12. **No process recovery** for workers - external process supervisors are required
3. [_Airflow_](https://airflow.apache.org/docs/apache-airflow/stable/index.html) - A workflow framework for orchestrating distributed scheduled/triggered workflows (a.k.a DAGs) described using Python scripts such that workers can execute tasks (a.k.a operators) in workflows. Built on top of SQL databases for workflow state persistence and can execute on a cluster directly using [_Celery_](https://docs.celeryproject.org/en/latest/getting-started/)or [_Dask_](https://dask.org/), on a [_Kubernetes_](https://kubernetes.io/) cluster, or managed in [AWS](https://aws.amazon.com/managed-workflows-for-apache-airflow/)/[GCP](https://cloud.google.com/composer). Comes with several core operators and there's a great deal of [independent ones](https://airflow.apache.org/docs/apache-airflow-providers/operators-and-hooks-ref/index.html) and a [registry of built-in & community provided ones](https://registry.astronomer.io/).
Features:
	1. Operators: [Python code](https://airflow.apache.org/docs/apache-airflow/stable/howto/operator/python.html), [Branching](https://www.astronomer.io/guides/airflow-branch-operator), [Run DAG](https://airflow.apache.org/docs/apache-airflow/stable/_api/airflow/operators/trigger_dagrun/index.html#module-airflow.operators.trigger_dagrun), [HTTP request](https://airflow.apache.org/docs/apache-airflow-providers-http/stable/operators.html#howto-operator-simplehttpoperator), [SQL checks](https://airflow.apache.org/docs/apache-airflow/stable/_api/airflow/operators/sql/index.html#module-airflow.operators.sql), etc.
	2. Sensors (operators waiting for events): [Python code](https://airflow.apache.org/docs/apache-airflow/stable/_api/airflow/sensors/python/index.html#module-airflow.sensors.python), [SQL query](https://airflow.apache.org/docs/apache-airflow/stable/_api/airflow/sensors/sql/index.html#module-airflow.sensors.sql), [Time Wait](https://airflow.apache.org/docs/apache-airflow/stable/_api/airflow/sensors/time_delta/index.html#module-airflow.sensors.time_delta), etc.
	3. Cross DAG dependencies (task in DAG X waits for task in DAG Y)
	4. DAG templates with [_Jinja_](https://jinja.palletsprojects.com/en/3.0.x/) and injecting values from env variables/JSON files/etc.
	5. Flexible DAG runs triggers: schedule based, re-runs, tasks results, ad-hoc, etc.
	6. Communications between executing DAGs/tasks
	7. Resources management: tasks priorities, processes pools
	8. Interception for DAG & operator specs and for tasks before execution
	9. Create Python packages with utilities, operators, etc. to reuse in DAG scripts
	10. DAGs validation ([_useful reference_](https://www.astronomer.io/guides/testing-airflow)):
		1. Static DAG analysis with unit tests
		2. Data integrity tests in the DAG itself, e.g. using [_Great Expectations_](https://greatexpectations.io/)
	11. Instrumentation: Monitoring, logging & visualization capabilities
	12. Reusable connections to external services/APIs
	13. Plugins for the Web UI, custom reusable connections and DAG template macros
	14. Admin CLI, REST API & Web UI
	15. **No Windows support** , however [the Linux subsystem can be used](https://towardsdatascience.com/run-apache-airflow-on-windows-10-without-docker-3c5754bb98b4)
4. [_Ray_](https://docs.ray.io/en/master/) - A workers & actors framework for implementing distributed, fault tolerant and scalable applications specialized for data science but usable for any distributed computing. Workers are stateless, actors are stateful, both are Python processes and therefore heavyweight and coarse grained. [Ray has an academic whitepaper](https://www.usenix.org/system/files/osdi18-moritz.pdf).
Features:
	1. Client mode - can send RPC requests to a cluster
	2. Auto-scaling (integrates to cluster managers) based on scale related settings
	3. Java prog. language support (not just Python)
	4. GPU scheduling (for machine learning purposes)
	5. Custom objects serialization
	6. Performance profiling: metrics, visualization, dumps, etc.
	7. Instrumentation: Monitoring, logging & visualization capabilities
	8. Admin CLI & Web UI
	9. Integration testing support (runs locally with multi process cluster)
	10. [_Kubernetes_](https://kubernetes.io/) deployment
	11. Integrates with [_Airflow_](https://airflow.apache.org/) and other useful technologies
	12. **Missing support for interception** for workers and actors
	13. **Alpha quality Windows support** , can try to run on WSL if there are issues
* _Ray_ actors are heavyweight processes, unlike _Orleans_ (.Net) and _Akka_ (Java/Scala).
* Python has a lightweight actors framework [_Thespian_](https://thespianpy.com/doc/#outline-container-org45f5f68), much less popular than above.


