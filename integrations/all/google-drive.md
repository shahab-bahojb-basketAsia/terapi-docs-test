---
title: Google Drive  
sidebarTitle: Google Drive  
---

API configuration: [`google-drive`](https://terapi.dev/providers.yaml)

## Features

| Features | Status |
| - | - |
| [Auth (OAuth)](/integrate/guides/authorize-an-api) | ✅ |
| [Sync data](/integrate/guides/sync-data-from-an-api) | ✅ |
| [Perform workflows](/integrate/guides/perform-workflows-with-an-api) | ✅ |
| [Proxy requests](/integrate/guides/proxy-requests-to-an-api) | ✅ |
| [Receive webhooks](/integrate/guides/receive-webhooks-from-an-api) | 🚫 (time to contribute: &lt;48h) |

We can implement missing features in &lt;48h, just ask for it in the [community](https://terapi.dev/slack).

## Getting started

-   [Google Drive access token specs](https://cloud.google.com/iam/docs/reference/sts/rest/v1/TopLevel/token#response-body)
-   [Google Drive OAuth scopes](https://developers.google.com/identity/protocols/oauth2/scopes#drive)

Need help getting started? Get help in the [community](https://terapi.dev/slack).

## Pre-built Google Drive integration

Terapi's pre-built Google Drive integration only syncs whitelisted files & folders. You can use the [Google Drive Picker](https://developers.google.com/drive/picker/guides/overview) to let the customer pick files & folders to sync.


  
    Scope to set: `https://www.googleapis.com/auth/drive.readonly`

    In your frontend, run the OAuth flow and show the Google Drive picker to your user.

    Example code:
    ```js
    const ingest = async () => {
        let filesIds = [];      
        
        const cid = generateCid(); // generate a unique id for the connection

        try {
            const auth = await yourAuthFunction('google-drive', cid);
            if (auth.connectionId) {
                filesIds = await openGooglePicker();
                if (filesIds.length === 0) {
                    return;
                }
            }
        } catch (error) {
            // handle error
        }
    }

    const openGooglePicker = async () => {
        return new Promise((resolve, reject) => {
            openPicker({
                appId: , // essential for keeping same file id between your app and Google
                clientId: ,
                developerKey: ,
                viewId: 'DOCS',
                showUploadView: true,
                showUploadFolders: true,
                supportDrives: true,
                multiselect: true,
                setIncludeFolders: true,
                setSelectFolderEnabled: true,
                callbackFunction: (data) => {
                    if (data.action === 'cancel') {
                        handleCancel();
                        resolve([]);
                        return;
                    } else if (data.action == 'picked') {
                        const fileIds = data.docs.map((doc) => doc.id);
                        resolve(fileIds);
                    }
                }
            });
        });
    };
    ```
    Placeholders:
    - `` is your App ID. [How to find your app ID](https://stackoverflow.com/a/40638063)
    - `` is the client ID of your Google OAuth app.
    - `` is the API key for your [Google Picker API](https://developers.google.com/drive/picker/guides/overview).
  
  
  
    Pass the user-selected file & folder IDs to your backend.

    From there, call the relevant SDK or REST API to store the IDs on the user's connection (SDK example):
    ```ts
    await updateMetadata(
        'google-drive',
        'CONNECTION-ID',
        {
            'folders': ['', ...],
            'files': ['', ...] 
        }
    );
    ```
  
  
  
    Re-trigger the sync in the dashboard, or with the API or Node SDK. File metadata should get synced.
  


## API gotchas

- Almost all Google Drive scopes are ["restricted scopes"](https://developers.google.com/identity/protocols/oauth2/production-readiness/restricted-scope-verification) by Google. This means your app needs to pass a security review with Google before you can go live with users.
    - The only exception is the `drive.file` scope, which lets your app access files & folders the user has previously authorized with the Google Drive Picker API.

Add Getting Started links and Gotchas by editing this page.
