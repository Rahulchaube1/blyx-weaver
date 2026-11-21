## Lay out and hit-test five tiles

Use integer logical pixels. Width, inset, gap, minimum width and row height support values up to 1,000,000. The column limit is 1–10,000, and a grid can address 1,000,000 items. Invalid geometry produces an empty rectangle or a missed hit. Right and bottom edges are exclusive. A narrow positive content area uses one column.

1. Open an empty file named `weaver-demo.blyx`.
2. Type `blyx-weaver-demo` and select **Weaver — runnable example**. You can also use **Snippets: Fill File with Snippet**.
3. Choose **Blyx: Run File** from the command palette. Change an argument near the end of `fn main()` to try another input.

Expected output

```text
3
112
1
```

[Work through the example in the browser](https://www.blyx-lang.space/play?example=package-weaver)
