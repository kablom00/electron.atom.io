---
version: v1.4.12
category: API
redirect_from:
  - /docs/v0.37.8/api/file-object
  - /docs/v0.37.7/api/file-object
  - /docs/v0.37.6/api/file-object
  - /docs/v0.37.5/api/file-object
  - /docs/v0.37.4/api/file-object
  - /docs/v0.37.3/api/file-object
  - /docs/v0.36.12/api/file-object
  - /docs/v0.37.1/api/file-object
  - /docs/v0.37.0/api/file-object
  - /docs/v0.36.11/api/file-object
  - /docs/v0.36.10/api/file-object
  - /docs/v0.36.9/api/file-object
  - /docs/v0.36.8/api/file-object
  - /docs/v0.36.7/api/file-object
  - /docs/v0.36.6/api/file-object
  - /docs/v0.36.5/api/file-object
  - /docs/v0.36.4/api/file-object
  - /docs/v0.36.3/api/file-object
  - /docs/v0.35.5/api/file-object
  - /docs/v0.36.2/api/file-object
  - /docs/v0.36.0/api/file-object
  - /docs/v0.35.4/api/file-object
  - /docs/v0.35.3/api/file-object
  - /docs/v0.35.2/api/file-object
  - /docs/v0.34.4/api/file-object
  - /docs/v0.35.1/api/file-object
  - /docs/v0.34.3/api/file-object
  - /docs/v0.34.2/api/file-object
  - /docs/v0.34.1/api/file-object
  - /docs/v0.34.0/api/file-object
  - /docs/v0.33.9/api/file-object
  - /docs/v0.33.8/api/file-object
  - /docs/v0.33.7/api/file-object
  - /docs/v0.33.6/api/file-object
  - /docs/v0.33.4/api/file-object
  - /docs/v0.33.3/api/file-object
  - /docs/v0.33.2/api/file-object
  - /docs/v0.33.1/api/file-object
  - /docs/v0.33.0/api/file-object
  - /docs/v0.32.3/api/file-object
  - /docs/v0.32.2/api/file-object
  - /docs/v0.31.2/api/file-object
  - /docs/v0.31.0/api/file-object
  - /docs/v0.30.4/api/file-object
  - /docs/v0.29.2/api/file-object
  - /docs/v0.29.1/api/file-object
  - /docs/v0.28.3/api/file-object
  - /docs/v0.28.2/api/file-object
  - /docs/v0.28.1/api/file-object
  - /docs/v0.28.0/api/file-object
  - /docs/v0.27.3/api/file-object
  - /docs/v0.27.2/api/file-object
  - /docs/v0.27.1/api/file-object
  - /docs/v0.27.0/api/file-object
  - /docs/v0.26.1/api/file-object
  - /docs/v0.26.0/api/file-object
  - /docs/v0.25.3/api/file-object
  - /docs/v0.25.2/api/file-object
  - /docs/v0.25.1/api/file-object
  - /docs/v0.25.0/api/file-object
  - /docs/v0.24.0/api/file-object
  - /docs/v0.23.0/api/file-object
  - /docs/v0.22.3/api/file-object
  - /docs/v0.22.2/api/file-object
  - /docs/v0.22.1/api/file-object
  - /docs/v0.21.3/api/file-object
  - /docs/v0.21.2/api/file-object
  - /docs/v0.21.1/api/file-object
  - /docs/v0.21.0/api/file-object
  - /docs/v0.20.8/api/file-object
  - /docs/v0.20.7/api/file-object
  - /docs/v0.20.6/api/file-object
  - /docs/v0.20.5/api/file-object
  - /docs/v0.20.4/api/file-object
  - /docs/v0.20.3/api/file-object
  - /docs/v0.20.2/api/file-object
  - /docs/v0.20.1/api/file-object
  - /docs/v0.20.0/api/file-object
  - /docs/vlatest/api/file-object
source_url: 'https://github.com/electron/electron/blob/master/docs/api/file-object.md'
title: File Object
excerpt: 'Use the HTML5 <code>File</code> API to work natively with files on the filesystem.'
sort_title: file-object
---
# `File` Object

> Use the HTML5 `File` API to work natively with files on the filesystem.

The DOM's File interface provides abstraction around native files in order to let users work on native files directly with the HTML5 file API. Electron has added a `path` attribute to the `File` interface which exposes the file's real path on filesystem.

Example of getting a real path from a dragged-onto-the-app file:

    <div id="holder">
      Drag your file here
    </div>

    <script>
      const holder = document.getElementById('holder')
      holder.ondragover = () => {
        return false;
      }
      holder.ondragleave = holder.ondragend = () => {
        return false;
      }
      holder.ondrop = (e) => {
        e.preventDefault()
        for (let f of e.dataTransfer.files) {
          console.log('File(s) you dragged here: ', f.path)
        }
        return false;
      }
    </script>
