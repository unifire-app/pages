---
layout: full
homepage: true
disable_anchors: true
description: Aspect is a compiling template engine for Lua and LuaJIT.
---

<!-- {% raw %} -->

**Aspect** is a compiling templating engine for Lua and OpenResty.

<!-- <img align="right" src="./aspect.png" width="200"> -->


## Synopsis

```twig
<!DOCTYPE html>
<html>
    <head>
        {% block head %}
            <title>{{ page.title }}</title>
        {% endblock %}
    </head>
    <body>
        {% block content %}
            <ul id="navigation">
            {% for item in navigation %}
                <li><a href="{{ item.href }}">
                    {{- item.caption|escape -}}
                </a></li>
            {% endfor %}
            </ul>
    
            <h1>My Webpage</h1>
            {{ page.body }}
        {% endblock %}
    </body>
</html>
```

<div class="row">
<div class="col-lg-6" markdown="1">

## Installation
{:.mt-lg-0}

The recommended way to install Aspect is via LuaRocks:

```bash
luarocks install aspect
```

Or add `src/?.lua` to `package.path`:

```lua
package.path = '/path/to/aspect/src/?.lua;' .. package.path
```

## Documentation links

- [Lua API](api.md)
- **Template**
  - [Syntax](syntax.md)
  - [Tags](tags.md)
  - [Filters](filters.md)
  - [Functions](funcs.md)
  - [Tests](tests.md)

## Features
{:.mt-lg-0}

The key-features are...
* _Well known_: The most popular syntax is used - 
  [Twig](https://twig.symfony.com/doc/2.x/templates.html) compatible, [Jinja](https://jinja.palletsprojects.com/en/2.10.x/templates/)/[Liquid](https://shopify.github.io/liquid/) like.
* _Fast_: Aspect compiles templates down to plain optimized Lua code. 
  Moreover, Lua code compiles into bytecode - the fastest representation of a template.
* _Secure_: Aspect has a sandbox mode to evaluate all template code. 
  This allows Aspect to be used as a template language for applications where users may modify the template design.
* _Flexible_: Aspect is powered by a flexible lexer and parser. 
  This allows the developer to define their own custom tags, filters, functions and operators, and to create their own DSL.
* _Supports_ lua 5.1/5.2/5.3 and luajit 2.0/2.1 (with OpenResty)
* Has [console renderer](./docs/cli.md).
* No dependencies. Pure Lua. 
* **[List of all features](./docs/features.md)**

Aspect also has a [console tool](./docs/cli.md) for rendering data

```bash
$ aspect /path/to/data.json /path/to/template.tpl
```

</div>
</div>
<!-- {% endraw %} -->
