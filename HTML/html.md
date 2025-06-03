# HTML Notes

## 1. What is HTML?

* HTML = HyperText Markup Language
* It is used to structure a web page.

## 2. Basic Structure of HTML

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <h1>Hello, World!</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
```

## 3. HTML Tags (Elements)

* Tags are written in `< >`
* Most tags have opening & closing: `<p> ... </p>`

## 4. Common HTML Tags

| Tag                    | Use                            |
| ---------------------- | ------------------------------ |
| `<h1>` to `<h6>`       | Headings (biggest to smallest) |
| `<p>`                  | Paragraph                      |
| `<br>`                 | Line Break                     |
| `<hr>`                 | Horizontal Line                |
| `<a href="">`          | Hyperlink                      |
| `<img src="">`         | Image                          |
| `<ul>`, `<ol>`, `<li>` | Lists                          |
| `<div>`                | Division (container)           |
| `<span>`               | Inline container               |

## 5. Text Formatting Tags

| Tag                 | Use              |
| ------------------- | ---------------- |
| `<b>` or `<strong>` | Bold text        |
| `<i>` or `<em>`     | Italic text      |
| `<u>`               | Underline        |
| `<small>`           | Small text       |
| `<mark>`            | Highlighted text |
| `<del>`             | Deleted text     |
| `<ins>`             | Inserted text    |

## 6. Links (Anchor Tag)

```html
<a href="https://example.com" target="_blank">Visit</a>
```

* `href` = URL
* `target="_blank"` = opens in new tab

## 7. Images

```html
<img src="image.jpg" alt="Image description" width="300" height="200">
```

## 8. Lists

**Unordered List:**

```html
<ul>
  <li>Apple</li>
  <li>Banana</li>
</ul>
```

**Ordered List:**

```html
<ol>
  <li>First</li>
  <li>Second</li>
</ol>
```

## 9. Tables

```html
<table border="1">
  <tr>
    <th>Name</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>John</td>
    <td>25</td>
  </tr>
</table>
```

## 10. Forms

```html
<form>
  <label>Name:</label>
  <input type="text" name="name"><br>
  <label>Password:</label>
  <input type="password" name="pass"><br>
  <input type="submit" value="Submit">
</form>
```

## 11. Input Types

* `text`, `password`, `email`, `number`, `checkbox`, `radio`, `submit`, `button`, `date`, `file`

## 12. Semantic Elements

| Tag         | Meaning             |
| ----------- | ------------------- |
| `<header>`  | Top section         |
| `<nav>`     | Navigation links    |
| `<main>`    | Main content        |
| `<section>` | Section of content  |
| `<article>` | Independent content |
| `<aside>`   | Side content        |
| `<footer>`  | Bottom info         |

## 13. Media Tags

```html
<video controls width="300">
  <source src="video.mp4" type="video/mp4">
</video>

<audio controls>
  <source src="audio.mp3" type="audio/mpeg">
</audio>
```

## 14. Iframe (Embed another site)

```html
<iframe src="https://example.com" width="400" height="300"></iframe>
```

## 15. Meta Tags (in `<head>`)

```html
<meta charset="UTF-8">
<meta name="description" content="Free HTML Notes">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

## 16. Inline vs Block Elements

| Inline Elements          | Block Elements         |
| ------------------------ | ---------------------- |
| `<span>`, `<a>`, `<img>` | `<div>`, `<p>`, `<h1>` |

## 17. Comments in HTML

```html
<!-- This is a comment -->
```

## 18. HTML5 Doctype

```html
<!DOCTYPE html>
```

## 19. HTML Entities

* `&nbsp;` = space
* `&lt;` = <
* `&gt;` = >
* `&amp;` = &
* `&quot;` = "
* `&copy;` = ©

## 20. Best Practices

* Always close your tags
* Use lowercase for tags
* Use semantic tags
* Use alt attributes for images
* Keep structure clean and readable

---

# INTERVIEW QUESTIONS

## Basic HTML

1. What is HTML? → HTML stands for HyperText Markup Language.
2. What is the purpose of HTML? → It structures web page content.
3. What does `<!DOCTYPE html>` mean? → It defines the HTML version (HTML5 here).
4. What is a tag in HTML? → A keyword used to define elements, e.g., `<p>`.
5. What is an element? → A complete HTML tag with content.
6. Difference between HTML and HTML5? → HTML5 supports audio, video, and semantic elements.
7. What are void elements? → Elements that don’t have a closing tag, e.g., `<br>`.
8. Is HTML case-sensitive? → No, tags are not case-sensitive.
9. How do you comment in HTML? → `<!-- This is a comment -->`
10. Can we write inline CSS in HTML? → Yes, using the style attribute.

## Common Tags

11. Tag for paragraph? → `<p>`
12. Tag for largest heading? → `<h1>`
13. Tag to insert image? → `<img src="img.jpg" alt="desc">`
14. Tag to create a link? → `<a href="url">Link</a>`
15. Tag to make text bold? → `<b>` or `<strong>`
16. Tag for italic text? → `<i>` or `<em>`
17. Tag to create a line break? → `<br>`
18. Tag for horizontal line? → `<hr>`
19. Tag for creating a table? → `<table>`
20. Tag to add a table row? → `<tr>`

## Lists & Forms

21. Unordered list tag? → `<ul>`
22. Ordered list tag? → `<ol>`
23. List item tag? → `<li>`
24. Form tag? → `<form>`
25. Text input tag? → `<input type="text">`
26. Password input tag? → `<input type="password">`
27. Submit button tag? → `<input type="submit">`
28. Textarea tag? → `<textarea></textarea>`
29. Dropdown/select tag? → `<select><option></option></select>`
30. Checkbox input tag? → `<input type="checkbox">`

## Advanced HTML

31. What is semantic HTML? → Tags that describe meaning, like `<article>`, `<nav>`.
32. What is the use of `<div>`? → A block-level container.
33. What is `<span>`? → An inline container.
34. What is `<iframe>` used for? → Embeds another page in the current page.
35. How to open a link in a new tab? → Add `target="_blank"` in `<a>`.
36. How to add metadata in HTML? → Using `<meta>` tag in `<head>`.
37. What is the `<head>` tag? → Contains meta info like title, links, styles.
38. What is the `<title>` tag? → Sets the browser tab name.
39. What is `<script>` used for? → To add JavaScript to a page.
40. What is the `<style>` tag? → To write internal CSS.

## Multimedia & Entities

41. How to embed a video? → `<video controls><source src="video.mp4"></video>`
42. How to embed audio? → `<audio controls><source src="audio.mp3"></audio>`
43. What is an entity in HTML? → A special character code (e.g., `&lt;` for <)
44. How to add a favicon? → `<link rel="icon" href="favicon.ico">`
45. What is alt in `<img>`? → Describes the image if it can’t load.

## HTML5 Features

46. New form input types in HTML5? → `email`, `date`, `range`, `color`, etc.
47. New semantic tags in HTML5? → `<header>`, `<footer>`, `<section>`, `<article>`
48. What is localStorage? → Stores data in browser permanently.
49. What is sessionStorage? → Stores data until the browser is closed.
50. What tool to validate HTML? → W3C Validator ([https://validator.w3.org](https://validator.w3.org))

