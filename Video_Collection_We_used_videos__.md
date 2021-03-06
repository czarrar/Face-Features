# Video Collection

We used videos taken from YouTube. We searched for people (1,595) already found in the YouTube Faces database with the aim of getting a higher resolution dataset than the extant YouTube Faces database. Our procedure for downloading and extracting relevant portions of the video also followed the prior face database.

1. Search a person’s name 
2. Take the top six results and minimize duplicate videos with edit distance less than 3
3. Do I want to downsample the frame-rate?
4. Detect faces using the dlib library
5. Filter videos to have time-points with only one face and length of clip must be a minimum of 2s (detections were considered consecutive if the Euclidean distance between detected corners was less than 10 or so pixels [might need to increase this given resolution]) 6. I want to then apply a face recognition algorithm to see if the clips are of that person...further whittle it down...can use the lqp approach for this. 7. Finally, manually verify the remaining videos were manually verified to ensure that (a) the videos are correctly labeled by subject, (b) are not semi-static, still-image slide-shows, and (c) no identical videos are included in the database.

What I actually want to do is use the previous database to provide training to a classifier, which we can then use to help identify the relevant clips in the video. Of course there could be some bias here in which clip is chosen but this would allow me the best way to keep a very large collection of videos that I could use at will...

From the other paper: We begin by using the 5, 749 names of subjects included in the LFW data set [6] to search YouTube for videos of these same individuals. The top six results for each query were downloaded. We minimize the num- ber of duplicate videos by considering two videos’ names with edit distance less than 3 to be duplicates. Downloaded videos are then split to frames at 24fps. We detect faces in these videos using the VJ face detector [17]. Automatic screening was performed to eliminate detections of less than 48 consecutive frames, where detections were considered consecutive if the Euclidean distance between their detected centers was less than 10 pixels. This process ensures that the videos contain stable detections and are long enough to provide useful information for the various recognition algo- rithms. Finally, the remaining videos were manually ver- ified to ensure that (a) the videos are correctly labeled by subject, (b) are not semi-static, still-image slide-shows, and (c) no identical videos are included in the database.
