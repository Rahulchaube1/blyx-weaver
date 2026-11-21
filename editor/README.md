# Blyx Weaver

Lay out equal-width tiles on small or large viewports, distribute leftover pixels and map pointer coordinates back to an item.

This extension includes the Blyx Weaver 0.1.0 source, a runnable example and completions for its public functions. It uses the Blyx Language extension for syntax highlighting and execution.

## Run in the editor

1. Open an empty file named `weaver-demo.blyx`.
2. Type `blyx-weaver-demo` and select **Weaver — runnable example**. You can also use **Snippets: Fill File with Snippet**.
3. Choose **Blyx: Run File** from the command palette. Change an argument near the end of `fn main()` to try another input.

Expected output

```text
3
112
1
```

## Use Weaver in a project

Extract the starter into a new folder. It contains `main.blyx`, the licensed framework source in `vendor/weaver`, and a VS Code task. With the Blyx 0.2.1 compiler and host toolchain installed, run `blyxc native-run main.blyx` from that folder. Type `blyx-weaver-` in a Blyx file to see the framework completions. [Download the starter ZIP](https://github.com/Rahulchaube1/blyxxxx/releases/download/framework-editors-v0.1.0/blyx-weaver-starter-0.1.0.zip)

[API and input requirements](https://www.blyx-lang.space/packages/weaver) · [Framework source](https://github.com/Rahulchaube1/blyx-weaver/tree/660e7fe3dbf52f721675812af5d7b4730c3044c4) · [Report an issue](https://github.com/Rahulchaube1/blyx-weaver/issues)

[GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) · [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube)
