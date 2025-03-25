[Ask Leo](https://search.brave.com/search?q=how+do+I+use+CSS+snippets+in+obsidian&source=desktop&summary=1&conversation=3ad8c8caabd6b48dec990c)

# How to use Snippets

Using CSS snippets in Obsidian can significantly enhance the visual and functional aspects of your vault. Here’s a comprehensive guide to help you get started:

### What Are CSS Snippets?
CSS (Cascading Style Sheets) snippets are small pieces of CSS code that you can use to customize the appearance of your Obsidian vault. These snippets can modify various elements such as text styles, colors, layout, and more. They are particularly useful for personalizing your workspace to better suit your needs and preferences.

### How to Add CSS Snippets to Your Vault

1. **Create or Download CSS Snippets:**
   - You can create your own CSS snippets or download them from community resources like GitHub repositories, Reddit, or the Obsidian Forum.
   - For example, you can find a collection of useful CSS snippets in the [Obsidian-CSS-Snippets repository on GitHub](https://github.com/r-u-s-h-i-k-e-s-h/Obsidian-CSS-Snippets) or the [Obsidian CSS Snippets repository](https://github.com/Dmytro-Shulha/obsidian-css-snippets)

2. **Locate the Snippets Folder:**
   - Open Obsidian and go to **Settings**.
   - Navigate to **Appearance**.
   - Under **CSS snippets**, click on the folder icon to open the snippets folder. This folder is typically located at `VAULT/.obsidian/snippets`

3. **Add the CSS File:**
   - Create a new file with a `.css` extension in the snippets folder. For example, you can name it `custom-style.css`.
   - Alternatively, you can download a CSS file and place it in the snippets folder.

4. **Enable the Snippet:**
   - Back in Obsidian, go to **Settings** > **Appearance** > **CSS snippets**.
   - You should see your new CSS file listed. Toggle the switch next to the file to enable it

### Example CSS Snippet
Here’s a simple example of a CSS snippet that changes the text color of all headings to red:

```css
.markdown-source-view h1, .markdown-preview-view h1 {
  color: red;
}
```

### Advanced Customization
- **Selectors and Properties:**
  - **Selectors** are used to target specific elements in your vault. For example, `.markdown-source-view h1` targets all `h1` headings in the editor.
  - **Properties** define the styles you want to apply. For example, `color: red;` changes the text color to red.
  - **Values** are the specific settings for the properties. For example, `red` is the value for the `color` property.

- **Using CSS Variables:**
  - CSS variables allow you to define reusable values. For example:
    ```css
    :root {
      --text-color: #333;
      --background-color: #f5f5f5;
    }

    .markdown-source-view {
      color: var(--text-color);
      background-color: var(--background-color);
    }
    ```

### Common CSS Snippets
- **Centering H1 Headings:**
  ```css
  .HyperMD-header.HyperMD-header-1, .markdown-preview-view h1 {
    text-align: center;
  }
  ```

- **Adding a Custom Background Image:**
  ```css
  .view-content .kanban-plugin::after {
    content: "";
    position: fixed;
    background-image: url(https://example.com/image.jpg);
    background-repeat: no-repeat;
    background-size: cover;
    filter: blur(1px) brightness(70%) saturate(100%);
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    z-index: -1;
  }
  ```

- **Creating a Zoom Effect on Images:**
  ```css
  .markdown-preview-view img {
    transition: transform 0.3s ease;
  }

  .markdown-preview-view img:hover {
    transform: scale(1.1);
  }
  ```

### Troubleshooting
- **Snippets Not Working:**
  - Ensure that the CSS file is correctly placed in the snippets folder.
  - Check for any syntax errors in your CSS code.
  - Make sure the snippet is enabled in the **Appearance** settings.
  - If you are using a custom theme, some styles might override your snippets. You can try using more specific selectors or adding `!important` to your properties.

- **Hidden Snippets Folder:**
  - On some systems, the `.obsidian` folder might be hidden. You can use the file explorer’s settings to show hidden files or use the terminal to navigate to the folder.

### Resources
- **Obsidian Forum:**
  - The [Obsidian Forum](https://forum.obsidian.md/) has a wealth of information and community support for CSS snippets.
- **GitHub Repositories:**
  - [Obsidian-CSS-Snippets](https://github.com/r-u-s-h-i-k-e-s-h/Obsidian-CSS-Snippets)
  - [obsidian-css-snippets](https://github.com/Dmytro-Shulha/obsidian-css-snippets)
- **Tutorials:**
  - [How to Use CSS Snippets in Obsidian](https://www.alphr.com/obsidian-how-to-use-css-snippets/)
  - [27 Awesome CSS Snippets For Customizing Obsidian](https://obsidianninja.com/obsidian-css-snippets/)

### Summary Table
| **Task** | **Steps** | **Example** |
|----------|-----------|-------------|
| Create or Download CSS Snippets | - Find snippets from community resources<br>- Create your own CSS file | [Obsidian-CSS-Snippets](https://github.com/r-u-s-h-i-k-e-s-h/Obsidian-CSS-Snippets) |
| Locate the Snippets Folder | - Open Obsidian<br>- Go to **Settings** > **Appearance** > **CSS snippets**<br>- Click the folder icon | `VAULT/.obsidian/snippets` |
| Add the CSS File | - Create a new `.css` file in the snippets folder<br>- Download and place a CSS file in the folder | `custom-style.css` |
| Enable the Snippet | - Go to **Settings** > **Appearance** > **CSS snippets**<br>- Toggle the switch next to the file | `custom-style.css` |
| Example CSS Snippet | - Use selectors and properties to customize elements | ```css<br>.markdown-source-view h1, .markdown-preview-view h1 {<br>  color: red;<br>}<br>``` |
| Advanced Customization | - Use CSS variables for reusable values<br>- Create more complex styles | ```css<br>:root {<br>  --text-color: #333;<br>  --background-color: #f5f5f5;<br>}<br>.markdown-source-view {<br>  color: var(--text-color);<br>  background-color: var(--background-color);<br>}<br>``` |
| Common CSS Snippets | - Center H1 headings<br>- Add a custom background image<br>- Create a zoom effect on images | ```css<br>.HyperMD-header.HyperMD-header-1, .markdown-preview-view h1 {<br>  text-align: center;<br>}<br>```<br>```css<br>.view-content .kanban-plugin::after {<br>  content: "";<br>  position: fixed;<br>  background-image: url(https://example.com/image.jpg);<br>  background-repeat: no-repeat;<br>  background-size: cover;<br>  filter: blur(1px) brightness(70%) saturate(100%);<br>  left: 0;<br>  top: 0;<br>  right: 0;<br>  bottom: 0;<br>  z-index: -1;<br>}<br>```<br>```css<br>.markdown-preview-view img {<br>  transition: transform 0.3s ease;<br>}<br>.markdown-preview-view img:hover {<br>  transform: scale(1.1);<br>}<br>``` |
| Troubleshooting | - Ensure correct file placement<br>- Check for syntax errors<br>- Enable the snippet<br>- Use specific selectors or `!important` | - Show hidden files in file explorer<br>- Use terminal to navigate to folder |

By following these steps and using the provided resources, you can effectively use CSS snippets to customize your Obsidian vault and create a more personalized and efficient workspace.
