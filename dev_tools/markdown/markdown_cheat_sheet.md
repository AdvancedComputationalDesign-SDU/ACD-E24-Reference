# Markdown Cheat Sheet

This cheat sheet provides a quick reference to Markdown syntax with examples to help you format your documentation effectively.

---

## Headings

Use `#` symbols to create headings. The number of `#` corresponds to the heading level.

```markdown
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
```

## Emphasis

- **Bold**

  ```markdown
  **This text is bold**
  ```

- *Italic*

  ```markdown
  *This text is italic*
  ```

- ***Bold and Italic***

  ```markdown
  ***This text is bold and italic***
  ```

## Lists

- **Unordered List**

  ```markdown
  - Item 1
  - Item 2
    - Subitem 2a
    - Subitem 2b
  ```

- **Ordered List**

  ```markdown
  1. First item
  2. Second item
     1. Subitem 2a
     2. Subitem 2b
  ```

## Links

- **Inline Link**

  ```markdown
  [Link Text](https://www.example.com)
  ```

- **Reference Link**

  ```markdown
  [Link Text][1]

  [1]: https://www.example.com
  ```

## Images

- **Embedding an Image**

  ```markdown
  ![Alt Text](path/to/image.png "Optional Title")
  ```

  Example:

  ```markdown
  ![Generated Pattern](../images/pattern_example1.png "Pattern Example 1")
  ```

## Code Blocks

- **Inline Code**

  ```markdown
  Use the `print()` function to display output.
  ```

- **Fenced Code Block**

  ```python
  import numpy as np
  array = np.zeros((100, 100, 3))
  ```

- **Indented Code Block**

  ```markdown
      This is an indented code block.
  ```

## Blockquotes

```markdown
> This is a blockquote.
>
> It can span multiple lines.
```

## Horizontal Rule

```markdown
---

```

## Tables

```markdown
| Column 1 | Column 2 | Column 3 |
| -------- | -------- | -------- |
| Data 1   | Data 2   | Data 3   |
| Data 4   | Data 5   | Data 6   |
```

## Task Lists

```markdown
- [x] Task 1
- [ ] Task 2
- [ ] Task 3
```

## Footnotes

```markdown
Here's a sentence with a footnote.[^1]

[^1]: This is the footnote.
```

## Strikethrough

```markdown
~~This text is crossed out.~~
```

---

## Examples

### Including an Image in Your Documentation

To include an image from your `images` folder:

```markdown
![Pattern Example](../images/pattern_example1.png "Generated Pattern")
```

### Creating a Table to Summarize Results

```markdown
| Method            | Description                               |
| ----------------- | ----------------------------------------- |
| `np.zeros()`      | Creates an array filled with zeros        |
| `np.random.rand()`| Generates random numbers between 0 and 1  |
```

---

## Tips

- **Preview Your Markdown**: Use a Markdown editor or GitHub's preview feature to check your formatting.
- **Keep It Simple**: Clarity is more important than complex formatting.
- **Use Headings**: Organize your document with headings for easy navigation.

---

## Resources

- [Mastering Markdown on GitHub](https://guides.github.com/features/mastering-markdown/)
- [Markdown Guide](https://www.markdownguide.org/)

---

*By using Markdown effectively, you can create professional and easy-to-read documentation for your projects.*

---