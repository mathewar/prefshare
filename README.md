# PrefShare

PrefShare is a simple, privacy-focused web application that allows users to select and share their personal preferences across various categories. The primary goal is to provide an easy way for users to communicate their likes and dislikes with others through a single, shareable link.

**All user data is encoded directly into the URL, meaning no information is ever saved or stored on any server, ensuring complete user privacy.**

[Try it out here]([https://your-live-demo-link-here](https://mathewar.github.io/prefshare))

![PrefShare Screenshot]() <!-- Optional: Add a screenshot of the app -->

## ✨ Features

- **100% Private:** No databases, no servers, no tracking. All preference data is stored in the URL.
- **Instant Sharing:** Get a unique, shareable link that reflects your choices in real-time.
- **Dynamic & Customizable:** Load your own set of preferences from any publicly accessible JSON file using a URL parameter.
- **Image Export:** Download a PNG image of your preferences to share on platforms that don't support long links.
- **Simple UI:** Clean, responsive, and easy-to-use interface built with Tailwind CSS.
- **Trivial Compression:** The preference data in the URL is compressed to keep links as short as possible.

## 🚀 How to Use

1.  **Enter Your Name:** Optionally, enter your name at the top. This will be included in the shared link and the downloaded image filename.
2.  **Select Preferences:** For each item, choose one of the five options: "N/A", "No", "Maybe", "Yes", or "Favorite".
3.  **Share Your Link:** Click the "Share Link" button to copy the unique URL to your clipboard.
4.  **Download Image:** Click the "Download" button to save a PNG image of your selections.
5.  **Reset:** Click "Reset" to clear all selections and start over.

## 🔧 Using a Custom Configuration

PrefShare can load a custom set of categories and questions from an external JSON file. This is perfect for creating your own tailored preference sheets.

1.  **Create a `preferences.json` file:**
    The file must be an array of objects, where each object represents a category. The structure should be:
    ```json
    [
      {
        "category": "Your Category Name",
        "icon": "lucide-icon-name",
        "questions": [
          "Question 1",
          "Question 2",
          "Question 3"
        ]
      },
      {
        "category": "Another Category",
        "icon": "settings",
        "questions": [
          "Item A",
          "Item B"
        ]
      }
    ]
    ```
    *You can find a list of valid icon names on the [Lucide Icons](https://lucide.dev/) website.*

2.  **Host the JSON file online:**
    For this to work, the file needs to be publicly accessible and served with the correct CORS headers (`Access-Control-Allow-Origin: *`). The easiest way to do this is with a **public GitHub Gist**:
    - Go to [gist.github.com](https://gist.github.com).
    - Paste your JSON content into the Gist.
    - Give it a filename like `preferences.json`.
    - Click "Create public gist".
    - On the next page, click the **"Raw"** button to view the raw file.

3.  **Construct the URL:**
    Copy the URL from the "Raw" view. It will look something like `https://gist.githubusercontent.com/YourUsername/.../raw/.../preferences.json`.

4.  **Use the `config` parameter:**
    Append this raw URL to the PrefShare application URL using the `?config=` query parameter.

    **Example:**
    `https://your-prefshare-url/index.html?config=https://gist.githubusercontent.com/YourUsername/.../raw/.../preferences.json`

The application will now load your custom preferences instead of the default set.

## 💻 Tech Stack

- **HTML5**
- **Tailwind CSS:** For all styling.
- **jQuery:** For DOM manipulation and event handling.
- **Lucide Icons:** For a clean and consistent icon set.
- **html2canvas:** To enable the image download functionality.

## 🔒 Privacy

This application was built with privacy as a core principle.
- No cookies are used.
- No analytics are collected.
- No data is ever sent to or stored on a server.
- The entire state of the application is contained within the URL you see in your browser's address bar.
