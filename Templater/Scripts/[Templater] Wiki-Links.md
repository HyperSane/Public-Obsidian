# Delete these lines that have hash-tags for script to work.
# This script makes a selected link convert from universal-MarkDown to Wiki links ( "[[The note]]" ).
# This allows having embedded links into notes, previewing the note without leaving (using a drop-down method).

<%*
const originalLink = tp.file.selection(); // Get the selected text
if (!originalLink) {
    tR += "No text selected!"; // If nothing is selected, output a message
    return;
}

// Extract the URL from the Markdown link (standard format: [text](url))
const regex = /\[.*?\]\((.*?)\)/; // Regex to capture the link URL inside ( )
const match = originalLink.match(regex);

if (match) {
    let filePath = match[1]; // The actual URL or path from the Markdown link
    filePath = decodeURIComponent(filePath); // Decode '%20' and other URL encoding
    const convertedLink = `[[${filePath}\\|display name here]]`; // Escape | for table compatibility
    tR += convertedLink; // Output the result
} else {
    tR += "Invalid link format! Make sure it's a Markdown link like [text](url)."; // Handle invalid input
}
%>
