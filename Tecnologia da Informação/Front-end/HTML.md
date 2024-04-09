# HTML: HyperText Markup Language

## Semantic HTML Example

### Header

```html
<header>
  <h1>Super duper best blog ever</h1>
  <nav>
    <a href="/">Home</a>
    <a href="/about">About</a>
    <a href="/archive">Archive</a>
  </nav>
</header>
```

### Main Content

```html
<main>
  <article>
    <header>
      <h1>Why you should buy more cheeses than you currently do</h1>
    </header>
    <section>
      <header>
        <h2>Part 1: Variety is spicy</h2>
      </header>
      <!-- cheesy content -->
    </section>
    <section>
      <header>
        <h2>Part 2: Cows are great</h2>
      </header>
      <!-- more cheesy content -->
    </section>
  </article>
</main>
```

### Footer

```html
<footer>
  <section class="contact" vocab="http://schema.org/" typeof="LocalBusiness">
    <h2>Contact us!</h2>
    <address property="email">
      <a href="mailto:us@example.com">us@example.com</a>
    </address>
    <address property="address" typeof="PostalAddress">
      <p property="streetAddress">123 Main St., Suite 404</p>
      <p>
        <span property="addressLocality">Yourtown</span>,
        <span property="addressRegion">AK</span>,
        <span property="postalCode">12345</span>
      </p>
      <p property="addressCountry">United States of America</p>
    </address>
  </section>
</footer>
```

### Other Semantic Elements

```html
<!-- conteúdo que é periférico, e pode ser considerado separado do conteúdo principal -->
<aside></aside>

<!-- Representa uma seção de texto que foi citada de outra fonte. -->
<blockquote>
  <p>This is a quoted text from another source.</p>
</blockquote>

<!-- Citar o título de uma obra, como um livro, filme, música, etc. -->
<cite>Author Name, Book Title</cite>

<!-- Indica que o texto dentro dele é um trecho de código. -->
<code></code>

<!-- for code block formatting -->
<data></data>
<del></del>
<figure></figure>
<ins></ins>
<time></time>
<var></var>
```

## Forms

### Input

Types

- button
- checkbox
- color
- date
- datetime-local
- email
- file
- hidden
  - It is not displayed but whose value is submitted to the server.
- image
- month
- number
- password
- radio
- range
- reset
- search
- submit
- tel
- text
- time
- url
- week
- datetime (obsoleto)
