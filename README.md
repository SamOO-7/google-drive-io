# google-drive-io

Node.js library that makes file access in Google Drive easy.

## Abstract
The official Google Drive API requires fetching of files by their id.  This is particular problematic when manipulating files/folders with directory structures (as recursion is often required).  This library provides convenience methods that can retrieve / insert files based on their paths.

## Methods

This library exposes a number of utility methods that aid file IO in Google Drive:

* `getFolder(folderPath, returnFields, auth, callback)`
   
   ```
   Attempts to fetch a google drive folder with path specified.
   Returns Google Drive file resource object if exists, otherwise err via callback(err, folder).
   @param  folderPath folder path to search for
   @param  returnFields fields in Google file resource to return (comma separated)
   @param  auth OAuth2 client for accessing user's Google Drive
   @param  callback(err, folder) where folder is the Google Drive folder resource object
   ```

* `getRootFolder(returnFields, auth, callback)`

   ```
   Attempts to fetch the root directory in google drive.
   Returns Google Drive file resource object if exists, otherwise err via callback(err, folder).
   @param  returnFields fields in Google file resource to return (comma separated)
   @param  auth OAuth2 client for accessing user's Google Drive
   @param  callback(err, folder) where folder is the Google Drive folder resource object
   ```

* `getFile(filePath, returnFields, auth, callback)`

   ```
   Attempts to fetch a google drive file with path specified.
   Returns Google Drive file resource object if exists, otherwise err via callback(err, folder).
   @param  filePath file path to search for
   @param  returnFields fields in Google file resource to return (comma separated)
   @param  auth OAuth2 client for accessing user's Google Drive
   @param  callback(err, folder) where file is the Google Drive file resource object
   ```

* `createFolderIfNotExists(folderPath, returnFields, auth, callback)`

   ```
   Creates a google drive folder with path specified in root directory if not exists, and returns the id and url of the target folder via callback(err, id, url) 
   @param  folderPath folder path to search for / create if not exists
   @param  returnFields fields in Google file resource to return (comma separated)
   @param  auth OAuth2 client for accessing user's Google Drive
   @param  err, folder where folder is the Google Drive folder resource object
   ```

* `createFolder(folderPath, returnFields, auth, callback)`

   ```
   See documentation for `createFolderIfNotExists`.
   ```

* `uploadFile(filePath, uploadPath, returnFields, auth, callback)`

   ```
   Upload a file to google drive.
   @param  filePath path to local file object
   @param  uploadPath path to upload to in Google Drive
   @param  returnFields fields in Google file resource to return (comma separated)
   @param  auth OAuth2 client for accessing user's Google Drive
   @param  callback(err, newFile) where newFile is Google Drive file resource object of the uploaded file
   ```

* `uploadFileIfNotExists(filePath, uploadPath, returnFields, auth, callback)`

   ```
   See documentation for `uploadFile`.

   ```