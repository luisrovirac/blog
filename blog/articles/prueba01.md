---
sidebar: auto
title: titulo nuevo
date: 2019-9-7 18:33:00
excerpt: Vuesax is a radically new framework and with an idea of ​​being different from other frameworks, we love what we have achieved so far in v3.x but now we want to give a total change in many features and improve the internal code as in the design.
autor: Luis Manuel Rovira Cruz
type: post
blog: true
tags:
  - Announcements
  - Pruebatag02
---

## Una prueba de fuego

lorem

::: tip
This is a tip
:::

::: warning no funciona
This is a warning
:::

::: danger
This is a dangerous warning
:::

```php{6}
namespace Illuminate\Support\Facades;
use Closure;
use Mockery;
use RuntimeException;
use Mockery\MockInterface;
abstract class Facade
{
    /**
     * The application instance being facaded.
     *
     * @var \Illuminate\Contracts\Foundation\Application
     */
    protected static $app;
    /**
     * The resolved object instances.
     *
     * @var array
     */
    protected static $resolvedInstance;
    /**
     * Run a Closure when the facade has been resolved.
     *
     * @param  \Closure  $callback
     * @return void
     */
    public static function resolved(Closure $callback)
    {
        static::$app->afterResolving(static::getFacadeAccessor(),
        function ($service) use ($callback) {
            $callback($service);
        });
    }
    /**
     * Convert the facade into a Mockery spy.
     *
     * @return \Mockery\MockInterface
     */
    public static function spy()
    {
        if (! static::isMock()) {
            $class = static::getMockableClass();
            return tap($class ? Mockery::spy($class) : Mockery::spy(),
            function ($spy) {
                static::swap($spy);
            });
        }
    }
    /**
     * Initiate a mock expectation on the facade.
     *
     * @return \Mockery\Expectation
     */
    public static function shouldReceive()
```


