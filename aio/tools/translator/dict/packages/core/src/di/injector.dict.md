["DI Providers"](guide/dependency-injection-providers).

[“DI 提供者”](guide/dependency-injection-providers)。

The following example creates a service injector instance.

以下示例创建一个服务注入器实例。

{&commat;example core/di/ts/provider_spec.ts region='ConstructorProvider'}



Usage example

使用范例

{&commat;example core/di/ts/injector_spec.ts region='Injector'}



`Injector` returns itself when given `Injector` as a token:

当给定 `Injector` 作为标记时，`Injector` 返回自身：

{&commat;example core/di/ts/injector_spec.ts region='injectInjector'}



Concrete injectors implement this interface. Injectors are configured
with [providers](guide/glossary#provider) that associate
dependencies of various types with [injection tokens](guide/glossary#di-token).

具体的注入器会实现此接口。配置有[某些提供者](guide/glossary#provider)的注入器，这些提供者会将各种类型的依赖项与[注入令牌](guide/glossary#di-token)相关联。

Internal note on the `options?: InjectOptions|InjectFlags` override of the `get`
method: consider dropping the `InjectFlags` part in one of the major versions.
It can **not** be done in minor/patch, since it's breaking for custom injectors
that only implement the old `InjectorFlags` interface.

关于 `options?: InjectOptions|InjectFlags` 覆盖 `get` 方法：考虑将 `InjectFlags` 部分放在主要版本之一中。它**不能**在次要/补丁中完成，因为它对于仅实现旧的 `InjectorFlags` 接口的自定义注入器来说是中断的。

The instance from the injector if defined, otherwise the `notFoundValue`.

注入器中的实例（如果已定义），否则为 `notFoundValue`。

When the `notFoundValue` is `undefined` or `Injector.THROW_IF_NOT_FOUND`.

当 `notFoundValue` 为 `undefined` 或 `Injector.THROW_IF_NOT_FOUND` 时。

Retrieves an instance from the injector based on the provided token.

根据提供的标记从注入器中检索实例。

use object-based flags \(`InjectOptions`\) instead.

改用基于对象的标志（`InjectOptions`）。

from v4.0.0 use ProviderToken<T>

从 v4.0.0 开始，改用 InjectionToken<T>

from v5 use the new signature Injector.create\(options\)

从 v5 开始使用新的签名 Injector.create（options）

An object with the following properties:

具有以下属性的对象：

`providers`: An array of providers of the [StaticProvider type](api/core/StaticProvider).

`providers`：一组 [StaticProvider 类型](api/core/StaticProvider)的提供者。

`parent`: \(optional\) A parent injector.

`parent`：（可选）父注入器。

`name`: \(optional\) A developer-defined identifying name for the new injector.

`name`：（可选）新注入器的开发人员自定义的标识名称。

The new injector instance.

新的注入器实例。

Creates a new injector instance that provides one or more dependencies,
according to a given type or types of `StaticProvider`.

创建一个新的注入器实例，该实例会根据指定的类型或 `StaticProvider` 的类型提供一个或多个依赖项。