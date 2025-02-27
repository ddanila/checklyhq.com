---
title: E2E Account Settings
subTitle: Modifying account settings with a file upload
date: 2020-07-22
author: Giovanni Rago
githubUser: ragog
tags:
  - e2e
  - file upload
weight: 9
menu:
  learn:
    parent: "E2E examples"
---

Most services allow users to manage their account settings. These oftentimes have far-reaching implications on how the user experiences the platform. Verifying that the account settings can be viewed and modified is key in making sure we are offering a smooth service.

<!-- more -->

## Steps

Account properties to verify can run the gamut from simple text to connected third party services. In this example, we will focus on a popular case: changing a profile image by uploading one of our own.

On our [test site](https://danube-webshop.herokuapp.com/), such a test could look as follows:

{{< tabs "1">}}
{{< tab "Playwright" >}}
```js {hl_lines=["19-22"]}
{{< readfile filename="samples/playwright/file-upload.js" >}}
```
{{< /tab >}}
{{< tab "Puppeteer" >}}
```js {hl_lines=["25-28"]}
{{< readfile filename="samples/puppeteer/file-upload.js" >}}
```
{{< /tab >}}
{{< /tabs >}}

{{< tabs "2">}}
{{< tab "macOS" >}}
```sh
USER_EMAIL=user@email.com USER_PASSWORD=supersecure1 FILE_PATH=file.jpg node file-upload.js
```
{{< /tab >}}
{{< tab "Windows" >}}
```sh
SET USER_EMAIL=user@email.com
SET USER_PASSWORD=supersecure1
SET FILE_PATH=file.jpg
node file-upload.js
```
{{< /tab >}}
{{< /tabs >}}

Here, we are simply checking for a message giving us feedback on the status of the upload. Depending on the website we are testing, it might be possible to also download the profile image afterwards to run a comparison locally for a more robust check.

## Takeaways
1. Use environment variables to inject secrets.
2. Use `uploadFile` (Puppeteer) or `setInputFiles` (Playwright) to upload the file.
3. If possible, download the file from the platform and compare it with the one that was just uploaded.

## Further reading
1. Official documentation on file upload with [Puppeteer](https://pptr.dev/#?product=Puppeteer&version=v10.2.0&show=api-elementhandleuploadfilefilepaths) and [Playwright](https://playwright.dev/docs/input#upload-files).
