Frequently-used modules

常用模块

An Angular application needs at least one module that serves as the root module.
As you add features to your app, you can add them in modules.
The following are frequently used Angular modules with examples of some of the things they contain:

Angular 应用至少需要一个充当根模块使用的模块。
如果你要把某些特性添加到应用中，可以通过添加模块来实现。
下列是一些常用的 Angular 模块，其中带有一些其内容物的例子：

To communicate with a server using the HTTP protocol.

使用 HTTP 协议与服务器通信。

To use `RouterLink`, `.forRoot()`, and `.forChild()`.

使用 `RouterLink` 、 `.forRoot()` 和 `.forChild()`。

To build reactive forms.

构建响应式表单。

To build template driven forms \(includes `NgModel`\).

构建模板驱动表单（包括 `NgModel`）。

To use `NgIf` and `NgFor`.

使用 `NgIf` 和 `NgFor`。

To run your application in a browser.

在浏览器中运行应用。

Import it from

导入自

Why you use it

为何用它

Importing modules

导入模块

When you use these Angular modules, import them in `AppModule`, or your feature module as appropriate, and list them in the `@NgModule` `imports` array.
For example, in the basic application generated by the [Angular CLI](cli), `BrowserModule` is the first import at the top of the `AppModule`, `app.module.ts`.

当你使用这些 Angular 模块时，在 `AppModule`（或适当的特性模块）中导入它们，并把它们列在当前 `@NgModule` 的 `imports` 数组中。比如，在 [Angular CLI](cli) 生成的基本应用中，`BrowserModule` 会在 `app.module.ts` 中 `AppModule` 的顶部最先导入。

The imports at the top of the array are JavaScript import statements while the `imports` array within `@NgModule` is Angular specific.
For more information on the difference, see [JavaScript Modules vs. NgModules](guide/ngmodule-vs-jsmodule).

文件顶部的这些导入是 JavaScript 的导入语句，而 `@NgModule` 中的 `imports` 数组则是 Angular 特有的。
要了解更多的不同点，参阅 [JavaScript 模块 vs. NgModule](guide/ngmodule-vs-jsmodule)。

`BrowserModule` and `CommonModule`

`BrowserModule` 和 `CommonModule`

`BrowserModule` imports `CommonModule`, which contributes many common directives such as `ngIf` and `ngFor`.
Additionally, `BrowserModule` re-exports `CommonModule` making all of its directives available to any module that imports `BrowserModule`.

`BrowserModule` 导入了 `CommonModule`，它贡献了很多通用的指令，比如 `ngIf` 和 `ngFor`。
另外，`BrowserModule` 重新导出了 `CommonModule`，以便它所有的指令在任何导入了 `BrowserModule` 的模块中都可以使用。

For applications that run in the browser, import `BrowserModule` in the root `AppModule` because it provides services that are essential to launch and run a browser application.
`BrowserModule`'s providers are for the whole application so it should only be in the root module, not in feature modules.
Feature modules only need the common directives in `CommonModule`; they don't need to re-install app-wide providers.

对于运行在浏览器中的应用来说，都必须在根模块中 `AppModule` 导入 `BrowserModule`，因为它提供了启动和运行浏览器应用时某些必须的服务。`BrowserModule` 的提供者是面向整个应用的，所以它只能在根模块中使用，而不是特性模块。
特性模块只需要 `CommonModule` 中的常用指令，它们不需要重新安装所有全应用级的服务。

If you do import `BrowserModule` into a lazy loaded feature module, Angular returns an error telling you to use `CommonModule` instead.

如果你把 `BrowserModule` 导入了惰性加载的特性模块中，Angular 就会返回一个错误，并告诉你要改用 `CommonModule`。

More on NgModules

关于 NgModule 的更多知识

You may also be interested in the following:

你可能还对下列内容感兴趣：

[Bootstrapping](guide/bootstrapping)

[引导启动](guide/bootstrapping)

[NgModules](guide/ngmodules)



[JavaScript Modules vs. NgModules](guide/ngmodule-vs-jsmodule)

[JavaScript 模块与 NgModules](guide/ngmodule-vs-jsmodule)。