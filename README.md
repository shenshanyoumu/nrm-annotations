# nrm -- NPM 仓库源管理器

[![NPM version][npm-image]][npm-url]

`nrm` 帮助开发者实现多个 NPM 仓库源间的快速切换,
目前内置仓库源: `npm`, `cnpm`, `taobao`, `nj(nodejitsu)`.

## 如何设置私有仓库源 ?

在项目中添加.yarnrc 配置文件:
`registry “http://your.registry”`

## 安装

```
$ npm install -g nrm
```

## 案例

```
$ nrm ls

* npm -----  https://registry.npmjs.org/
  cnpm ----  http://r.cnpmjs.org/
  taobao --  https://registry.npm.taobao.org/
  nj ------  https://registry.nodejitsu.com/
  skimdb -- https://skimdb.npmjs.com/registry

```

```
$ nrm use cnpm  //switch registry to cnpm

    Registry has been set to: http://r.cnpmjs.org/

```

## 使用

```
Usage: nrm [options] [command]

  Commands:

    ls                                    罗列所有可用的仓库源
    current                               当前仓库源地址
    use <registry>                        切换仓库源
    add <registry> <url> [home]           增加一个自定义的仓库源
    set-auth <registry> [value]           Set authorize information for a custom registry with a base64 encoded string or username and pasword
      -a  --always-auth                     Set is always auth
      -u  --username <username>             Your user name for this registry
      -p  --password <password>             Your password for this registry
    set-email <registry> <value>          Set email for a custom registry
    set-hosted-repo <registry> <value>    Set hosted npm repository for a custom registry to publish packages
    del <registry>                        Delete one custom registry
    home <registry> [browser]             Open the homepage of registry with optional browser
    test [registry]                       Show the response time for one or all registries
    publish [<tarball>|<folder>]          Publish package to current registry if current registry is a custom registry.  if you\'re not using custom registry, this command will run npm publish directly
      -t --tag [tag]                        Add tag
      -a --access <public|restricted>       Set access
      -o --otp [otpcode]                    Set otpcode
      -dr --dry-run                         Set is dry run
    help                                  Print this help

  Options:

    -h, --help     output usage information
    -V, --version  output the version number
```

## Registries

- [npm](https://www.npmjs.org)
- [cnpm](http://cnpmjs.org)
- [nodejitsu](https://www.nodejitsu.com)
- [taobao](http://npm.taobao.org/)

## Notice

When you are using preset registries the `publish` command will proxy to the npm official registry.
When you are using a custom registry you will need to run the `set-hosted-repo` to set a url to publish pacakges to your hosted registry.

## Maintainer is wanted

If you find nrm is useful and is a experienced node.js developer, then you can help maintain nrm.
If you have the interest you can reach me through email: pana.wang@outlook.com

## TODO

- None

## LICENSE

MIT

[npm-image]: https://img.shields.io/npm/v/nrm.svg?style=flat-square
[npm-url]: https://npmjs.org/package/nrm
