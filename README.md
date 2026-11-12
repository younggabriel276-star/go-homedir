# go-homedir
    
This is a Go library for detecting the user's home directory without
the use of cgo, so the library can be used in cross-compilation environments.

Usage is incredibly simple, just call `homedir.Dir()` to get the home directory
for a user, and `homedir.Expand()` to expand the `~` in a path to the home
directory.

**Why not just use `os/user`?** The built-in `os/user` package requires
cgo on Darwin systems. This means that any Go codCode that uses that package
cannot cross-compile. But 99% of the time, the use for `os/user` is just to
retrieve the home directory, which we can do for the current user without
cgo. This library does that, enabling cross-compilation.
go-homedir

This Go library identifies the user’s home directory without cgo, allowing use in cross-compilation settings.

Usage is straightforward: call homedir.Dir() to obtain a user’s home directory and homedir.Expand() to replace ~ in a path with that directory.

    Why not use os/user? The standard os/user package needs cgo on Darwin systems, which blocks cross-compilation. Since most uses of os/user simply fetch the home directy, this library provides that capability f the current user without cgo, suppting cross-compilation.