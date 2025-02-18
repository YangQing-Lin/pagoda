Pagoda: Rapid, easy full-stack web development starter kit in Go
Pagoda：快速、简便的 Go 语言全栈网络开发入门套件
------------------------------------------------------------------------------------------------

[![Go Report Card](https://goreportcard.com/badge/github.com/mikestefanello/pagoda)](https://goreportcard.com/report/github.com/mikestefanello/pagoda) [![Test](https://github.com/mikestefanello/pagoda/actions/workflows/test.yml/badge.svg)](https://github.com/mikestefanello/pagoda/actions/workflows/test.yml) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) [![Go Reference](https://pkg.go.dev/badge/github.com/mikestefanello/pagoda.svg)](https://pkg.go.dev/github.com/mikestefanello/pagoda) [![GoT](https://img.shields.io/badge/Made%20with-Go-1f425f.svg)](https://go.dev) [![Mentioned in Awesome Go](https://awesome.re/mentioned-badge.svg)](https://github.com/avelino/awesome-go)

![Logo](https://user-images.githubusercontent.com/552328/147838644-0efac538-a97e-4a46-86a0-41e3abdf9f20.png)

Table of Contents
目录
----------------------

*   [Introduction
导言](#introduction)
*   [Overview
概述](#overview)
*   [Foundation
基金会](#foundation)
*   [Backend
后台](#backend)
*   [Frontend
前端](#frontend)
*   [Storage
存储](#storage)
*   [Screenshots
屏幕截图](#screenshots)
*   [Getting started
开始](#getting-started)
*   [Dependencies
依赖关系](#dependencies)
*   [Start the application
启动应用程序](#start-the-application)
*   [Running tests
运行测试](#running-tests)
*   [Service container
服务集装箱](#service-container)
*   [Dependency injection
依赖注入](#dependency-injection)
*   [Test dependencies
测试依赖性](#test-dependencies)
*   [Configuration
配置](#configuration)
*   [Environment overrides
环境覆盖](#environment-overrides)
*   [Environments
环境](#environments)
*   [Database
数据库](#database)
*   [Auto-migrations
自动迁移](#auto-migrations)
*   [Separate test database
独立的测试数据库](#separate-test-database)
*   [ORM](#orm)
*   [Entity types
实体类型](#entity-types)
*   [New entity type
新实体类型](#new-entity-type)
*   [Sessions
会议](#sessions)
*   [Encryption
加密](#encryption)
*   [Authentication
认证](#authentication)
*   [Login / Logout
登录/注销](#login--logout)
*   [Forgot password
忘记密码](#forgot-password)
*   [Registration
注册](#registration)
*   [Authenticated user
认证用户](#authenticated-user)
*   [Middleware
中间件](#middleware)
*   [Email verification
电子邮件验证](#email-verification)
*   [Routes
道路](#routes)
*   [Custom middleware
定制中间件](#custom-middleware)
*   [Handlers
处理程序](#handlers)
*   [Errors
错误](#errors)
*   [Testing
测试](#testing)
*   [HTTP server
HTTP 服务器](#http-server)
*   [Request / Request helpers
请求/请求帮助](#request--response-helpers)
*   [Goquery
查询](#goquery)
*   [Pages
页面](#pages)
*   [Flash messaging
Flash 消息传送](#flash-messaging)
*   [Pager
呼叫器](#pager)
*   [CSRF](#csrf)
*   [Automatic template parsing
自动模板解析](#automatic-template-parsing)
*   [Cached responses
缓存响应](#cached-responses)
*   [Cache tags
缓存标签](#cache-tags)
*   [Cache middleware
缓存中间件](#cache-middleware)
*   [Data
数据](#data)
*   [Forms
表格](#forms)
*   [Submission processing
提交处理](#submission-processing)
*   [Inline validation
内联验证](#inline-validation)
*   [Headers
页眉](#headers)
*   [Status code
状态代码](#status-code)
*   [Metatags
元标记](#metatags)
*   [URL and link generation
生成 URL 和链接](#url-and-link-generation)
*   [HTMX support
支持 HTMX](#htmx-support)
*   [Rendering the page
渲染页面](#rendering-the-page)
*   [Template renderer
模板呈现器](#template-renderer)
*   [Custom functions
自定义功能](#custom-functions)
*   [Caching
缓存](#caching)
*   [Hot-reload for development
用于开发的热加载](#hot-reload-for-development)
*   [File configuration
文件配置](#file-configuration)
*   [Funcmap](#funcmap)
*   [Cache
缓存](#cache)
*   [Set data
设置数据](#set-data)
*   [Get data
获取数据](#get-data)
*   [Flush data
冲洗数据](#flush-data)
*   [Flush tags
平装标签](#flush-tags)
*   [Tasks
任务](#tasks)
*   [Queues
队列](#queues)
*   [Dispatcher
调度员](#dispatcher)
*   [Cron
克朗](#cron)
*   [Files
文件](#files)
*   [Static files
静态文件](#static-files)
*   [Cache control headers
缓存控制标头](#cache-control-headers)
*   [Cache-buster
缓存克星](#cache-buster)
*   [Email
电子邮件](#email)
*   [HTTPS](#https)
*   [Logging
记录](#logging)
*   [Roadmap
路线图](#roadmap)
*   [Credits
荣誉](#credits)

Introduction
导言
-----------------

### Overview
概述

_Pagoda_ is not a framework but rather a base starter-kit for rapid, easy full-stack web development in Go, aiming to provide much of the functionality you would expect from a complete web framework as well as establishing patterns, procedures and structure for your web application.
_Pagoda_不是一个框架，而是一个基础入门工具包，用于快速、轻松地使用 Go 进行全栈网络开发，旨在提供您期望从完整网络框架中获得的大部分功能，并为您的网络应用程序建立模式、程序和结构。

Built on a solid [foundation](#foundation) of well-established frameworks and modules, _Pagoda_ aims to be a starting point for any web application with the benefit over a mega-framework in that you have full control over all of the code, the ability to easily swap any frameworks or modules in or out, no strict patterns or interfaces to follow, and no fear of lock-in.
_Pagoda_建立在由成熟框架和模块组成的坚实[基础](#foundation)之上，旨在成为任何网络应用程序的起点，与大型框架相比，它的优势在于您可以完全控制所有代码，能够轻松地将任何框架或模块换入或换出，无需遵循严格的模式或接口，也不必担心被锁定。

While separate JavaScript frontends have surged in popularity, many prefer the reliability, simplicity and speed of a full-stack approach with server-side rendered HTML. Even the popular JS frameworks all have SSR options. This project aims to highlight that _Go_ templates can be powerful and easy to work with, and interesting [frontend](#frontend) libraries can provide the same modern functionality and behavior without having to write any JS at all.
虽然独立的 JavaScript 前端大受欢迎，但许多人更喜欢使用服务器端渲染 HTML 的全栈方法的可靠性、简单性和速度。即使是流行的 JavaScript 框架也都有 SSR 选项。本项目旨在强调 _Go_ 模板功能强大且易于使用，而有趣的 [前端](#frontend)库可以提供相同的现代功能和行为，而无需编写任何 JavaScript。

### Foundation
基金会

While many great projects were used to build this, all of which are listed in the [credits](#credits) section, the following provide the foundation of the back and frontend. It's important to note that you are **not required to use any of these**. Swapping any of them out will be relatively easy.
虽然我们使用了许多优秀的项目来构建本系统，[credits](#credits)部分列出了所有这些项目，但以下项目提供了后台和前台的基础。需要注意的是，**您并不需要使用其中的任何一个**。更换其中任何一个都相对容易。

#### Backend
后台

*   [Echo](https://echo.labstack.com/): High performance, extensible, minimalist Go web framework.
[Echo](https://echo.labstack.com/)：高性能、可扩展、简约的 Go 网络框架。
*   [Ent](https://entgo.io/): Simple, yet powerful ORM for modeling and querying data.
[Ent](https://entgo.io/)：用于数据建模和查询的简单而强大的 ORM。

#### Frontend
前端

Go server-side rendered HTML combined with the projects below enable you to create slick, modern UIs without writing any JavaScript or CSS.
Go 服务器端呈现的 HTML 与下面的项目相结合，让你无需编写任何 JavaScript 或 CSS，就能创建流畅、现代的用户界面。

*   [HTMX](https://htmx.org/): Access AJAX, CSS Transitions, WebSockets and Server Sent Events directly in HTML, using attributes, so you can build modern user interfaces with the simplicity and power of hypertext.
[HTMX](https://htmx.org/)：使用属性直接在 HTML 中访问 AJAX、CSS 过渡、WebSockets 和服务器发送事件，因此您可以利用超文本的简洁性和强大功能构建现代用户界面。
*   [Alpine.js](https://alpinejs.dev/): Rugged, minimal tool for composing behavior directly in your markup. Think of it like jQuery for the modern web. Plop in a script tag and get going.
[Alpine.js](https://alpinejs.dev/)：坚固耐用的极简工具，可直接在标记中合成行为。可以把它想象成现代网络的 jQuery。插入一个脚本标签即可开始工作。
*   [Bulma](https://bulma.io/): Provides ready-to-use frontend components that you can easily combine to build responsive web interfaces. No JavaScript dependencies.
[Bulma](https://bulma.io/)：提供随时可用的前端组件，您可以轻松将其组合起来，构建响应式网页界面。不依赖 JavaScript。

#### Storage
存储

*   [SQLite](https://sqlite.org/): A small, fast, self-contained, high-reliability, full-featured, SQL database engine and the most used database engine in the world.
[SQLite](https://sqlite.org/)：一个小型、快速、独立、高可靠性、全功能的 SQL 数据库引擎，也是世界上使用最多的数据库引擎。

Originally, Postgres and Redis were chosen as defaults but since the aim of this project is rapid, simple development, it was changed to SQLite which now provides the primary data storage as well as persistent, background [task queues](#tasks). For [caching](#cache), a simple in-memory solution is provided. If you need to use something like Postgres or Redis, swapping those in can be done quickly and easily. For reference, [this branch](https://github.com/mikestefanello/pagoda/tree/postgres-redis) contains the code that included those (but is no longer maintained).
最初，Postgres 和 Redis 被选为默认设置，但由于该项目的目标是快速、简单的开发，因此改为 SQLite，它现在提供了主要数据存储以及持久的后台[任务队列](#tasks)。对于[缓存](#cache)，我们提供了一个简单的内存解决方案。如果您需要使用 Postgres 或 Redis，可以快速、轻松地将它们替换进来。作为参考，[此分支](https://github.com/mikestefanello/pagoda/tree/postgres-redis)包含了包含这些内容的代码（但已不再维护）。

### Screenshots
屏幕截图

#### Inline form validation
内联表单验证

![Inline validation](https://user-images.githubusercontent.com/552328/147838632-570a3116-1e74-428f-8bfc-523ed309ef06.png)

#### Switch layout templates, user registration
切换布局模板、用户注册

![Registration](https://user-images.githubusercontent.com/552328/147838633-c1b3e4f6-bbfd-44e1-b0be-884d1a83f8f4.png)

#### Alpine.js modal, HTMX AJAX request
Alpine.js 模态、HTMX AJAX 请求

![Alpine and HTMX](https://user-images.githubusercontent.com/552328/147838634-4b84c5d5-dc3b-4280-ac12-247ab22184a3.png)

Getting started
开始
--------------------

### Dependencies
依赖关系

Ensure that [Go](https://go.dev/) is installed on your system.
确保[Go](https://go.dev/)已安装在系统中。

### Start the application
启动应用程序

After checking out the repository, from within the root, simply run `make run`:
检查完软件源后，只需在根目录下运行 `make run` 即可：

git clone git@github.com:mikestefanello/pagoda.git
cd pagoda
make run


Since this repository is a _template_ and not a Go _library_, you **do not** use `go get`.
由于该版本库是 _模板_，而不是 Go _库_，因此您**不要**使用 `go get`。

By default, you should be able to access the application in your browser at `localhost:8000`. This can be changed via the [configuration](#configuration).
默认情况下，您可以通过 `localhost:8000`在浏览器中访问应用程序。这可以通过 [配置](#configuration)进行更改。

By default, your data will be stored within the `dbs` directory. If you ever want to quickly delete all data just remove this directory.
默认情况下，您的数据将存储在 `dbs` 目录中。如果您想快速删除所有数据，只需删除该目录即可。

### Running tests
运行测试

To run all tests in the application, execute `make test`. This ensures that the tests from each package are not run in parallel. This is required since many packages contain tests that connect to the test database which is stored in memory and reset automatically for each package.
要运行应用程序中的所有测试，请执行 `make test`。这将确保每个软件包中的测试不会并行运行。这是必需的，因为许多软件包包含连接到测试数据库的测试，而测试数据库存储在内存中，并为每个软件包自动重置。

Service container
服务集装箱
-------------------------

The container is located at `pkg/services/container.go` and is meant to house all of your application's services and/or dependencies. It is easily extensible and can be created and initialized in a single call. The services currently included in the container are:
容器位于 `pkg/services/container.go` 中，用于容纳应用程序的所有服务和/或依赖项。它易于扩展，只需一次调用即可创建和初始化。容器中目前包含的服务有

*   Configuration
配置
*   Cache
缓存
*   Database
数据库
*   ORM
*   Web
网络
*   Validator
验证器
*   Authentication
认证
*   Mail
邮件
*   Template renderer
模板呈现器
*   Tasks
任务
*   Files
文件

A new container can be created and initialized via `services.NewContainer()`. It can be later shutdown via `Shutdown()`.
新容器可通过 `services.NewContainer()` 创建和初始化。随后可通过 `Shutdown()` 关闭容器。

### Dependency injection
依赖注入

The container exists to faciliate easy dependency-injection both for services within the container as well as areas of your application that require any of these dependencies. For example, the container is automatically passed to the `Init()` method of your route [handlers](#handlers) so that the handlers have full, easy access to all services.
容器的存在是为了方便容器内的服务以及应用程序中需要这些依赖关系的区域进行依赖关系注入。例如，容器会自动传递给路由[处理程序](#handlers)的`Init()`方法，这样处理程序就可以轻松访问所有服务。

### Test dependencies
测试依赖性

It is common that your tests will require access to dependencies, like the database, or any of the other services available within the container. Keeping all services in a container makes it especially easy to initialize everything within your tests. You can see an example pattern for doing this [here](#environments).
常见的情况是，您的测试需要访问依赖项，如数据库或容器中可用的任何其他服务。将所有服务保存在容器中可以让您特别轻松地在测试中初始化所有内容。您可以在此处[](#environments)查看这样做的示例模式。

Configuration
配置
------------------

The `config` package provides a flexible, extensible way to store all configuration for the application. Configuration is added to the `Container` as a _Service_, making it accessible across most of the application.
`config` 包提供了一种灵活、可扩展的方式来存储应用程序的所有配置。配置将作为 _Service_ 添加到 `Container` 中，从而使应用程序的大部分内容都能访问配置。

Be sure to review and adjust all of the default configuration values provided in `config/config.yaml`.
请务必查看并调整 `config/config.yaml` 中提供的所有默认配置值。

### Environment overrides
环境覆盖

Leveraging the functionality of [viper](https://github.com/spf13/viper) to manage configuration, all configuration values can be overridden by environment variables. The name of the variable is determined by the set prefix and the name of the configuration field in `config/config.yaml`.
利用 [viper](https://github.com/spf13/viper) 管理配置的功能，所有配置值均可由环境变量覆盖。变量名称由 `config/config.yaml` 中的设置前缀和配置字段名称决定。

In `config/config.go`, the prefix is set as `pagoda` via `viper.SetEnvPrefix("pagoda")`. Nested fields require an underscore between levels. For example:
在 `config/config.go` 中，前缀通过 `viper.SetEnvPrefix("pagoda")` 设置为 `pagoda` 。嵌套字段要求在层级之间使用下划线。例如

http:
port: 1234


can be overridden by setting an environment variable with the name `PAGODA_HTTP_PORT`.
可以通过设置名称为 `PAGODA_HTTP_PORT` 的环境变量来重写。

### Environments
环境

The configuration value for the current _environment_ (`Config.App.Environment`) is an important one as it can influence some behavior significantly (will be explained in later sections).
当前_环境_（`Config.App.Environment`）的配置值非常重要，因为它会对某些行为产生重大影响（将在后面的章节中解释）。

A helper function (`config.SwitchEnvironment`) is available to make switching the environment easy, but this must be executed prior to loading the configuration. The common use-case for this is to switch the environment to `Test` before tests are executed:
有一个辅助函数（`config.SwitchEnvironment`）可以帮助用户轻松切换环境，但必须在加载配置之前执行。常见的使用情况是在执行测试之前将环境切换为 `Test` ：

func TestMain(m *testing.M) {
// Set the environment to test
config.SwitchEnvironment(config.EnvTest)

// Start a new container
c = services.NewContainer()

// Run tests
exitVal := m.Run()

// Shutdown the container
if err := c.Shutdown(); err != nil {
panic(err)
}

os.Exit(exitVal)
}


Database
数据库
--------------

The database currently used is [SQLite](https://sqlite.org/) but you are free to use whatever you prefer. If you plan to continue using [Ent](https://entgo.io/), the incredible ORM, you can check their supported databases [here](https://entgo.io/docs/dialects). The database driver is provided by [go-sqlite3](https://github.com/mattn/go-sqlite3). A reference to the database is included in the `Container` if direct access is required.
目前使用的数据库是 [SQLite](https://sqlite.org/)，但您可以自由使用任何您喜欢的数据库。如果你打算继续使用 [Ent](https://entgo.io/)（令人难以置信的 ORM），可以在 [这里](https://entgo.io/docs/dialects)查看他们支持的数据库。[go-sqlite3](https://github.com/mattn/go-sqlite3)提供了数据库驱动程序。如果需要直接访问，`容器`中会包含对数据库的引用。

Database configuration can be found and managed within the `config` package.
数据库配置可在 `config` 软件包中找到并管理。

### Auto-migrations
自动迁移

[Ent](https://entgo.io/) provides automatic migrations which are executed on the database whenever the `Container` is created, which means they will run when the application starts.
[Ent](https://entgo.io/) 提供了自动迁移功能，每当创建 `Container` 时都会在数据库中执行迁移，这意味着它们将在应用程序启动时运行。

### Separate test database
独立的测试数据库

Since many tests can require a database, this application supports a separate database specifically for tests. Within the `config`, the test database can be specified at `Config.Database.TestConnection`, which is the database connection string that will be used. By default, this will be an in-memory SQLite database.
由于许多测试都需要数据库，因此本应用程序支持专门用于测试的独立数据库。在 `config` 中，可在 `Config.Database.TestConnection` 处指定测试数据库，这也是将使用的数据库连接字符串。默认情况下，这将是一个内存 SQLite 数据库。

When a `Container` is created, if the [environment](#environments) is set to `config.EnvTest`, the database client will connect to the test database instead and run migrations so your tests start with a clean, ready-to-go database.
创建 `Container` 时，如果 [environment](#environments) 设置为 `config.EnvTest`，数据库客户端将连接到测试数据库并运行迁移，这样您的测试将从一个干净的、随时可用的数据库开始。

When this project was using Postgres, it would automatically drop and recreate the test database. Since the current default is in-memory, that is no longer needed. If you decide to use a test database not in-memory, you can alter the `Container` initialization code to do this for you.
当该项目使用 Postgres 时，它会自动删除并重新创建测试数据库。由于当前的默认值是内存，因此不再需要这样做。如果您决定使用非内存的测试数据库，可以更改 `Container` 初始化代码来代劳。

ORM
---

As previously mentioned, [Ent](https://entgo.io/) is the supplied ORM. It can swapped out, but I highly recommend it. I don't think there is anything comparable for Go, at the current time. If you're not familiar with Ent, take a look through their top-notch [documentation](https://entgo.io/docs/getting-started).
如前所述，[Ent](https://entgo.io/) 是提供的 ORM。它可以被替换掉，但我强烈推荐使用它。我认为目前还没有任何可与 Go 相媲美的产品。如果您对 Ent 不熟悉，请查看他们一流的 [文档](https://entgo.io/docs/getting-started)。

An Ent client is included in the `Container` to provide easy access to the ORM throughout the application.
`容器`中包含一个 Ent 客户端，以便在整个应用程序中轻松访问 ORM。

Ent relies on code-generation for the entities you create to provide robust, type-safe data operations. Everything within the `ent` package in this repository is generated code for the two entity types listed below with the exception of the schema declaration.
Ent 依靠为你创建的实体生成代码来提供强大、类型安全的数据操作。除模式声明外，该资源库中 `ent` 包内的所有内容都是为下面列出的两种实体类型生成的代码。

### Entity types
实体类型

The two included entity types are:
包括的两种实体类型是

*   User
用户
*   PasswordToken
密码令牌

### New entity type
新实体类型

While you should refer to their [documentation](https://entgo.io/docs/getting-started) for detailed usage, it's helpful to understand how to create an entity type and generate code. To make this easier, the `Makefile` contains some helpers.
详细用法请参阅[文档](https://entgo.io/docs/getting-started)，但了解如何创建实体类型和生成代码会很有帮助。为了简化这一过程，`Makefile`包含了一些帮助文件。

1. Ensure all Ent code is downloaded by executing `make ent-install`.
执行 `make ent-install` 以确保下载了所有 Ent 代码。
2. Create the new entity type by executing `make ent-new name=User` where `User` is the name of the entity type. This will generate a file like you can see in `ent/schema/user.go` though the `Fields()` and `Edges()` will be left empty.
执行 `make ent-new name=User` 创建新实体类型，其中 `User` 是实体类型的名称。这将生成一个类似于 `ent/schema/user.go` 中的文件，但 `Fields()` 和 `Edges()` 将留空。
3. Populate the `Fields()` and optionally the `Edges()` (which are the relationships to other entity types).
填充 `Fields()` 和可选的 `Edges()` （这是与其他实体类型的关系）。
4. When done, generate all code by executing `make ent-gen`.
完成后，执行 `make ent-gen` 生成所有代码。

The generated code is extremely flexible and impressive. An example to highlight this is one used within this application:
生成的代码非常灵活，令人印象深刻。本应用程序中使用的一个示例就很好地说明了这一点：

entity, err := c.ORM.PasswordToken.
Query().
Where(passwordtoken.ID(tokenID)).
Where(passwordtoken.HasUserWith(user.ID(userID))).
Where(passwordtoken.CreatedAtGTE(expiration)).
Only(ctx.Request().Context())


This executes a database query to return the _password token_ entity with a given ID that belong to a user with a given ID and has a _created at_ timestamp field that is greater than or equal to a given time.
执行数据库查询，返回具有给定 ID 的 _密码令牌_实体，该实体属于具有给定 ID 的用户，且 _创建于_时间戳字段大于或等于给定时间。

Sessions
会议
-------------

Sessions are provided and handled via [Gorilla sessions](https://github.com/gorilla/sessions) and configured as middleware in the router located at `pkg/handlers/router.go`. Session data is currently stored in cookies but there are many [options](https://github.com/gorilla/sessions#store-implementations) available if you wish to use something else.
会话通过 [Gorilla 会话](https://github.com/gorilla/sessions)提供和处理，并在位于 `pkg/handlers/router.go` 的路由器中配置为中间件。会话数据目前存储在 cookie 中，但如果您想使用其他方式，也有很多 [选项](https://github.com/gorilla/sessions#store-implementations)可用。

Here's a simple example of loading data from a session and saving new values:
下面是一个从会话中加载数据并保存新值的简单示例：

func SomeFunction(ctx echo.Context) error {
sess, err := session.Get(ctx, "some-session-key")
if err != nil {
return err
}
sess.Values["hello"] = "world"
sess.Values["isSomething"] = true
return sess.Save(ctx.Request(), ctx.Response())
}


### Encryption
加密

Session data is encrypted for security purposes. The encryption key is stored in [configuration](#configuration) at `Config.App.EncryptionKey`. While the default is fine for local development, it is **imperative** that you change this value for any live environment otherwise session data can be compromised.
为安全起见，会话数据将被加密。加密密钥存储在 [configuration](#configuration) 中的 `Config.App.EncryptionKey` 中。虽然默认值适用于本地开发，但**对于任何实时环境，您都必须更改此值，否则会话数据可能会被泄露。**

Authentication
认证
-------------------

Included are standard authentication features you expect in any web application. Authentication functionality is bundled as a _Service_ within `services/AuthClient` and added to the `Container`. If you wish to handle authentication in a different manner, you could swap this client out or modify it as needed.
其中包括您期望在任何网络应用程序中使用的标准身份验证功能。身份验证功能作为 _Service_ 捆绑在 `services/AuthClient` 中，并添加到 `Container` 中。如果您希望以不同的方式处理身份验证，您可以根据需要更换或修改该客户端。

Authentication currently requires [sessions](#sessions) and the session middleware.
身份验证目前需要 [会话](#sessions) 和会话中间件。

### Login / Logout
登录/注销

The `AuthClient` has methods `Login()` and `Logout()` to log a user in or out. To track a user's authentication state, data is stored in the session including the user ID and authentication status.
`AuthClient` 拥有 `Login()` 和 `Logout()` 方法，用于登录或注销用户。为跟踪用户的身份验证状态，会话中会存储包括用户 ID 和身份验证状态在内的数据。

Prior to logging a user in, the method `CheckPassword()` can be used to determine if a user's password matches the hash stored in the database and on the `User` entity.
在登录用户之前，可使用方法 `CheckPassword()`来确定用户密码是否与存储在数据库和 `User` 实体中的哈希值相匹配。

Routes are provided for the user to login and logout at `user/login` and `user/logout`.
在 `user/login` 和 `user/logout` 中为用户提供了登录和注销路径。

### Forgot password
忘记密码

Users can reset their password in a secure manner by issuing a new password token via the method `GeneratePasswordResetToken()`. This creates a new `PasswordToken` entity in the database belonging to the user. The actual token itself, however, is not stored in the database for security purposes. It is only returned via the method so it can be used to build the reset URL for the email. Rather, a hash of the token is stored, using `bcrypt` the same package used to hash user passwords. The reason for doing this is the same as passwords. You do not want to store a plain-text value in the database that can be used to access an account.
用户可以通过方法 `GeneratePasswordResetToken()` 生成一个新的密码令牌，从而以安全的方式重置密码。这会在数据库中创建一个属于用户的新 `PasswordToken` 实体。但是，出于安全考虑，实际令牌本身不会存储在数据库中。它只会通过该方法返回，以便用于创建电子邮件的重置 URL。相反，我们使用 `bcrypt` 来存储令牌的哈希值，该软件包也用于对用户密码进行哈希处理。这样做的原因与密码相同。我们不想在数据库中存储可用于访问账户的纯文本值。

Tokens have a configurable expiration. By default, they expire within 1 hour. This can be controlled in the `config` package. The expiration of the token is not stored in the database, but rather is used only when tokens are loaded for potential usage. This allows you to change the expiration duration and affect existing tokens.
令牌有可配置的过期时间。默认情况下，它们会在 1 小时内过期。这可以在 `config` 包中进行控制。令牌的过期时间不会存储在数据库中，而只会在加载令牌以供使用时使用。这样，您就可以更改过期时间并影响现有令牌。

Since the actual tokens are not stored in the database, the reset URL must contain the user and password token ID. Using that, `GetValidPasswordToken()` will load a matching, non-expired _password token_ entity belonging to the user, and use `bcrypt` to determine if the token in the URL matches stored hash of the password token entity.
由于数据库中不存储实际令牌，因此重置 URL 必须包含用户和密码令牌 ID。使用该 ID，`GetValidPasswordToken()` 将加载属于用户的匹配、未过期的 _密码令牌_实体，并使用 `bcrypt` 来确定 URL 中的令牌是否与密码令牌实体的已存储哈希值相匹配。

Once a user claims a valid password token, all tokens for that user should be deleted using `DeletePasswordTokens()`.
用户申请有效密码令牌后，应使用 `DeletePasswordTokens()` 删除该用户的所有令牌。

Routes are provided to request a password reset email at `user/password` and to reset your password at `user/password/reset/token/:user/:password_token/:token`.
提供了通过 `user/password` 申请密码重置电子邮件和通过 `user/password/reset/token/:user/:password_token/:token` 重置密码的路径。

### Registration
注册

The actual registration of a user is not handled within the `AuthClient` but rather just by creating a `User` entity. When creating a user, use `HashPassword()` to create a hash of the user's password, which is what will be stored in the database.
用户的实际注册并不在 `AuthClient` 中处理，而是通过创建 `User` 实体来完成。创建用户时，使用 `HashPassword()` 创建用户密码的哈希值，该值将存储在数据库中。

A route is provided for the user to register at `user/register`.
在 `user/register` 中为用户提供了注册路径。

### Authenticated user
认证用户

The `AuthClient` has two methods available to get either the `User` entity or the ID of the user currently logged in for a given request. Those methods are `GetAuthenticatedUser()` and `GetAuthenticatedUserID()`.
`AuthClient` 有两个方法可用来获取 `User` 实体或给定请求的当前登录用户 ID。这两个方法是 `GetAuthenticatedUser()` 和 `GetAuthenticatedUserID()` 。

#### Middleware
中间件

Registered for all routes is middleware that will load the currently logged in user entity and store it within the request context. The middleware is located at `middleware.LoadAuthenticatedUser()` and, if authenticated, the `User` entity is stored within the context using the key `context.AuthenticatedUserKey`.
为所有路由注册的中间件将加载当前登录的用户实体，并将其存储在请求上下文中。中间件位于 `middleware.LoadAuthenticatedUser()` ，如果通过验证，`User` 实体将使用 `context.AuthenticatedUserKey` 密钥存储在上下文中。

If you wish to require either authentication or non-authentication for a given route, you can use either `middleware.RequireAuthentication()` or `middleware.RequireNoAuthentication()`.
如果希望对指定路由要求身份验证或非身份验证，可以使用 `middleware.RequireAuthentication()` 或 `middleware.RequireNoAuthentication()` 。

### Email verification
电子邮件验证

Most web applications require the user to verify their email address (or other form of contact information). The `User` entity has a field `Verified` to indicate if they have verified themself. When a user successfully registers, an email is sent to them containing a link with a token that will verify their account when visited. This route is currently accessible at `/email/verify/:token` and handled by `pkg/handlers/auth.go`.
大多数网络应用程序都要求用户验证其电子邮件地址（或其他形式的联系信息）。`User` 实体有一个字段 `Verified` 用于指示用户是否已验证自己。用户注册成功后，系统会向其发送一封电子邮件，其中包含一个链接和一个令牌，访问该链接时将验证其账户。目前可通过 `/email/verify/:token` 访问此路由，并由 `pkg/handlers/auth.go` 处理。

There is currently no enforcement that a `User` must be verified in order to access the application. If that is something you desire, it will have to be added in yourself. It was not included because you may want partial access of certain features until the user verifies; or no access at all.
目前没有强制规定必须验证 `User` 才能访问应用程序。如果您希望这样做，则必须自行添加。之所以没有加入，是因为您可能希望在用户验证之前部分访问某些功能，或者完全不访问。

Verification tokens are [JSON Web Tokens](https://jwt.io/) generated and processed by the [jwt](https://github.com/golang-jwt/jwt) module. The tokens are _signed_ using the encryption key stored in [configuration](#configuration) (`Config.App.EncryptionKey`). **It is imperative** that you override this value from the default in any live environments otherwise the data can be comprimised. JWT was chosen because they are secure tokens that do not have to be stored in the database, since the tokens contain all of the data required, including built-in expirations. These were not chosen for password reset tokens because JWT cannot be withdrawn once they are issued which poses a security risk. Since these tokens do not grant access to an account, the ability to withdraw the tokens is not needed.
验证令牌是由 [jwt](https://github.com/golang-jwt/jwt) 模块生成和处理的 [JSON Web 令牌](https://jwt.io/)。令牌使用存储在 [configuration](#configuration) 中的加密密钥_签名_（`Config.App.EncryptionKey`）。**在任何实时环境中，您都必须**覆盖默认值，否则数据将受到损害。之所以选择 JWT，是因为它们是无需存储在数据库中的安全令牌，因为令牌包含了所需的所有数据，包括内置的过期时间。密码重置令牌没有选择 JWT，因为 JWT 一旦发布就不能撤回，这会带来安全风险。由于这些令牌不授予对账户的访问权限，因此不需要提取令牌的功能。

By default, verification tokens expire 12 hours after they are issued. This can be changed in configuration at `Config.App.EmailVerificationTokenExpiration`. There is currently not a route or form provided to request a new link.
默认情况下，验证令牌会在发出 12 小时后过期。可在 `Config.App.EmailVerificationTokenExpiration` 配置中进行更改。目前没有提供申请新链接的途径或表格。

Be sure to review the [email](#email) section since actual email sending is not fully implemented.
请务必查看 [email](#email) 部分，因为实际的电子邮件发送尚未完全实现。

To generate a new verification token, the `AuthClient` has a method `GenerateEmailVerificationToken()` which creates a token for a given email address. To verify the token, pass it in to `ValidateEmailVerificationToken()` which will return the email address associated with the token and an error if the token is invalid.
要生成新的验证令牌，`AuthClient`有一个方法 `GenerateEmailVerificationToken()` ，可为给定的电子邮件地址创建令牌。要验证令牌，可将其传入 `ValidateEmailVerificationToken()` ，该方法将返回与令牌相关联的电子邮件地址，如果令牌无效，则将返回错误信息。

Routes
道路
-----------

The router functionality is provided by [Echo](https://echo.labstack.com/guide/routing/) and constructed within via the `BuildRouter()` function inside `pkg/handlers/router.go`. Since the _Echo_ instance is a _Service_ on the `Container` which is passed in to `BuildRouter()`, middleware and routes can be added directly to it.
路由器功能由 [Echo](https://echo.labstack.com/guide/routing/) 提供，并通过 `pkg/handlers/router.go` 中的 `BuildRouter()` 函数构建。由于 _Echo_ 实例是传入 `Container` 的 _Service_ 上的一个 _服务_，因此中间件和路由可以直接添加到其中。

### Custom middleware
定制中间件

By default, a middleware stack is included in the router that makes sense for most web applications. Be sure to review what has been included and what else is available within _Echo_ and the other projects mentioned.
默认情况下，路由器中包含了一个中间件栈，这对大多数网络应用程序来说都是合理的。请务必查看_Echo_和提及的其他项目中包含的内容和其他可用内容。

A `middleware` package is included which you can easily add to along with the custom middleware provided.
其中包含一个`中间件`包，您可以轻松地将其添加到所提供的自定义中间件中。

### Handlers
处理程序

A `Handler` is a simple type that handles one or more of your routes and allows you to group related routes together (ie, authentication). All provided handlers are located in `pkg/handlers`. _Handlers_ also handle self-registering their routes with the router.
`Handler` 是一种简单的类型，用于处理一个或多个路由，并允许您将相关路由分组（即身份验证）。所有提供的处理程序都位于 `pkg/handlers` 中。_处理程序_还负责向路由器自注册路由。

#### Example
示例

The provided patterns are not required, but were designed to make development as easy as possible.
所提供的模式不是必需的，但其目的是尽可能简化开发过程。

For this example, we'll create a new handler which includes a GET and POST route and uses the ORM. Start by creating a file at `pkg/handlers/example.go`.
在本示例中，我们将创建一个包含 GET 和 POST 路由并使用 ORM 的新处理程序。首先在 `pkg/handlers/example.go` 下创建一个文件。

1. Define the handler type:
定义处理程序类型：

type Example struct {
orm *ent.Client
*services.TemplateRenderer
}


1. Register the handler so the router automatically includes it
注册处理程序，以便路由器自动将其包含在内

func init() {
Register(new(Example))
}


1. Initialize the handler (and inject any required dependencies from the _Container_). This will be called automatically.
初始化处理程序（并从 _Container_ 中注入任何所需的依赖项）。这将被自动调用。

func (e *Example) Init(c *services.Container) error {
e.TemplateRenderer = c.TemplateRenderer
e.orm = c.ORM
return nil
}


1. Declare the routes
宣布路线

**It is highly recommended** that you provide a `Name` for your routes. Most methods on the back and frontend leverage the route name and parameters in order to generate URLs.
**强烈建议**您为路由提供`名称`。后台和前台的大多数方法都会利用路由名称和参数来生成 URL。

func (e *Example) Routes(g *echo.Group) {
g.GET("/example", e.Page).Name = "example"
g.POST("/example", c.PageSubmit).Name = "example.submit"
}


1. Implement your routes
执行路线

func (e *Example) Page(ctx echo.Context) error {
// add your code here
}

func (e *Example) PageSubmit(ctx echo.Context) error {
// add your code here
}


### Errors
错误

Routes can return errors to indicate that something wrong happened. Ideally, the error is of type `*echo.HTTPError` to indicate the intended HTTP response code. You can use `return echo.NewHTTPError(http.StatusInternalServerError)`, for example. If an error of a different type is returned, an _Internal Server Error_ is assumed.
路由可以返回错误，以表明发生了错误。理想情况下，错误类型为 `*echo.HTTPError` 以指示预期的 HTTP 响应代码。例如，可以使用 `return echo.NewHTTPError(http.StatusInternalServerError)` 。如果返回不同类型的错误，则假定为_内部服务器错误_。

The [error handler](https://echo.labstack.com/guide/error-handling/) is set to the provided `Handler` in `pkg/handlers/error.go` in the `BuildRouter()` function. That means that if any middleware or route return an error, the request gets routed there. This route conveniently constructs and renders a `Page` which uses the template `templates/pages/error.gohtml`. The status code is passed to the template so you can easily alter the markup depending on the error type.
在 `pkg/handlers/error.go` 的 `BuildRouter()` 函数中，[错误处理器](https://echo.labstack.com/guide/error-handling/)被设置为 `Handler` 中提供的 。这意味着，如果任何中间件或路由返回错误，请求就会被路由到那里。该路由会方便地构建并渲染一个使用模板 `templates/pages/error.gohtml` 的 `Page` 。状态代码会传递给模板，因此您可以根据错误类型轻松更改标记。

### Redirects
重定向

The `pkg/redirect` package makes it easy to perform redirects, especially if you provide names for your routes. The `Redirect` type provides the ability to chain redirect options and also supports automatically handling HTMX redirects for boosted requests.
`pkg/redirect` 软件包可让您轻松执行重定向，尤其是在您为路由提供名称的情况下。`Redirect` 类型提供了链式重定向选项的功能，还支持自动处理 HTMX 重定向的增强请求。

For example, if your route name is `user_profile` with a URL pattern of `/user/profile/:id`, you can perform a redirect by doing:
例如，如果路由名称为 `user_profile`，URL 模式为 `/user/profile/:id` ，则可以通过以下操作执行重定向：

return redirect.New(ctx).
Route("user_profile").
Params(userID).
Query(queryParams).
Go()


### Testing
测试

Since most of your web application logic will live in your routes, being able to easily test them is important. The following aims to help facilitate that.
由于网络应用程序的大部分逻辑都将存在于路由中，因此能够轻松地对它们进行测试非常重要。以下内容就是为了帮助实现这一目标。

The test setup and helpers reside in `pkg/handlers/router_test.go`.
测试设置和帮助程序位于 `pkg/handlers/router_test.go` 中。

Only a brief example of route tests were provided in order to highlight what is available. Adding full tests did not seem logical since these routes will most likely be changed or removed in your project.
我们只提供了一个路由测试的简短示例，以强调可用的路由。添加完整的测试似乎不合逻辑，因为这些路由很可能会在项目中更改或删除。

#### HTTP server
HTTP 服务器

When the route tests initialize, a new `Container` is created which provides full access to all of the _Services_ that will be available during normal application execution. Also provided is a test HTTP server with the router added. This means your tests can make requests and expect responses exactly as the application would behave outside of tests. You do not need to mock the requests and responses.
路由测试初始化时，会创建一个新的 `容器`，该容器可提供对所有 _服务_的完全访问，这些服务在正常应用程序执行期间可用。此外，还提供了一个添加了路由器的测试 HTTP 服务器。这意味着您的测试可以发出请求，并期望得到与应用程序在测试之外的行为完全相同的响应。您无需模拟请求和响应。

#### Request / Response helpers
请求/响应助手

With the test HTTP server setup, test helpers for making HTTP requests and evaluating responses are made available to reduce the amount of code you need to write. See `httpRequest` and `httpResponse` within `pkg/handlers/router_test.go`.
设置了测试 HTTP 服务器后，就可以使用测试助手来发出 HTTP 请求和评估响应，从而减少需要编写的代码量。请参阅 `httpRequest` 和 `httpResponse` 中的 `pkg/handlers/router_test.go` 。

Here is an example how to easily make a request and evaluate the response:
下面是一个如何轻松发出请求并评估响应的示例：

func TestAbout_Get(t *testing.T) {
doc := request(t).
setRoute("about").
get().
assertStatusCode(http.StatusOK).
toDoc()
}


#### Goquery
查询

A helpful, included package to test HTML markup from HTTP responses is [goquery](https://github.com/PuerkitoBio/goquery). This allows you to use jQuery-style selectors to parse and extract HTML values, attributes, and so on.
[goquery](https://github.com/PuerkitoBio/goquery)是从 HTTP 响应中测试 HTML 标记的一个有用的附带软件包。它允许你使用 jQuery 风格的选择器来解析和提取 HTML 值、属性等。

In the example above, `toDoc()` will return a `*goquery.Document` created from the HTML response of the test HTTP server.
在上面的示例中，`toDoc()` 将返回一个从测试 HTTP 服务器的 HTML 响应创建的 `*goquery.Document` 文件。

Here is a simple example of how to use it, along with [testify](https://github.com/stretchr/testify) for making assertions:
下面是一个简单的示例，说明如何使用它以及 [testify](https://github.com/stretchr/testify) 进行断言：

h1 := doc.Find("h1.title")
assert.Len(t, h1.Nodes, 1)
assert.Equal(t, "About", h1.Text())


Pages
页面
----------

The `Page` is the major building block of your `Handler` responses. It is a _struct_ type located at `pkg/page/page.go`. The concept of the `Page` is that it provides a consistent structure for building responses and transmitting data and functionality to the templates. Pages are rendered with the `TemplateRenderer`.
`Page` 是 `Handler` 响应的主要构件。它是一个 _struct_ 类型，位于 `pkg/page/page.go` 中。`Page` 的概念是，它为构建响应以及向模板传输数据和功能提供了一致的结构。页面通过 `TemplateRenderer` 渲染。

All example routes provided construct and _render_ a `Page`. It's recommended that you review both the `Page` and the example routes as they try to illustrate all included functionality.
所提供的所有示例路由都会构建并_渲染_一个`页面`。建议您同时查看 `Page` 和示例路由，因为它们试图说明所有包含的功能。

As you develop your application, the `Page` can be easily extended to include whatever data or functions you want to provide to your templates.
在您开发应用程序的过程中，`页面`可以很容易地进行扩展，以包含您想为模板提供的任何数据或功能。

Initializing a new page is simple:
初始化新页面非常简单：

func (c *home) Get(ctx echo.Context) error {
p := page.New(ctx)
}


Using the `echo.Context`, the `Page` will be initialized with the following fields populated:
使用 `echo.Context` 将初始化 `Page` 并填充以下字段：

*   `Context`: The passed in _context_
`上下文`：传入的 _上下文_
*   `Path`: The requested URL path
`路径`：请求的 URL 路径
*   `URL`: The requested URL
`URL`：请求的 URL
*   `StatusCode`: Defaults to 200
`状态代码`：默认为 200
*   `Pager`: Initialized `Pager` (see below)
`Pager`: 已初始化 `Pager` (见下文)
*   `RequestID`: The request ID, if the middleware is being used
`RequestID`：如果使用中间件，则为请求 ID
*   `IsHome`: If the request was for the homepage
`IsHome`：如果请求是针对主页的
*   `IsAuth`: If the user is authenticated
`IsAuth`： 如果用户已通过身份验证
*   `AuthUser`: The logged in user entity, if one
`AuthUser`：登录的用户实体（如果有的话
*   `CSRF`: The CSRF token, if the middleware is being used
`CSRF`：如果使用中间件，则为 CSRF 标记
*   `HTMX.Request`: Data from the HTMX headers, if HTMX made the request (see below)
`HTMX.Request`：来自 HTMX 头信息的数据，如果 HTMX 提出了请求（见下文）

### Flash messaging
Flash 消息传送

Flash messaging functionality is provided within the `msg` package. It is used to provide one-time status messages to users.
Flash 消息功能由 `msg` 包提供。它用于向用户提供一次性状态信息。

Flash messaging requires that [sessions](#sessions) and the session middleware are in place since that is where the messages are stored.
Flash 消息传递要求[会话](#sessions)和会话中间件就位，因为这是存储消息的地方。

#### Creating messages
创建信息

There are four types of messages, and each can be created as follows:
有四种类型的信息，每种信息的创建方法如下：

*   Success: `msg.Success(ctx echo.Context, message string)`
成功： `msg.Success(ctx echo.Context, message string)`
*   Info: `msg.Info(ctx echo.Context, message string)`
信息： `msg.Info(ctx echo.Context, message string)`
*   Warning: `msg.Warning(ctx echo.Context, message string)`
警告： `msg.Warning(ctx echo.Context, message string)`
*   Danger: `msg.Danger(ctx echo.Context, message string)`
危险： `msg.Danger(ctx echo.Context, message string)`

The _message_ string can contain HTML.
_message_ 字符串可包含 HTML。

#### Rendering messages
渲染信息

When a flash message is retrieved from storage in order to be rendered, it is deleted from storage so that it cannot be rendered again.
当从存储中提取闪存信息以便渲染时，会将其从存储中删除，使其无法再次渲染。

The `Page` has a method that can be used to fetch messages for a given type from within the template: `Page.GetMessages(typ msg.Type)`. This is used rather than the _funcmap_ because the `Page` contains the request context which is required in order to access the session data. Since the `Page` is the data destined for the templates, you can use: `{{.GetMessages "success"}}` for example.
`Page` 有一个方法可用于从模板中获取给定类型的信息： `Page.GetMessages(typ msg.Type)` .之所以使用该方法而不是 _funcmap_ 是因为 `Page` 包含访问会话数据所需的请求上下文。由于 `Page` 是用于模板的数据，因此您可以使用：`{{.GetMessages "success"}}` 举例说明。

To make things easier, a template _component_ is already provided, located at `templates/components/messages.gohtml`. This will render all messages of all types simply by using `{{template "messages" .}}` either within your page or layout template.
为了方便起见，我们已经提供了一个模板 _组件_，位于 `templates/components/messages.gohtml` 。只需在页面或布局模板中使用 `{{template "messages" .}}` 即可呈现所有类型的所有消息。

### Pager
呼叫器

A very basic mechanism is provided to handle and facilitate paging located in `pkg/page/pager.go`. When a `Page` is initialized, so is a `Pager` at `Page.Pager`. If the requested URL contains a `page` query parameter with a numeric value, that will be set as the page number in the pager.
`pkg/page/pager.go`中提供了一个非常基本的机制来处理和促进分页。当一个 `Page` 被初始化时，在 `Page.Pager` 中的 `Pager` 也会被初始化。如果请求的 URL 包含一个数值为`page`的查询参数，该查询参数将被设置为页码。

During initialization, the _items per page_ amount will be set to the default, controlled via constant, which has a value of 20. It can be overridden by changing `Pager.ItemsPerPage` but should be done before other values are set in order to not provide incorrect calculations.
在初始化过程中，_每页条目数_将被设置为默认值，通过常量控制，其值为 20。可以通过更改 `Pager.ItemsPerPage` 来覆盖该值，但应在设置其他值之前更改，以免提供不正确的计算结果。

Methods include:
方法包括

*   `SetItems(items int)`: Set the total amount of items in the entire result-set
`SetItems(items int)`: 设置整个结果集中的项目总数
*   `IsBeginning()`: Determine if the pager is at the beginning of the pages
`IsBeginning()`：确定页面是否处于开始位置
*   `IsEnd()`: Determine if the pager is at the end of the pages
`IsEnd()`：确定页面是否处于结束状态
*   `GetOffset()`: Get the offset which can be useful is constructing a paged database query
`GetOffset()`：获取偏移量，这在构建分页数据库查询时非常有用

There is currently no template (yet) to easily render a pager.
目前还没有模板（尚未有）可以轻松呈现一个分页器。

### CSRF

By default, all non GET requests will require a CSRF token be provided as a form value. This is provided by middleware and can be adjusted or removed in the router.
默认情况下，所有非 GET 请求都要求提供 CSRF 标记作为表单值。这是由中间件提供的，可以在路由器中调整或删除。

The `Page` will contain the CSRF token for the given request. There is a CSRF helper component template which can be used to easily render a hidden form element in your form which will contain the CSRF token and the proper element name. Simply include `{{template "csrf" .}}` within your form.
`Page` 将包含给定请求的 CSRF 标记。有一个 CSRF 辅助组件模板，可用于在表单中轻松呈现一个隐藏表单元素，其中将包含 CSRF 标记和适当的元素名称。只需在表单中包含 `{{template "csrf" .}}` 即可。

### Automatic template parsing
自动模板解析

Dealing with templates can be quite tedious and annoying so the `Page` aims to make it as simple as possible with the help of the [template renderer](#template-renderer). To start, templates for _pages_ are grouped in the following directories within the `templates` directory:
处理模板可能相当繁琐和恼人，因此 `Page` 希望借助 [template renderer](#template-renderer) 使处理模板变得尽可能简单。首先，_页面_的模板被归类到 `templates` 目录下的以下目录中：

*   `layouts`: Base templates that provide the entire HTML wrapper/layout. This template should include a call to `{{template "content" .}}` to render the content of the `Page`.
`布局`：提供整个 HTML 封装/布局的基础模板。此模板应包含对 `{{template "content" .}}` 的调用，以呈现 `Page` 的内容。
*   `pages`: Templates that are specific for a given route/page. These must contain `{{define "content"}}{{end}}` which will be injected in to the _layout_ template.
`页面`：特定路由/页面的模板。这些模板必须包含`{{define "content"}}{{end}}`，它们将被注入到 _layout_ 模板中。
*   `components`: A shared library of common components that the layout and base template can leverage.
`组件`：布局和基础模板可利用的通用组件共享库。

Specifying which templates to render for a given `Page` is as easy as:
为给定的 `Page` 指定要呈现的模板非常简单：

page.Name = "home"
page.Layout = "main"


That alone will result in the following templates being parsed and executed when the `Page` is rendered:
仅这一点就会导致在呈现 `Page` 时解析并执行以下模板：

1. `layouts/main.gohtml` as the base template
将 `layouts/main.gohtml` 作为基本模板
2. `pages/home.gohtml` to provide the `content` template for the layout
`pages/home.gohtml` 为布局提供 `content` 模板
3. All template files located within the `components` directory
位于 `components` 目录中的所有模板文件
4. The entire [funcmap](#funcmap)
整个[功能映射](#funcmap)

The [template renderer](#template-renderer) also provides caching and local hot-reloading.
[模板呈现器](#template-renderer)还提供缓存和本地热加载功能。

### Cached responses
缓存响应

A `Page` can have cached enabled just by setting `Page.Cache.Enabled` to `true`. The `TemplateRenderer` will automatically handle caching the HTML output, headers and status code. Cached pages are stored using a key that matches the full request URL and [middleware](#cache-middleware) is used to serve it on matching requests.
只需将 `Page.Cache.Enabled` 设置为 `true` 即可启用 `Page` 的缓存功能。`TemplateRenderer` 将自动处理 HTML 输出、标题和状态代码的缓存。缓存页面使用与完整请求 URL 匹配的键进行存储，[中间件](#cache-middleware)用于在匹配请求时提供缓存。

By default, the cache expiration time will be set according to the configuration value located at `Config.Cache.Expiration.Page` but it can be set per-page at `Page.Cache.Expiration`.
默认情况下，缓存过期时间将根据 `Config.Cache.Expiration.Page` 中的配置值设置，但也可在 `Page.Cache.Expiration` 中按页面设置。

#### Cache tags
缓存标签

You can optionally specify cache tags for the `Page` by setting a slice of strings on `Page.Cache.Tags`. This provides the ability to build in cache invalidation logic in your application driven by events such as entity operations, for example.
通过在 `Page.Cache.Tags` 上设置字符串片段，您可以选择性地为 `Page` 指定缓存标记。这样，您就可以在实体操作等事件驱动的应用程序中建立缓存失效逻辑。

You can use the [cache client](#cache) on the `Container` to easily [flush cache tags](#flush-tags), if needed.
如果需要，您可以在 `Container` 上使用 [缓存客户端](#cache)，以轻松 [冲洗缓存标记](#flush-tags)。

#### Cache middleware
缓存中间件

Cached pages are served via the middleware `ServeCachedPage()` in the `middleware` package.
缓存页面通过 `middleware` 包中的中间件 `ServeCachedPage()` 提供。

The cache is bypassed if the requests meet any of the following criteria:
如果请求符合以下任一条件，则绕过缓存：

1. Is not a GET request
不是 GET 请求
2. Is made by an authenticated user
由通过身份验证的用户创建

Cached pages are looked up for a key that matches the exact, full URL of the given request.
缓存页面会查找与给定请求的完整 URL 完全匹配的关键字。

### Data
数据

The `Data` field on the `Page` is of type `any` and is what allows your route to pass whatever it requires to the templates, alongside the `Page` itself.
`Page` 上的 `Data` 字段类型为 `任意`，它允许路由将其所需的任何内容传递给模板，以及 `Page` 本身。

### Forms
表格

The `Form` field on the `Page` is similar to the `Data` field, but it's meant to store a struct that represents a form being rendered on the page.
`Page` 上的 `Form` 字段与 `Data` 字段类似，但它用于存储一个结构，该结构代表页面上正在呈现的表单。

An example of this pattern is:
这种模式的一个例子是

type ContactForm struct {
Email      string `form:"email" validate:"required,email"`
Message    string `form:"message" validate:"required"`
form.Submission
}


Embedding `form.Submission` satisfies the `form.Form` interface and makes dealing with submissions and validation extremely easy.
嵌入 `form.Submission` 满足了 `form.Form` 接口的要求，使处理提交和验证变得极为简单。

Then in your page:
然后在您的页面中

p := page.New(ctx)
p.Form = form.Get[ContactForm](ctx)


This will either initialize a new form to be rendered, or load one previously stored in the context (ie, if it was already submitted). How the _form_ gets populated with values so that your template can render them is covered in the next section.
这将初始化一个要呈现的新表单，或者加载以前存储在上下文中的表单（即，如果表单已经提交）。下一节将介绍如何为 _form_ 填充值，以便模板可以呈现它们。

#### Submission processing
提交处理

Form submission processing is made extremely simple by leveraging functionality provided by [Echo binding](https://echo.labstack.com/guide/binding/), [validator](https://github.com/go-playground/validator) and the `Submission` struct located in `pkg/form/submission.go`.
通过利用 [Echo binding](https://echo.labstack.com/guide/binding/)、[validator](https://github.com/go-playground/validator) 和 `Submission` 结构（位于 `pkg/form/submission.go` 中）提供的功能，表单提交处理变得极为简单。

Using the example form above, this is all you would have to do within the _POST_ callback for your route:
使用上面的表单示例，您只需在路由的 _POST_ 回调中执行这些操作即可：

Start by submitting the form along with the request context. This will:
首先提交表格和申请内容。这将

1. Store a pointer to the form so that your _GET_ callback can access the form values (shown previously). That allows the form to easily be re-rendered with any validation errors it may have as well as the values that were provided.
存储一个指向表单的指针，以便您的 _GET_ 回调可以访问表单值（如前所述）。这样就可以轻松地重新渲染表单，并显示表单可能存在的任何验证错误以及所提供的值。
2. Parse the input in the _POST_ data to map to the struct so the fields becomes populated. This uses the `form` struct tags to map form input values to the struct fields.
解析 _POST_ 数据中的输入，将其映射到结构中，从而填充字段。这将使用 `form` 结构标记将表单输入值映射到结构字段。
3. Validate the values in the struct fields according to the rules provided in the optional `validate` struct tags.
根据可选的 `validate` 结构标记中提供的规则，验证结构字段中的值。

var input ContactForm

err := form.Submit(ctx, &input)


Check the error returned, and act accordingly. For example:
检查返回的错误，并采取相应措施。例如

switch err.(type) {
case nil:
// All good!
case validator.ValidationErrors:
// The form input was not valid, so re-render the form
return c.Page(ctx)
default:
// Request failed, show the error page
return err
}


And finally, your template:
最后是你的模板：

<form id="contact" method="post" hx-post="{{url "contact.post"}}">
<input id="email" name="email" type="email" class="input" value="{{.Form.Email}}">
<input id="message" name="message" type="text" class="input" value="{{.Form.Message}}">
</form


#### Inline validation
内联验证

The `Submission` makes inline validation easier because it will store all validation errors in a map, keyed by the form struct field name. It also contains helper methods that your templates can use to provide classes and extract the error messages.
`Submission` 使内联验证变得更容易，因为它会将所有验证错误存储在一个以表单结构字段名为关键字的映射中。它还包含辅助方法，您的模板可以使用这些方法提供类并提取错误信息。

While [validator](https://github.com/go-playground/validator) is a great package that is used to validate based on struct tags, the downside is that the messaging, by default, is not very human-readable or easy to override. Within `Submission.setErrorMessages()` the validation errors are converted to more readable messages based on the tag that failed validation. Only a few tags are provided as an example, so be sure to expand on that as needed.
[validator](https://github.com/go-playground/validator)是一个用于根据结构标记进行验证的优秀软件包，但其缺点是默认情况下的消息传递不是非常人性化，也不容易覆盖。在 `Submission.setErrorMessages()` 中，验证错误会根据验证失败的标记转换为更易读的信息。仅提供了几个标记作为示例，因此请务必根据需要进行扩展。

To provide the inline validation in your template, there are two things that need to be done.
要在模板中提供内联验证，需要做两件事。

First, include a status class on the element so it will highlight green or red based on the validation:
首先，在元素上加入状态类，这样它就会根据验证结果高亮显示绿色或红色：

<input id="email" name="email" type="email" class="input {{.Form.GetFieldStatusClass "Email"}}" value="{{.Form.Email}}">


Second, render the error messages, if there are any for a given field:
其次，如果给定字段有错误信息，则渲染错误信息：

{{template "field-errors" (.Form.GetFieldErrors "Email")}}


### Headers
页眉

HTTP headers can be set either via the `Page` or the _context_:
HTTP 头信息可通过 `Page` 或 _context_ 设置：

p := page.New(ctx)
p.Headers["HeaderName"] = "header-value"


ctx.Response().Header().Set("HeaderName", "header-value")


### Status code
状态代码

The HTTP response status code can be set either via the `Page` or the _context_:
HTTP 响应状态代码可通过 `Page` 或 _context_ 设置：

p := page.New(ctx)
p.StatusCode = http.StatusTooManyRequests


ctx.Response().Status = http.StatusTooManyRequests


### Metatags
元标记

The `Page` provides the ability to set basic HTML metatags which can be especially useful if your web application is publicly accessible. Only fields for the _description_ and _keywords_ are provided but adding additional fields is very easy.
`Page` 提供了设置基本 HTML 元标记的功能，如果您的网络应用程序可被公众访问，该功能将特别有用。只提供了 _description_ 和 _keywords_ 字段，但添加其他字段非常容易。

p := page.New(ctx)
p.Metatags.Description = "The page description."
p.Metatags.Keywords = []string{"Go", "Software"}


A _component_ template is included to render metatags in `core.gohtml` which can be used by adding `{{template "metatags" .}}` to your _layout_.
_component_ 模板包含在 `core.gohtml` 中，可通过在 _布局中添加 `{{template "metatags" .}}` 来呈现元标记。_

### URL and link generation
生成 URL 和链接

Generating URLs in the templates is made easy if you follow the [routing patterns](#patterns) and provide names for your routes. Echo provides a `Reverse` function to generate a route URL with a given route name and optional parameters. This function is made accessible to the templates via _funcmap_ function `url`.
如果您遵循[路由模式](#patterns)并为您的路由提供名称，那么在模板中生成 URL 将变得非常容易。Echo 提供了一个 `Reverse` 函数，用于使用给定的路由名称和可选参数生成路由 URL。该函数可通过 _funcmap_ 函数 `url` 访问模板。

As an example, if you have route such as:
举例来说，如果您有这样的路线：

e.GET("/user/profile/:user", handler.Get).Name = "user_profile"


And you want to generate a URL in the template, you can:
如果您想在模板中生成一个 URL，也是可以的：

{{url "user_profile" 1}


Which will generate: `/user/profile/1`
这将生成`/user/profile/1`

There is also a helper function provided in the [funcmap](#funcmap) to generate links which has the benefit of adding an _active_ class if the link URL matches the current path. This is especially useful for navigation menus.
[funcmap](#funcmap) 中还提供了一个辅助函数来生成链接，如果链接 URL 与当前路径匹配，该函数还可以添加一个 _active_ 类。这对导航菜单尤其有用。

{{link (url "user_profile" .AuthUser.ID) "Profile" .Path "extra-class"}}


Will generate:
将产生

<a href="/user/profile/1" class="is-active extra-class">Profile</a>


Assuming the current _path_ is `/user/profile/1`; otherwise the `is-active` class will be excluded.
假设当前_路径_是`/user/profile/1`；否则将排除`is-active`类。

### HTMX support
支持 HTMX

[HTMX](https://htmx.org/) is an awesome JavaScript library allows you to access AJAX, CSS Transitions, WebSockets and Server Sent Events directly in HTML, using attributes, so you can build modern user interfaces with the simplicity and power of hypertext.
[HTMX](https://htmx.org/) 是一个超棒的 JavaScript 库，它允许您使用属性直接在 HTML 中访问 AJAX、CSS 过渡、WebSockets 和服务器发送事件，因此您可以利用超文本的简洁性和强大功能构建现代用户界面。

Many examples of its usage are available in the included examples:
附带的示例中提供了许多使用示例：

*   All navigation links use [boost](https://htmx.org/docs/#boosting) which dynamically replaces the page content with an AJAX request, providing a SPA-like experience.
所有导航链接都使用 [boost](https://htmx.org/docs/#boosting)，通过 AJAX 请求动态替换页面内容，提供类似 SPA 的体验。
*   All forms use either [boost](https://htmx.org/docs/#boosting) or [hx-post](https://htmx.org/docs/#triggers) to submit via AJAX.
所有表单均使用 [boost](https://htmx.org/docs/#boosting) 或 [hx-post](https://htmx.org/docs/#triggers) 通过 AJAX 提交。
*   The mock search autocomplete modal uses [hx-get](https://htmx.org/docs/#targets) to fetch search results from the server via AJAX and update the UI.
模拟搜索自动完成模态使用 [hx-get](https://htmx.org/docs/#targets) 通过 AJAX 从服务器获取搜索结果并更新用户界面。
*   The mock posts on the homepage/dashboard use [hx-get](https://htmx.org/docs/#targets) to fetch and page posts via AJAX.
主页/仪表板上的模拟帖子使用 [hx-get](https://htmx.org/docs/#targets) 通过 AJAX 获取和页面帖子。

All of this can be easily accomplished without writing any JavaScript at all.
所有这些都可以在不编写任何 JavaScript 的情况下轻松实现。

Another benefit of [HTMX](https://htmx.org/) is that it's completely backend-agnostic and does not require any special tools or integrations on the backend. But to make things easier, included is a small package to read and write [HTTP headers](https://htmx.org/docs/#requests) that HTMX uses to communicate additional information and commands.
[HTMX](https://htmx.org/)的另一个优点是它与后台完全无关，不需要任何特殊工具或后台集成。不过，为了让事情变得更简单，我们还提供了一个小软件包，用于读写 [HTTP 标头](https://htmx.org/docs/#requests)，HTMX 利用这些标头传达其他信息和命令。

The `htmx` package contains the headers for the _request_ and _response_. When a `Page` is initialized, `Page.HTMX.Request` will also be initialized and populated with the headers that HTMX provides, if HTMX made the request. This allows you to determine if HTMX is making the given request and what exactly it is doing, which could be useful both in your _route_ as well as your _templates_.
`htmx` 包包含 _request_ 和 _response_ 的头部。当初始化 `Page` 时，`Page.HTMX.Request` 也将被初始化，并填充 HTMX 提供的头信息（如果 HTMX 提出了请求）。这样，您就可以确定 HTMX 是否发出了给定的请求，以及它到底在做什么，这对您的 _route_ 和 _templates_ 都很有用。

If you need to set any HTMX headers in your `Page` response, this can be done by altering `Page.HTMX.Response`.
如果您需要在 `Page` 响应中设置任何 HTMX 标头，可通过更改 `Page.HTMX.Response` 来实现。

#### Layout template override
布局模板覆盖

To facilitate easy partial rendering for HTMX requests, the `Page` will automatically change your _Layout_ template to use `htmx.gohtml`, which currently only renders `{{template "content" .}}`. This allows you to use an HTMX request to only update the content portion of the page, rather than the entire HTML.
为了便于 HTMX 请求的部分呈现，`Page` 将自动更改您的 _Layout_ 模板，使其使用 `htmx.gohtml` ，该模板目前仅呈现 `{{template "content" .}}` 。这样，您就可以使用 HTMX 请求只更新页面的内容部分，而不是整个 HTML。

This override only happens if the HTMX request being made is **not a boost** request because **boost** requests replace the entire `body` element so there is no need to do a partial render.
只有当 HTMX 请求不是 **boost** 请求时，才会覆盖此覆盖，因为 **boost** 请求会替换整个 `body` 元素，因此无需进行部分呈现。

#### Conditional processing / rendering
条件处理/渲染

Since HTMX communicates what it is doing with the server, you can use the request headers to conditionally process in your _route_ or render in your _template_, if needed. If your routes aren't doing multiple things, you may not need this, but it's worth knowing how flexible you can be.
由于 HTMX 会与服务器通信，因此如果需要，您可以使用请求头在 _路由_中进行有条件处理，或在 _模板_中进行渲染。如果你的路由不是做多件事，你可能不需要这样做，但值得了解一下你可以做得多么灵活。

A simple example of this:
举个简单的例子：

if page.HTMX.Request.Target == "search" {
// You know this request HTMX is fetching content just for the #search element
}


{{if eq .HTMX.Request.Target "search"}}
// Render content for the #search element
{{end}}


#### CSRF token
CSRF 标记

If [CSRF](#csrf) protection is enabled, the token value will automatically be passed to HTMX to be included in all non-GET requests. This is done in the `footer` template by leveraging HTMX [events](https://htmx.org/reference/#events).
如果启用了 [CSRF](#csrf) 保护，标记值将自动传递给 HTMX，并包含在所有非 GET 请求中。这是通过利用 HTMX [events](https://htmx.org/reference/#events) 在 `footer` 模板中实现的。

### Rendering the page
渲染页面

Once your `Page` is fully built, rendering it via the embedded `TemplateRenderer` in your _handler_ can be done simply by calling `RenderPage()`:
一旦您的 `Page` 完全构建完成，只需调用 `RenderPage()` 即可通过 _处理程序_中的嵌入式 `TemplateRenderer` 渲染它：

func (c *home) Get(ctx echo.Context) error {
p := page.New(ctx)
p.Layout = templates.LayoutMain
p.Name = templates.PageHome
return c.RenderPage(ctx, p)
}


Template renderer
模板呈现器
-------------------------

The _template renderer_ is a _Service_ on the `Container` that aims to make template parsing and rendering easy and flexible. It is the mechanism that allows the `Page` to do [automatic template parsing](#automatic-template-parsing). The standard `html/template` is still the engine used behind the scenes. The code can be found in `pkg/services/template_renderer.go`.
_模板呈现器_是 _服务_，位于 `Container` 上，旨在使模板解析和呈现变得简单而灵活。它是允许 `Page` 进行 [自动模板解析](#automatic-template-parsing)的机制。标准的 `html/template` 仍然是幕后使用的引擎。代码可在 `pkg/services/template_renderer.go` 中找到。

Here is an example of a complex rendering that uses multiple template files as well as an entire directory of template files:
下面是一个使用多个模板文件和整个模板文件目录的复杂渲染示例：

buf, err = c.TemplateRenderer.
Parse().
Group("page").
Key("home").
Base("main").
Files("layouts/main", "pages/home").
Directories("components").
Execute(data)


This will do the following:
这将起到以下作用：

*   [Cache](#caching) the parsed template with a _group_ of `page` and _key_ of `home` so this parse only happens once
[缓存](#caching)已解析的模板，其中_组_为`page`，_键_为`home`，因此该解析只发生一次。
*   Set the _base template file_ as `main`
将 _基础模板文件_设置为 `main`
*   Include the templates `templates/layout/main.gohtml` and `templates/pages/home.gohtml`
包含模板 `templates/layout/main.gohtml` 和 `templates/pages/home.gohtml`
*   Include all templates located within the directory `templates/components`
包括位于 `templates/components` 目录中的所有模板
*   Include the [funcmap](#funcmap)
包含 [funcmap](#funcmap)
*   Execute the parsed template with `data` being passed in to the templates
执行解析后的模板，并将 `data` 传递给模板

Using the example from the [page rendering](#rendering-the-page), this is will execute:
使用[页面呈现](#rendering-the-page)中的示例，将执行此操作：

buf, err = c.TemplateRenderer.
Parse().
Group("page").
Key(page.Name).
Base(page.Layout).
Files(
fmt.Sprintf("layouts/%s", page.Layout),
fmt.Sprintf("pages/%s", page.Name),
).
Directories("components").
Execute(page)


If you have a need to _separately_ parse and cache the templates then later execute, you can separate the operations:
如果您需要_单独_解析和缓存模板，然后再执行，您可以将这些操作分开：

_, err := c.TemplateRenderer.
Parse().
Group("my-group").
Key("my-key").
Base("auth").
Files("layouts/auth", "pages/login").
Directories("components").
Store()


tpl, err := c.TemplateRenderer.Load("my-group", "my-key")
buf, err := tpl.Execute(data)


### Custom functions
自定义功能

All templates will be parsed with the [funcmap](#funcmap) so all of your custom functions as well as the functions provided by [sprig](https://github.com/Masterminds/sprig) will be available.
所有模板都将使用 [funcmap](#funcmap) 进行解析，因此您的所有自定义函数以及 [sprig](https://github.com/Masterminds/sprig) 提供的函数都将可用。

### Caching
缓存

Parsed templates will be cached within a `sync.Map` so the operation will only happen once per cache _group_ and _ID_. Be careful with your cache _group_ and _ID_ parameters to avoid collisions.
解析的模板将缓存在 `sync.Map` 中，因此每个缓存 _group_ 和 _ID_ 仅会发生一次操作。请小心使用缓存 _group_ 和 _ID_ 参数，以避免碰撞。

### Hot-reload for development
用于开发的热加载

If the current [environment](#environments) is set to `config.EnvLocal`, which is the default, the cache will be bypassed and templates will be parsed every time they are requested. This allows you to have hot-reloading without having to restart the application so you can see your HTML changes in the browser immediately.
如果当前[环境](#environments)设置为`config.EnvLocal`（这是默认设置），则将绕过缓存，并在每次请求时解析模板。这样，您就可以在无需重启应用程序的情况下进行热加载，从而可以立即在浏览器中看到 HTML 更改。

### File configuration
文件配置

To make things easier and less repetitive, parameters given to the _template renderer_ must not include the `templates` directory or the template file extensions. The file extension is stored as a constant (`TemplateExt`) within the `config` package.
为使操作更简便，减少重复，给 _模板呈现器_ 的参数不得包含 `templates` 目录或模板文件扩展名。文件扩展名将作为一个常量（`TemplateExt`）存储在 `config` 包中。

Funcmap
-------

The `funcmap` package provides a _function map_ (`template.FuncMap`) which will be included for all templates rendered with the [template renderer](#template-renderer). Aside from a few custom functions, [sprig](https://github.com/Masterminds/sprig) is included which provides over 100 commonly used template functions. The full list is available [here](http://masterminds.github.io/sprig/).
`funcmap`包提供了一个_函数图_（`template.FuncMap`），它将包含在使用 [模板呈现器](#template-renderer)呈现的所有模板中。除了一些自定义函数外，[sprig](https://github.com/Masterminds/sprig)还提供了 100 多个常用模板函数。[此处](http://masterminds.github.io/sprig/)提供了完整的列表。

To include additional custom functions, add to the map in `NewFuncMap()` and define the function in the package. It will then become automatically available in all templates.
要包含其他自定义函数，请在 `NewFuncMap()` 中添加到映射中，并在软件包中定义该函数。然后，它将自动在所有模板中可用。

Cache
缓存
----------

As previously mentioned, the default cache implementation is a simple in-memory store, backed by [otter](https://github.com/maypok86/otter), a lockless cache that uses [S3-FIFO](https://s3fifo.com/) eviction. The `Container` houses a `CacheClient` which is a useful, wrapper to interact with the cache (see examples below). Within the `CacheClient` is the underlying store interface `CacheStore`. If you wish to use a different store, such as Redis, and want to keep using the `CacheClient`, simply implement the `CacheStore` interface with a Redis library and adjust the `Container` initialization to use that.
如前所述，默认的缓存实现是一个简单的内存存储，由 [otter](https://github.com/maypok86/otter) 支持，这是一个使用 [S3-FIFO](https://s3fifo.com/) 驱逐的无锁缓存。`Container` 包含一个`CacheClient`，它是一个与缓存交互的有用封装器（请参阅下面的示例）。`CacheClient`中包含底层存储接口 `CacheStore`。如果您希望使用不同的存储，如 Redis，并希望继续使用 `CacheClient` ，只需使用 Redis 库实现 `CacheStore` 接口，并调整 `Container` 初始化以使用该存储。

The built-in usage of the cache is currently only for optional [page caching](#cached-responses) and a simple example route located at `/cache` where you can set and view the value of a given cache entry.
缓存的内置用法目前仅用于可选的 [页面缓存](#cached-responses)，以及位于 `/cache` 的一个简单路由示例，在该路由中，您可以设置和查看给定缓存项的值。

Since the current cache is in-memory, there's no need to adjust the `Container` during tests. When this project used Redis, the configuration had a separate database that would be used strictly for tests to avoid writing to your primary database. If you need that functionality, it is easy to add back in.
由于当前缓存在内存中，因此在测试过程中无需调整 `Container` 。当该项目使用 Redis 时，配置中有一个单独的数据库，严格用于测试，以避免写入主数据库。如果您需要该功能，很容易将其添加回去。

### Set data
设置数据

**Set data with just a key:
只需一个按键即可设置数据：**

err := c.Cache.
Set().
Key("my-key").
Data(myData).
Expiration(time.Hour * 2).
Save(ctx)


**Set data within a group:
在组内设置数据：**

err := c.Cache.
Set().
Group("my-group").
Key("my-key").
Expiration(time.Hour * 2).
Data(myData).
Save(ctx)


**Include cache tags:
包括缓存标签：**

err := c.Cache.
Set().
Key("my-key").
Tags("tag1", "tag2").
Expiration(time.Hour * 2).
Data(myData).
Save(ctx)


### Get data
获取数据

data, err := c.Cache.
Get().
Group("my-group").
Key("my-key").
Fetch(ctx)


### Flush data
冲洗数据

err := c.Cache.
Flush().
Group("my-group").
Key("my-key").
Execute(ctx)


### Flush tags
平装标签

This will flush all cache entries that were tagged with the given tags.
这将清除所有使用给定标签标记的缓存条目。

err := c.Cache.
Flush().
Tags("tag1", "tag2").
Execute(ctx)


### Tagging
标记

As shown in the previous examples, cache tags were provided because they can be convenient. However, maintaining them comes at a cost and it may not be a good fit for your application depending on your needs. When including tags, the `CacheClient` must lock in order to keep the tag index in sync. And since the tag index cannot support eviction, since that could result in a flush call not actually flushing the tag's keys, the maps that provide the index do not have a size limit. See the code for more details.
如前面的示例所示，提供缓存标签是因为它们很方便。但是，维护它们需要付出代价，而且根据您的需要，它可能并不适合您的应用程序。当包含标签时，`CacheClient`必须锁定以保持标签索引同步。由于标签索引不支持驱逐，因为驱逐可能导致刷新调用无法实际刷新标签的键，因此提供索引的映射没有大小限制。更多详情，请参阅代码。

Tasks
任务
----------

Tasks are queued operations to be executed in the background, either immediately, at a specfic time, or after a given amount of time has passed. Some examples of tasks could be long-running operations, bulk processing, cleanup, notifications, etc.
任务是在后台执行的队列操作，可以是立即执行、在特定时间执行，也可以是在一定时间后执行。任务的一些例子可以是长期运行的操作、批量处理、清理、通知等。

Since we're already using [SQLite](https://sqlite.org/) for our database, it's available to act as a persistent store for queued tasks so that tasks are never lost, can be retried until successful, and their concurrent execution can be managed. [Backlite](https://github.com/mikestefanello/backlite) is the library chosen to interface with [SQLite](https://sqlite.org/) and handle queueing tasks and processing them asynchronously. I wrote that specifically to address the requirements I wanted to satisfy for this project.
由于我们已经使用 [SQLite](https://sqlite.org/) 作为我们的数据库，因此它可以作为队列任务的持久存储，这样任务就不会丢失，可以重试直到成功，并且可以管理它们的并发执行。[Backlite](https://github.com/mikestefanello/backlite)是用于与[SQLite](https://sqlite.org/)接口的库，可处理队列任务和异步处理任务。这是我为满足本项目的需求而专门编写的。

To make things easy, the _Backlite_ client is provided as a _Service_ on the `Container` which allows you to register queues and add tasks.
为了方便起见，_Backlite_ 客户端是作为 _Service_ 在 `Container` 上提供的，它允许您注册队列和添加任务。

Configuration for the _Backlite_ client is exposed through the app's yaml configuration. The required database schema will be automatically installed when the app starts.
_Backlite_ 客户端的配置通过应用程序的 yaml 配置公开。应用程序启动时，将自动安装所需的数据库模式。

### Queues
队列

A full example of a queue implementation can be found in `pkg/tasks` with an interactive form to create a task and add to the queue at `/task` (see `pkg/handlers/task.go`). Also refer to the [Backlite](https://github.com/mikestefanello/backlite) documentation for reference and examples.
队列实现的完整示例可在 `pkg/tasks` 中找到，在 `/task` 中有一个创建任务并添加到队列的交互式表单（请参阅 `pkg/handlers/task.go`）。有关参考和示例，请参阅 [Backlite](https://github.com/mikestefanello/backlite) 文档。

See `pkg/tasks/register.go` for a simple way to register all of your queues and to easily pass the `Container` to them so the queue processor callbacks have access to all of your app's dependencies.
请参阅 `pkg/tasks/register.go`，了解注册所有队列的简单方法，并轻松将 `Container` 传递给它们，以便队列处理器回调可以访问应用程序的所有依赖项。

### Dispatcher
调度员

The _task dispatcher_ is what manages the worker pool used for executing tasks in the background. It monitors incoming and scheduled tasks and handles sending them to the pool for execution by the queue's processor callback. This must be started in order for this to happen. In `cmd/web/main.go`, the _task dispatcher_ is automatically started when the app starts via:
_任务派发器_负责管理用于在后台执行任务的工人池。它负责监控传入的任务和计划任务，并通过队列的处理器回调将任务发送到池中执行。为此，必须启动该程序。在 `cmd/web/main.go` 中，当应用程序通过以下方式启动时，_任务派发器_ 将自动启动：

c.Tasks.Start(ctx)


The app [configuration](#configuration) contains values to configure the client and dispatcher including how many goroutines to use, when to release stuck tasks back into the queue, and how often to cleanup retained tasks in the database.
应用程序 [configuration](#configuration) 包含用于配置客户端和调度程序的值，包括使用多少个 goroutines、何时将卡住的任务释放回队列，以及多久清理一次数据库中保留的任务。

When the app is shutdown, the dispatcher is given 10 seconds to wait for any in-progress tasks to finish execution. This can be changed in `cmd/web/main.go`.
当应用程序关闭时，会给调度程序 10 秒钟的时间来等待任何正在执行的任务执行完毕。这可以在 `cmd/web/main.go` 中更改。

Cron
克朗
---------

By default, no cron solution is provided because it's very easy to add yourself if you need this. You can either use a [ticker](https://pkg.go.dev/time#Ticker) or a [library](https://github.com/robfig/cron).
默认情况下，不提供 cron 解决方案，因为如果需要的话，很容易自己添加。您可以使用 [标记](https://pkg.go.dev/time#Ticker)或 [库](https://github.com/robfig/cron)。

Files
文件
----------

To handle file management functionality such as file uploads, an abstracted file system interface is provided as a _Service_ on the `Container` powered by [afero](https://github.com/spf13/afero). This allows you to easily change the file system backend (ie, local, GCS, SFTP, in-memory) without having to change any of the application code other than the initialization on the `Container`. By default, the local OS is used with a directory specified in the application configuration (which defaults to `uploads`). When running tests, an in-memory file system backend is automatically used.
为处理文件管理功能（如文件上传），我们在由 [afero](https://github.com/spf13/afero) 提供支持的 _Container_ 上提供了一个抽象文件系统接口作为 _Service_ 。这样，您就可以轻松更改文件系统后端（即本地、GCS、SFTP、内存），而无需更改除 `Container` 上的初始化之外的任何应用程序代码。默认情况下，本地操作系统使用应用程序配置中指定的目录（默认为 `uploads`）。运行测试时，将自动使用内存文件系统后端。

A simple file upload form example is provided at `/files` which also dynamically lists all files previously uploaded. No database entities or entries are created or provided for files and uploaded files are not available to be served. You will have to implement whatever functionality your application needs.
`/files` 中提供了一个简单的文件上传表单示例，该表单还动态列出了之前上传的所有文件。我们不会为文件创建或提供数据库实体或条目，也不会为上传的文件提供服务。您必须实现您的应用程序所需的任何功能。

Static files
静态文件
-------------------

Static files are currently configured in the router (`pkg/handler/router.go`) to be served from the `static` directory. If you wish to change the directory, alter the constant `config.StaticDir`. The URL prefix for static files is `/files` which is controlled via the `config.StaticPrefix` constant.
静态文件目前在路由器（`pkg/handler/router.go`）中被配置为从 `static` 目录中提供。如果您想更改目录，请更改常量 `config.StaticDir`。静态文件的 URL 前缀是 `/files`，它由 `config.StaticPrefix` 常量控制。

### Cache control headers
缓存控制标头

Static files are grouped separately so you can apply middleware only to them. Included is a custom middleware to set cache control headers (`middleware.CacheControl`) which has been added to the static files router group.
静态文件被单独分组，因此你可以只对它们应用中间件。其中包括一个用于设置缓存控制头的自定义中间件（`middleware.CacheControl`），该中间件已添加到静态文件路由器组中。

The cache max-life is controlled by the configuration at `Config.Cache.Expiration.StaticFile` and defaults to 6 months.
缓存的最长寿命由 `Config.Cache.Expiration.StaticFile` 配置控制，默认为 6 个月。

### Cache-buster
缓存克星

While it's ideal to use cache control headers on your static files so browsers cache the files, you need a way to bust the cache in case the files are changed. In order to do this, a function is provided in the [funcmap](#funcmap) to generate a static file URL for a given file that appends a cache-buster query. This query string is randomly generated and persisted until the application restarts.
虽然在静态文件上使用缓存控制头以便浏览器缓存文件是最理想的做法，但您需要一种方法来破坏缓存，以防文件被更改。为此，[funcmap](#funcmap)中提供了一个函数，用于为给定文件生成一个静态文件 URL，并附加一个缓存破坏查询。该查询字符串是随机生成的，并一直保留到应用程序重新启动为止。

For example, to render a file located in `static/picture.png`, you would use:
例如，要渲染位于 `static/picture.png` 中的文件，您可以使用

<img src="{{file "picture.png"}}"/>


Which would result in:
这将导致

<img src="/files/picture.png?v=9fhe73kaf3"/>


Where `9fhe73kaf3` is the randomly-generated cache-buster.
其中，`9fhe73kaf3`是随机生成的高速缓存抑制器。

Email
电子邮件
------------

An email client was added as a _Service_ to the `Container` but it is just a skeleton without any actual email-sending functionality. The reason is because there are a lot of ways to send email and most prefer using a SaaS solution for that. That makes it difficult to provide a generic solution that will work for most applications.
电子邮件客户端已作为 _Service_ 添加到 `Container` 中，但它只是一个骨架，没有任何实际的电子邮件发送功能。原因是发送电子邮件的方式有很多，而且大多数人更喜欢使用 SaaS 解决方案。因此，很难提供一个适用于大多数应用程序的通用解决方案。

The structure in the client (`MailClient`) makes composing emails very easy and you have the option to construct the body using either a simple string or with a template by leveraging the [template renderer](#template-renderer). The standard library can be used if you wish to send email via SMTP and most SaaS providers have a Go package that can be used if you choose to go that direction. **You must** finish the implementation of `MailClient.send`.
客户端的结构（`MailClient`）使电子邮件的撰写非常简单，您可以选择使用简单的字符串或模板（通过使用 [template renderer](#template-renderer) 来构建正文。如果您希望通过 SMTP 发送电子邮件，可以使用标准库，如果您选择朝这个方向发展，大多数 SaaS 提供商都有 Go 软件包可供使用。**您必须**完成`MailClient.send`的实现。

The _from_ address will default to the configuration value at `Config.Mail.FromAddress`. This can be overridden per-email by calling `From()` on the email and passing in the desired address.
_from_ 地址将默认为 `Config.Mail.FromAddress` 中的配置值。可以通过在电子邮件上调用 `From()` 并输入所需的地址，来覆盖每封邮件。

See below for examples on how to use the client to compose emails.
有关如何使用客户端撰写电子邮件的示例，请参阅下文。

**Sending with a string body**:
**使用字符串正文发送**：

err = c.Mail.
Compose().
To("hello@example.com").
Subject("Welcome!").
Body("Thank you for registering.").
Send(ctx)


**Sending with a template body**:
**使用模板正文发送**：

err = c.Mail.
Compose().
To("hello@example.com").
Subject("Welcome!").
Template("welcome").
TemplateData(templateData).
Send(ctx)


This will use the template located at `templates/emails/welcome.gohtml` and pass `templateData` to it.
这将使用位于 `templates/emails/welcome.gohtml` 的模板，并将 `templateData` 传递给它。

HTTPS
-----

By default, the application will not use HTTPS but it can be enabled easily. Just alter the following configuration:
默认情况下，应用程序不使用 HTTPS，但可以轻松启用。只需更改以下配置即可：

*   `Config.HTTP.TLS.Enabled`: `true`
`Config.HTTP.TLS.Enabled`：`true`
*   `Config.HTTP.TLS.Certificate`: Full path to the certificate file
`Config.HTTP.TLS.Certificate`：证书文件的完整路径
*   `Config.HTTP.TLS.Key`: Full path to the key file
`Config.HTTP.TLS.Key`：密钥文件的完整路径

To use _Let's Encrypt_ follow [this guide](https://echo.labstack.com/cookbook/auto-tls/#server).
要使用_Let's Encrypt_，请遵循[本指南](https://echo.labstack.com/cookbook/auto-tls/#server)。

Logging
记录
------------

By default, the [Echo logger](https://echo.labstack.com/guide/customization/#logging) is not used for the following reasons:
默认情况下，[回声记录仪](https://echo.labstack.com/guide/customization/#logging)不被使用，原因如下：

1. It does not support structured logging, which makes it difficult to deal with variables, especially if you intend to store a logger in context with pre-populated attributes.
它不支持结构化日志记录，因此很难处理变量，尤其是当你打算在上下文中存储带有预填充属性的日志记录器时。
2. The upcoming v5 release of Echo will not contain a logger.
即将发布的 Echo v5 版本将不包含记录仪。
3. It should be easy to use whatever logger you prefer (even if that is Echo's logger).
使用您喜欢的任何记录仪（即使是 Echo 的记录仪）都很容易。

The provided implementation uses the relatively new [log/slog](https://go.dev/blog/slog) library which was added to Go in version 1.21 but swapping that out for whichever you prefer is very easy.
所提供的实现使用了相对较新的 [log/slog](https://go.dev/blog/slog) 库，该库是在 1.21 版中添加到 Go 中的，但将其替换为您喜欢的任何库都非常容易。

### Context
背景

The simple `pkg/log` package provides the ability to set and get a logger from the Echo context. This is especially useful when you use the provided logger middleware (see below). If you intend to use a different logger, modify these methods to receive and return the logger of your choice.
简单的 `pkg/log` 软件包提供了从 Echo 上下文设置和获取日志记录器的功能。这在使用所提供的日志中间件（见下文）时尤其有用。如果您打算使用不同的日志记录器，请修改这些方法以接收和返回您选择的日志记录器。

### Usage
使用方法

Adding a logger to the context:
为上下文添加日志记录器

logger := slog.New(logHandler).With("id", requestId)
log.Set(ctx, logger)


Access and use the logger:
访问和使用记录仪

func (h *handler) Page(ctx echo.Context) error {
log.Ctx(ctx).Info("send a message to the log",
"value_one", valueOne,
"value_two", valueTwo,
)
}


### Log level
日志级别

When the _Container_ configuration is initialized (`initConfig()`), the `slog` default log level is set based on the environment. `INFO` is used for production and `DEBUG` for everything else.
当 _Container_ 配置初始化时（`initConfig()` ），`slog` 默认日志级别将根据环境进行设置。`INFO` 用于生产环境，而 `DEBUG` 用于其他环境。

### Middleware
中间件

The `SetLogger()` middleware has been added to the router which sets an initialized logger on the request context. It's recommended that this remains after Echo's `RequestID()` middleware because it will add the request ID to the logger which means that all logs produced for that given request will contain the same ID, so they can be linked together. If you want to include more attributes on all request logs, set those fields here.
路由器中添加了 `SetLogger()` 中间件，它可以在请求上下文中设置一个初始化的日志记录器。建议将其保留在 Echo 的 `RequestID()` 中间件之后，因为它会将请求 ID 添加到日志记录器中，这意味着为给定请求生成的所有日志都将包含相同的 ID，因此可以将它们链接在一起。如果您想在所有请求日志中包含更多属性，请在此处设置这些字段。

The `LogRequest()` middleware is a replacement for Echo's `Logger()` middleware which produces a log of every request made, but uses our logger rather than Echo's.
`LogRequest()` 中间件可替代 Echo 的 `Logger()` 中间件，后者会生成每个请求的日志，但使用的是我们的日志记录器而不是 Echo 的。

2024/06/15 09:07:11 INFO GET /contact request_id=gNblvugTKcyLnBYPMPTwMPEqDOioVLKp ip=::1 host=localhost:8000 referer="" status=200 bytes_in=0 bytes_out=5925 latency=107.527803ms


Roadmap
路线图
-------------

Future work includes but is not limited to:
未来的工作包括但不限于

*   Admin section
管理部分
*   OAuth
*   Flexible pager templates
灵活的寻呼机模板

Credits
荣誉
------------

Thank you to all of the following amazing projects for making this possible.
感谢以下所有令人惊叹的项目，使这一切成为可能。

*   [afero
红掌](https://github.com/spf13/afero)
*   [alpinejs
阿尔卑斯山](https://github.com/alpinejs/alpine)
*   [backlite
背光](https://github.com/mikestefanello/backlite)
*   [bulma
灯泡](https://github.com/jgthms/bulma)
*   [echo
回响](https://github.com/labstack/echo)
*   [ent
入口](https://github.com/ent/ent)
*   [go
去](https://go.dev/)
*   [go-sqlite3](https://github.com/mattn/go-sqlite3)
*   [goquery
查询](https://github.com/PuerkitoBio/goquery)
*   [htmx](https://github.com/bigskysoftware/htmx)
*   [jwt](https://github.com/golang-jwt/jwt)
*   [otter
獭](https://github.com/maypok86/otter)
*   [sessions
会议](https://github.com/gorilla/sessions)
*   [sprig
萌芽](https://github.com/Masterminds/sprig)
*   [sqlite](https://sqlite.org/)
*   [testify
证明](https://github.com/stretchr/testify)
*   [validator
验证器](https://github.com/go-playground/validator)
*   [viper
毒蛇](https://github.com/spf13/viper)

