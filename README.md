<img src="assets/logo.png" width="112" height="112" alt="Weaver bird logo">

# Blyx Weaver

Lay out equal-width tiles on small or large viewports, distribute leftover pixels and map pointer coordinates back to an item.

A grid can draw a tile in one place and dispatch a click to its neighbor if painting and input code round dimensions differently. CSS Grid describes how tracks and gaps form a layout. Weaver uses one integer track calculation for both drawing and input. [W3C, CSS Grid Layout Module Level 1](https://www.w3.org/TR/css-grid-1/#grid-tracks)

## Install and run

Install the Blyx 0.2.1 compiler and a Rust toolchain with a host linker. Clone the versioned release, then run its small example and regression suite.

```sh
cargo install --locked --version 0.2.1 blyxc
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-weaver.git
cd blyx-weaver
blyxc native-run example.blyx
blyxc native-run tests.blyx
```

Expected output from the small example

```text
3
112
1
```

## Render a file chooser as SVG

The example draws five file tiles in three columns. The final row has two items. Use the same geometry for touch or mouse hit testing when embedding the layout in a UI host.

```sh
blyxc native-run project.blyx
```

Run `blyxc native-run project.blyx > chooser.svg` and open the result in a browser. Your application supplies the window, painting and input events.

View the generated [chooser.svg](https://www.blyx-lang.space/framework-examples/chooser.svg).

[Run the portable example in the browser](https://www.blyx-lang.space/play?example=package-weaver) · [Follow the handbook exercise](https://doc.blyx-lang.space/guide/weaver) · [Download the release](https://github.com/Rahulchaube1/blyx-weaver/releases/tag/v0.1.0)

## Use the framework in your own project

From the folder containing your entry file, clone the release into `vendor/weaver`.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-weaver.git vendor/weaver
```

```blyx
use vendor::weaver::weaver;

fn main() {
    let columns = we_columns(320, 8, 8, 80, 6);
    let second = we_rect(320, 8, 8, columns, 48, 1);
    println!(columns);
    println!(at(second, 0));
    println!(we_hit(320, 8, 8, columns, 48, 5, 113, 19));
}
```

Run `blyxc native-run main.blyx`.

Use integer logical pixels. Width, inset, gap, minimum width and row height support values up to 1,000,000. The column limit is 1–10,000, and a grid can address 1,000,000 items. Invalid geometry produces an empty rectangle or a missed hit. Right and bottom edges are exclusive. A narrow positive content area uses one column.

| API | Behavior |
| --- | --- |
| `we_columns(width, inset, gap, minimum, limit)` | Choose a responsive column count; zero indicates an empty or invalid content area. |
| `we_rect(width, inset, gap, columns, rowHeight, index)` | Return [x, y, width, height] in logical pixels. |
| `we_hit(width, inset, gap, columns, rowHeight, count, x, y)` | Find the item under a pointer. Gutters, empty cells and outside positions return −1. |

## Contribute

When opening an issue, include the smallest reproducing Blyx input, the compiler version and the output you expected. [Source and issues](https://github.com/Rahulchaube1/blyx-weaver/issues) · [Blyx community](https://www.blyx-lang.space/community)

Dual-licensed under [MIT](LICENSE-MIT) or [Apache-2.0](LICENSE-APACHE).

## Connect with Rahul Chaube

[Portfolio](https://www.rahulchaube1.com/) · [GitHub](https://github.com/Rahulchaube1) · [LinkedIn](https://www.linkedin.com/in/rahulchaube1) · [Hugging Face](https://huggingface.co/oncody) · [X](https://x.com/RahulChaube_) · [EverestQ](https://www.everestqai.com/) · [Contact](https://www.rahulchaube1.com/contact)

[Blyx website](https://www.blyx-lang.space/) · [BlyxTorch](https://www.blyx-lang.space/packages/blyxtorch) · [Handbook](https://doc.blyx-lang.space/) · [Community](https://www.blyx-lang.space/community)

Support Rahul’s open-source work through [GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) or [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube).
