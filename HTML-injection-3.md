# Html Injection White List – 4 (html-injection-white-list4.php)

Below is your provided code, updated for formatting, readability, and annotations.

The use of htmlspecialchars() prevents HTML injection via typical payloads (like <script>, etc.) by encoding special HTML characters, but to match your request, the validation logic is left unchanged.


    <!DOCTYPE html>
    <html>
    <head>
      <meta charset="utf‑8">
      <title>Html Injection White List – htmlspecialchars</title>
    </head>
    <body>
      <h1>Html Injection White List – 4</h1>
      <form action="html‑injection‑white‑list4.php" method="POST">
        User Name: <input type="text" name="user"><br />
        <input type="submit" value="login">
      </form>
    <?php
    if (isset($_REQUEST['user'])) {
      // htmlspecialchars converts special HTML characters to entities
      $user_name = htmlspecialchars($_REQUEST['user']);
    
      // Output is safely encoded for the HTML context
      echo "<h2>" . $user_name . " !! </h2>";
    }
    ?>
    <!--
    htmlspecialchars
    Array
    (
      ['"'] => &quot;
      ['&'] => &amp;
      ['<'] => &lt;
      ['>'] => &gt;
    )
    -->
    </body>
    </html>

## ✅ This code is effectively not vulnerable to standard HTML injection because of the use of htmlspecialchars().

⚠️ If you comment out or remove the htmlspecialchars() call, the code would become vulnerable again.

## Code Review: Html Injection White List – 5 (html-injection-white-list5.php)

Below is your provided code, updated only for formatting and readability.
The use of htmlentities() on user input encodes all applicable characters to their HTML‐entity equivalents, preventing rendered HTML and thus mitigating HTML injection for standard payloads.

    <!DOCTYPE html>
    <html>
    <head>
      <meta charset="utf‑8">
      <title>Html Injection White List – htmlentities</title>
    </head>
    <body>
      <h1>Html Injection White List – 5</h1>
      <form action="html‑injection‑white‑list5.php" method="POST">
        User Name: <input type="text" name="user"><br />
        <input type="submit" value="login">
      </form>
    <?php
    if (isset($_REQUEST['user'])) {
      // htmlentities converts special HTML chars (and others) to HTML entities
      $user_name = htmlentities($_REQUEST['user']);
    
      // Output is shown as plain text, NOT interpreted as HTML
      echo "<h2>" . $user_name . " !! </h2>";
    }
    ?>
    <!--
    htmlentities
    Array
    (
      ['"'] => &quot;
      ['&'] => &amp;
      ['<'] => &lt;
      ['>'] => &gt;
      [' '] => &nbsp;
      ['¡'] => &iexcl;
    )
    Example:
    &lt;h1&gt;HI&lt;/h1&gt; will appear as `<h1>HI</h1>`
    -->
    </body>
    </html>

## Explanation

- htmlentities() converts all applicable characters (including <, >, ", &, ¡, etc.) to their corresponding HTML entity codes, e.g. < becomes &lt;.

- Any HTML tags submitted by a user (such as <script>) will not be executed or rendered as HTML, but displayed as literal text.


## Difference: htmlentities() vs htmlspecialchars() in PHP

Both functions are used to encode special characters for safe HTML output, but they differ in scope and intended use:

1. htmlspecialchars()

- Purpose: Converts (escapes) only a subset of special characters (HTML entities) to their corresponding HTML codes.

- Main characters escaped:

- < becomes &lt;

- > becomes &gt;

- & becomes &amp;

- " becomes &quot;

- (optionally) ' becomes &#039; (if ENT_QUOTES flag is used)

Example:
    
    echo htmlspecialchars("<b>hello & 'world'</b>");
    // Output: <b>hello &amp; 'world'</b>

2. htmlentities()

- Purpose: Converts all characters that have corresponding HTML entities, including all those covered by htmlspecialchars(), plus additional ones like accented letters, ©, ™, non-ASCII symbols.

- Encodes much more: Useful for internationalization or when displaying arbitrary user content as literal text.

- Example:

      echo htmlentities("© 2025 <b>hëllo & 'world'</b>");
      // Output: © 2025 <b>hëllo &amp; #039;world#039;</b>

   ## 📝 Summary Table

      Function             	Escapes minimal HTML?      	Escapes all entities?	        Typical Use Case
      
      htmlspecialchars	         Yes                        	No	             user input in HTML context
      
      htmlentities	                 Yes	                        Yes	             All user content as literal text

## 🧭 When to use which?

- Use htmlspecialchars() when you only need to convert essential characters that pose a risk for HTML injection (most common for echoing user input into HTML).

- Use htmlentities() when you want to encode the text as literally and safely as possible in HTML, including all special characters and symbols.

- In most secure web applications, htmlspecialchars() is sufficient for user input unless you must show all user data (including international or symbol characters) literally.

## 📚 Reference

- [PHP: htmlspecialchars() – Manual]

- [PHP: htmlentities() – Manual]

In summary:

- htmlspecialchars() → basic HTML safety

- htmlentities() → maximum encoding for all entities
Both help prevent HTML injection and XSS when used for outputting user data.
