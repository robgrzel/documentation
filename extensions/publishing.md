Once you've crafted the code for your extension, you'll need to create a JSON description of your package, so that it can be imported using the Extension manager.

The JSON description must be hosted on a URL the app can reach out to. In these steps, we'll use Listed to generate a JSON endpoint.

### Steps:

1. Create a new note in Standard Notes called "my-extension.json", and enter the following as its contents:

```
---
metatype: json
---

{
        "identifier": "org.yourdomain.my-markdown-editor",
        "name": "My Markdown Editor",
        "content_type": "SN|Component",
        "area": "editor-editor",
        "version": "1.0.0",
        "description": "A fully featured Markdown editor that supports live preview, a styling toolbar, and split pane support.",
        "url": "https://listed.standardnotes.org/my-extension-json-link",
        "download_url": "https://github.com/sn-extensions/advanced-markdown-editor/archive/1.0.184.zip",
	"latest_url": "https://listed.standardnotes.org/my-extension-json-link",
        "marketing_url": "https://standardnotes.org/extensions/advanced-markdown",
        "thumbnail_url": "https://domain.org/editors/adv-markdown.jpg"
}
```

2. Head over to listed.standardnotes.org, and generate an account by clicking "Generate Author Link". Copy that link, then, in the Extensions menu in Standard Notes, click "Import Extension" in the bottom right corner. Paste in your link, and press enter, then accept.

3. Back in your "my-extension.json" note, click "Actions" in the menu bar below the note title, then click "Publish to Private Link". Click "Open Private Link" to preview your JSON endpoint.

4. In the Extensions window, click "Import Extension", and paste in your JSON endpoint, press Enter, then accept to install your extension.

### Local Installation
Extensions in Standard Notes desktop support local installation. We recommend using GitHub releases to host your download file.

1. In your extension repository on GitHub, go to the Releases tab, then click "Draft New Release".

2. Click "Publish release" (you don't need to enter any information). Standard Notes will use the auto-generated "Source code (zip)" archive that GitHub generates.

3. Right click on "Source code (zip)", then choose the option to Copy Link Address. Use this value for `download_url` in your JSON contents.

By default, Standard Notes will look for the `index.html` file located in the root of the project. If your main file is not in the root, you can specify a custom path.

**To specify the root file of your extension:**

1. In your extension's repository, create a file called `package.json` if it does not already exist.

2. Add the following entry anywhere in the root level of `package.json`:

```
...
  "sn": {
    "main": "relative/path/to/index.html"
  },
...
```

`main` can also be a CSS file if you're publishing a theme.

### Autoupdate

Standard Notes will ping the `latest_url`endpoint automatically to update extensions. For this value, you can use the same JSON endpoint you're using for `url` (your `my-extension.json` endpoint).

### Questions?

Join the [Slack group](https://standardnotes.org/slack) and ask away in the #dev channel.