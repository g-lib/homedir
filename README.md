# go-homedir

本包就是用来在不用cgo的情况下获取用户家目, 所以本库可以在跨平台编译环境下使用。

使用起来很简单, 直接调用 `homedir.Dir()` 获取用户家目录, a调用 `homedir.Expand()` 展开 `~` 为家目录路径。

**为什么不直接使用 `os/user`?** Golang自带的 `os/user` 包在Darwin系统需要cgo。 这意味着凡是使用了这个包的Golangf代码都不能跨平台编译。但是`os/user`99%的时间只使用用来遍历用户家目录，但是家目录我们可以不用cgo便能获取到。这个包就是用来在不用cgo的情况下获取用户家目录，从而不影响跨平台编译。

## Fork-From

[go-home-dir](https://github.com/mitchellh/go-homedir)