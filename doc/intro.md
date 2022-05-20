# Set of technology updates and tips

All this is build using mdbook.

```shell
mdbook serve --open
```

mdBook is a command line tool to create books with Markdown. It is ideal for creating product or API documentation, tutorials, course materials or anything that requires a clean, easily navigable and customizable presentation.

- Lightweight Markdown syntax helps you focus more on your content
- Integrated search support
- Color syntax highlighting for code blocks for many different languages
- Theme files allow customizing the formatting of the output
- Preprocessors can provide extensions for custom syntax and modifying content
- Backends can render the output to multiple formats
- Written in Rust for speed, safety, and simplicity
- Automated testing of Rust code samples

<https://rust-lang.github.io/mdBook/>

And small tip - math is build using mathjax:

\\( \int x dx = \frac{x^2}{2} + C \\)

centered:

\\[ \mu = \frac{1}{N} \sum_{i=0} x_i \\]


And can have editable /runnable rust:

```rust,editable
fn main() {
    let number = 5;
    print!("{}", number);
}
```


Also some graphs from mermaid:
```mermaid
graph TD;
A-->B;
A-->C;
B-->D;
C-->D;
```


```admonish warning
A beautifully styled message.
```

```admonish warning "Data loss"
The following steps can lead to irrecoverable data corruption.
```

~~~admonish bug
This syntax won't work in Python 3:
```python
print "Hello, world!"
```
~~~

More: <https://rust-lang.github.io/mdBook/format/mdbook.html>


