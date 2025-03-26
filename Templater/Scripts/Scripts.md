[See for how to run Templater Scripts](https://github.com/HyperSane/Public-Obsidian/blob/main/Templater/Templater.md)

# Templater Scripts Basic Guide

Setup Templater in Obsidian

To set up Templater in Obsidian, start by enabling the Templater community plugin. Navigate to Settings > Community Plugins, find Templater by SilentVoid13, and install it. Once installed, enable it by toggling the switch next to it

Next, create a folder in your vault to store your template files. This folder can be named anything you like, but a common choice is "Templates" After creating the folder, you need to configure Templater to point to this folder. Go to Templater settings and set the folder location to the path of your newly created Templates folder

To use Templater, you can either trigger it from the command palette by typing "Templater: Insert Template" or set up a keyboard shortcut for it. To set up a keyboard shortcut, go to Settings > Hotkeys, filter for "Templater", and specify a shortcut for "Templater: Insert Template"

Once configured, you can create templates as regular notes within your Templates folder. These templates can include dynamic content using Templater's syntax, such as variables and functions, to generate content based on the current date, user input, or other data

For example, a simple template might look like this:

```markdown
---
title: Game Title?
date: {{date:YYYY-MM-DD}}
---
```

This template prompts the user for a title and automatically sets the date when the template is used

Remember to keep your templates simple at first and add more complexity as needed

# Templater Full-Guide1


Setting up Templater in Obsidian can significantly enhance your note-taking and productivity. Below is a detailed guide to help you get started:

### Step-by-Step Guide to Setting Up Templater in Obsidian

#### 1. **Install and Enable Templater**
1. **Open Obsidian:**
   - Launch the Obsidian application on your device.

2. **Navigate to Community Plugins:**
   - Go to the settings by clicking on the gear icon in the left sidebar.
   - Scroll down to the "Community plugins" section and click on "Browse."

3. **Search for Templater:**
   - In the search bar, type "Templater" and look for the plugin by SilentVoid.
   - Click on "Install" to download and install the plugin.

4. **Enable Templater:**
   - After installation, return to the "Community plugins" page.
   - Find Templater in the list and enable it by toggling the switch next to it.

#### 2. **Create a Templates Folder**
1. **Create a Folder:**
   - In your Obsidian vault, create a new folder named "Templates" (or any name you prefer).
   - This folder will store all your template files.

2. **Configure Templater:**
   - Go back to the settings and navigate to the "Templater" section.
   - Set the "Template Folder Location" to the folder you just created.

#### 3. **Create Your First Template**
1. **Create a New Note:**
   - Right-click on the "Templates" folder and select "New Note."
   - Name the note something descriptive, like "Daily Note Template."

2. **Add Template Content:**
   - Open the new note and add the content you want to include in your template.
   - For example, a simple daily note template might look like this:
     ```markdown
     ---
     creation date: <% tp.file.creation_date() %>
     modification date: <% tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm:ss") %>
     ---
     << [[<% tp.date.now("YYYY-MM-DD", -1) %\>]] | [[<% tp.date.now("YYYY-MM-DD", 1) %\>]] >>

     # Daily Note for <% tp.file.title %>

     ## Tasks
     - [ ] Task 1
     - [ ] Task 2

     ## Notes
     - Note 1
     - Note 2

     ## Links
     - [[Link to related note]]
     ```

#### 4. **Use Templater in Your Notes**
1. **Insert a Template:**
   - To insert a template into a new note, you can use the command palette.
   - Press `Ctrl + P` (or `Cmd + P` on macOS) to open the command palette.
   - Type "Templater: Insert Template" and select it.
   - Choose the template you created from the list.

2. **Keyboard Shortcut (Optional):**
   - For quicker access, you can set up a keyboard shortcut for inserting templates.
   - Go to settings, then "Hotkeys."
   - Filter for "Templater" and set a shortcut for "Templater: Insert Template."

#### 5. **Advanced Templater Features**
1. **Dynamic Content:**
   - Templater supports dynamic content using JavaScript. For example, you can generate a unique ID for each note:
     ```markdown
     ---
     cuid: newsletter<% tp.file.creation_date("YYYYMMDD-HHmmss") %>
     alias: "Newsletter on <% tp.date.now('MMM Do YYYY') %>"
     dates:
       created: <% tp.file.creation_date("YYYY-MM-DDTHH:mm:ss") %>
     tags: newsletter
     ---
     ```

2. **User Functions:**
   - You can create custom JavaScript functions to use in your templates.
   - Create a folder in your vault for functions, then edit Templater settings to point to it.
   - Create a file like `makeProgressBar.js` and fill it with your function:
     ```javascript
     function makeProgressBar(numerator, denominator, size = 50, filledChar = "█", unFilledChar = "◽", label="") {
         let percentage = numerator / denominator;
         let maxBlocks = size;
         let numFilled = Math.floor(percentage * maxBlocks);
         return `${label}: [${filledChar.repeat(numFilled)}${unFilledChar.repeat(maxBlocks - numFilled)}] ${Math.floor(percentage * 100)}% ( ${numerator}/${denominator} )`;
     }
     module.exports = makeProgressBar;
     ```
   - Restart Obsidian and use the function in your templates:
     ```markdown
     <%* function month() {
         let fileDateNum = fileDate.date();
         let numDays = fileDate.daysInMonth();
         tR += tp.user.makeProgressBar(fileDateNum, numDays, size=numDays, filledChar = "█", unFilledChar = "◽", label="Month");
     }
     month(); %>
     ```

#### 6. **Additional Tips and Resources**
1. **Community Templates:**
   - Explore community templates for inspiration. You can find many examples on the Obsidian forum and GitHub.
   - For instance, the [Obsidian-templater-templates](https://github.com/Mahgozar/Obsidian-templater-templates) repository contains a variety of useful templates.

2. **Documentation:**
   - Refer to the official [Templater documentation](https://silentvoid13.github.io/Templater/) for a comprehensive guide on all available features and functions.

3. **Plugins Integration:**
   - Combine Templater with other plugins like Dataview and Tracker to enhance your note-taking experience.
   - For example, use Dataview to create dynamic summaries and visualizations based on your notes.

### Summary Table
| Step | Action | Description |
|------|--------|-------------|
| 1    | Install Templater | Navigate to Community Plugins, search for Templater, install, and enable it. |
| 2    | Create Templates Folder | Create a folder named "Templates" in your vault and set it as the Template Folder Location in Templater settings. |
| 3    | Create a Template | Create a new note in the Templates folder and add your desired template content. |
| 4    | Insert Template | Use the command palette to insert a template into a new note. Optionally, set a keyboard shortcut for quicker access. |
| 5    | Advanced Features | Utilize dynamic content and custom JavaScript functions to enhance your templates. |
| 6    | Additional Resources | Explore community templates and official documentation for more ideas and detailed guides. |

By following these steps, you should be well on your way to setting up and using Templater in Obsidian effectively. Happy note-taking!
