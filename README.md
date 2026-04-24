# Minecraft Server Template

A template for running a vanilla or modded Minecraft server on a POSIX system, with support for Git integration and automatic modpack updates.

---

## Usage

1) Either create a repository from this template, clone it, or simply copy and paste its contents into a local directory.
2) Make sure to install a Java version that supports the Minecraft server version you want to run, and ensure it is available on your `PATH`.
3) Make sure that `jq` and either `curl` or `wget` are installed. All of them are usually preinstalled on most reasonable systems.
4) If you want Git integration, ensure that `git` is installed as well.
   - Additionally, it's a good idea to install `git-lfs` if you plan to use this template as is.
   - Otherwise, if you don't want to use Git LFS, remove the `.gitattributes` file provided by this template.
5) Edit `server-launcher.properties` to your liking.
   - For a vanilla setup, set `minecraft.version` to the version you want to run.
   - For a modded setup, specify the `packwiz.url` that points to a [Packwiz](https://github.com/packwiz/packwiz) metadata file *(usually `pack.toml`)*.
   - In order to use Git integration, set the `git.enable` property to `true`.
   - If you plan to use Git integration and want to prevent the repository size from spiraling out of control, you can set the `git.limit` property in order to instruct the launcher to periodically compact the history into a single commit.
6) Run `./server-launcher`.
   - Any arguments provided to `server-launcher` will be passed directly to the Minecraft server.
   - In order to pass arguments to the JVM, use the `java.args` property in `server-launcher.properties` or the `SERVER_LAUNCHER_JAVA_ARGS` environment variable.

----

## License

Licensed under the terms of the [CC0-1.0 License](LICENSE).
