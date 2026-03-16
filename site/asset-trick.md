implement the Asset trick and editor asset trick for this Gemini Canvas Site

# Asset trick implementation guide

- if __app_id is present, the upload assets button is present, otherwise, 'display: none' for all asset trick elements
- it opens a modal we can drop a folder into to upload assets
- modal contains a manifest of expected files with rel-paths before we upload, if any, and post upload, if they were found in the uploaded folder or not. this appears even if the manifest would be empty. this appears even before the asset folder is uploaded, so we can see what assets we are missing and need to add to the folder before uploading
- reuploading clears the existing assets, we need to upload a folder with all assets at once
- once uploaded, the rel urls of the site will direct to the uploaded assets instead according to their name and path
- once it all looks good, we can download a zip of the website source + the assets uploaded called "site.zip", in a bundle that would still work if we were to open it as a local file; this allows for cleanly putting the site onto cloudflare pages. the page itself is saved in the zip as index.html
- during export of 'index.html', all script blocks before '<title>' blocks in <head> must be stripped, as they contain gemini app specific injected code. add an id to <head> to make it easy to get a reference to even when disabled or injected in an iframe-like context
- do not strip dev panel HTML or scripts during export
- when uploaded files are not found in the site, list them in the asset manifest as 'unused' to help users understand exactly what folder they should upload
- compute required assets once and cache, as post upload the asset manifest will change to point to the uploaded files

## Editor asset trick extension implementation guide

- additionally there is a toggle edit button, only present when upload trick is on. while toggled, any of the copy text can be edited. when exporting, the updated site copy is downloaded as the edited text when downloading the zip in index.html
- finally, there is a quick 'copy site' button which copies what would be the contents of 'index.html' to clipboard.