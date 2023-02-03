# Video Media Conversion Task 

Your submitted repo code should be in PHP Laravel 7

This test is in two parts, the first part is a media conversion service that converts media files(mp3, mp4, m4a) to HLS, and the second half is a Frontend vuejs app that plays the converted HLS media files. Considering this is a test, you can stop at just part 1, we’re not trying to make you do too much for a job application test. 

### Part 1:

Make a laravel 7 app that receives requests via an api and converts mp4 files to HLS (.ts) files. 
For this test, your api doesn’t need to take actual file paths, your codebase can have a static file it always converts for every request. Use a small size mp4 file that’s also inside your submitted GitHub repo. 

Few things to note: 
- use ffmpeg library to convert the media files 
- Each conversion job converts to both 480p and 720p 

NB: Media conversions should always be a background job. The conversion process would typically last longer than any default http request time limit. 


### Part 2:
- use any HLS viewing library to play the media files you converted in part one.

The goal of this test is to access your ability to learn new concepts you might not be familiar with, and also review your idea of best practices code and efficiency wise. 

The submission should be a GitHub repo with a simple readme on how to run the code you’ve built. 

######Success! 



