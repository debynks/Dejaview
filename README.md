# Dejaview


This is a Node.js application using the Express framework. It creates a web server to serve image and video files, and it reads data from a JSON file that contains details of the images and videos.

The exif-parser, path, and exiftool-vendored modules are imported, but not used in the code.

The fs module is used to read the JSON file, and the data is parsed into an object that is used to populate arrays of file names, types, sizes, and keywords.

Three routes are defined using app.get(). The root route '/' renders an index.ejs view that displays a paginated list of all the image and video files. The /images route and /videos route render images.ejs and videos.ejs views respectively that display a paginated list of only the image or video files.

The pagination logic is implemented by getting the page number from the query parameter, setting a limit of items per page, calculating the starting index of items to show on the current page, and slicing the arrays of file names, types, and sizes based on the starting index and limit. The total number of pages is calculated by dividing the total number of files by the limit.

The rendered views receive the sliced arrays of file names, types, and sizes, as well as the current page number and total number of pages, and display them in an HTML table with pagination controls.

Express that reads metadata from images and videos and displays them on a web page. Here is a brief explanation of the code:

    The required packages are imported, including Express, exif-parser, path, fs, and exiftool-vendored.
    The view engine is set to EJS.
    Static files are served using the express.static middleware.
    The exifdata.json file is read using the fs.readFile method.
    The data from the JSON file is parsed and stored in arrays, including the filenames, file types, file sizes, and keywords.
    Routes are defined for the root URL, /images, and /videos. These routes use pagination to display a limited number of items per page and slice the arrays based on the starting index and limit. The EJS templates are rendered with the sliced arrays and pagination details.

Overall, this code sets up a web server that displays metadata about images and videos in a paginated format.
