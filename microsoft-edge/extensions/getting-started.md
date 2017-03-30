---
description: Get an end to end overview of the journey from beginning development to packaging of Edge extensions.
title: Extensions - Getting started
author: abbycar
ms.author: abigailc
ms.date: 03/02/2017
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, css, javascript, developer, extensions
---

# Getting started with extensions

Whether you're a new developer wanting to familiarize yourself with extensions or a seasoned veteran with a Chrome extension you'd like to port, this guide contains all the information you need to develop, test, package, and publish an extension for Microsoft Edge. 

## Developing an extension

The first step of this journey is to create an Edge extension: 
- New to extensions? Check out our [guide on how to create extensions](./guides/creating-an-extension.md) for information on how to build your first browser extension! 
- Already familiar with extension APIs? Check out our [API support documentation](./api-support.md) for the latest info on which APIs are supported/in development. 
- Have a Chrome extension that you want to port to Microsoft Edge? Try the [Microsoft Edge Extension Toolkit](./guides/porting-chrome-extensions.md)!

## Loading and debugging

Once you have an extension that works in Edge, you'll want to side load it to see it in action. The first step to do this is to ensure that you have [extension developer features enabled](./guides/adding-and-removing-extensions.md). This will allow you to side load extension files in Edge so that you can test your extension while developing it. Should you run into any issues, the F12 developer tools allow you to [debug the various contexts of your extension](./guides/debugging-extensions.md) to determine exactly what's going on. Still running into issues? Our [troubleshooting guide](./troubleshooting.md) has solutions to several common gotchas. 

## Reporting bugs and getting help

Think you've found a bug in our extensions platform? If the issue is specific to Edge, please search for it on our [Edge Issue Tracker](https://developer.microsoft.com/microsoft-edge/platform/issues/) to see if it's already been reported. If it has, great! You can press the "+ Me too" button to upvote the bug and the "Watch this issue for updates" button to be alerted to any changes on the issue. If you can't find the issue you're running into, feel free to open a new issue and provide as much information as possible so our developers can look into it. 

Are we missing an API that your extension needs to work properly? If so, [we're always listening on UserVoice](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer/category/87962-extensions). Feel free to upvote your API if it already exists, or to create a new feedback item so that other developers can upvote it too! 

Do you have a question that you can't find an answer to in the documentation? We strongly recommend you join the [Microsoft Edge Extensions community](https://stackoverflow.com/questions/tagged/microsoft-edge-extension) on Stack Overflow and ask it there!

## Testing your extension

As of the Windows Anniversary Update, [Microsoft WebDriver](../dev-guide/tools/webdriver.md) supports the automated side loading of extensions in Edge sessions. This will allow you to write simple tests to ensure that any extension that is meant to modify a page does so in the expected manner. You can find more info on how to do this in our [testing guide](./guides/packaging/creating-and-testing-extension-packages.md#automated-testing-with-webdriver). Also, stay tuned for updates as we plan to add more extension-specific features to Microsoft WebDriver in the future.

## Adding the final touches

So your extension works in Edge. What happens next? Before you continue packaging your extension, we strongly recommend you to check out these guides to ensure that your extension is following our best-practice policies: 
- Make sure your extension icons are [correctly sized](./guides/design.md) and [accessible](./guides/accessibility.md) (meaning they're visible in both light and dark themes of Edge as well as in high contrast mode). 
- If your extension needs to support multiple languages, please make sure you've taken a look over our [internationalization guide](./guides/internationalization.md). 

## Packaging an extension

Now your extension is finally polished up and is ready to be packaged. Since our extensions platform is still in its infancy, we're purposely allowing only small numbers of extensions into the Windows Store at a time so that we can focus on delivering a quality experience for our users and developers. If you want to get your extension packaged in preparation for submission, however, or if you want to package it for ease of distribution within your development/testing teams, there are plenty of resources available to help you: 

- Our recommended solution for creating an extension package is to follow our [ManifoldJS packaging guide](./guides/packaging/using-manifoldjs-to-package-extensions.md) which will walk you through the steps of using a Node.js based tool to easily package your extension no matter what platform you develop on. If you want a more manual and in-depth look into our extension packaging format, please refer to our [AppX package creation guide](./guides/packaging/creating-and-testing-extension-packages.md#preparing-the-submission-folder). 
- If your extension supports multiple languages, you'll also need to follow our guide on [localizing extension packages](./guides/packaging/localizing-extension-packages.md) so that the languages you have in your extension are correctly registered after packaging. 

If you're an enterprise customer looking to distribute your packaged extensions via internal channels, please see our [extensions for enterprise guide](./extensions-for-enterprise.md) to see how to do this.  

## Publishing to the Windows Store

As stated above, we're purposely allowing only a small numbers of extensions into the Windows Store at a time so that we can focus on quality.

> [!NOTE]  
> Submitting a Microsoft Edge extension to the Windows Store is currently a restricted capability. [Reach out to us](http://aka.ms/extension-request) with your requests to be a part of the Windows Store, and we’ll consider you for a future update.

 
Once we've reached out to you, the first step of the publishing process is to make sure your extension conforms to our [browser extension policy](./microsoft-browser-extension-policy.md) as well as the [Edge extensions section of the Windows Store Policies](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12). 

Once you've confirmed that your extension follows the policies, you will need to register for a [Windows Dev Center account and reserve the name of your extension](./guides/packaging/extensions-in-the-windows-dev-center.md). Once this is done, you'll be able to submit your extension to the Windows Store where it will undergo manual review and automated performance testing to ensure that it does not negatively impact page load time or browser memory consumption.  
 
> [!NOTE]
The process for publishing an extension to the Windows Store (whether it's a brand new extension or an update to an existing one) can take up to 72 hours to complete. In order to expedite this process, please ensure you have verified these common gotchas before submitting to avoid having to resubmit later: 
> - Your screenshots are correctly sized and are of your extension running in Microsoft Edge 
> - Your extension description references "Microsoft Edge" instead of "Edge" (this is a legal requirement) 
> - Your 150x150 icon in your extension package [does not have a transparent background](./guides/design.md#windows-store-icon) (The Windows Store client does not correctly render images with transparent backgrounds) 


In addition to the above, and if applicable, please ensure that any platform availability information on your website correctly mentions your extension's availability on Edge. While the Windows Store does not allow for one-click inline extension installs, you can [deep-link to your extension in the Windows Store](./tips-and-tricks.md#get-a-direct-link-to-your-extension-in-the-windows-store) to make it easy for users to acquire it. 

The Windows Store also allows you to [control the visibility of your extension](https://blogs.windows.com/buildingapps/2015/09/10/managing-hidden-apps-beta-apps-and-visibility-of-in-app-purchases-in-dev-center/) in the Windows Store catalog. Some of our partners have taken advantage of this functionality to achieve the following: 
- Publishing a second beta version of their extension as hidden in the Windows Store.
- Initially publishing their extension as hidden to monitor initial telemetry before eventually changing its status to visible once a certain level of confidence is reached.

## That's it!

If you've reached the bottom of this guide, you've completed the process of developing an extension for Microsoft Edge! Be sure to check out our [tips and tricks](./tips-and-tricks.md) page for ideas on how to market your extension and interact with your users.