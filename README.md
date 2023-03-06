# TrackMate_split_merge_correction
Correction of split and merge artifacts in TrackMate

When there is faulty object recognition in TrackMate, a specific kind of artifact may occur, where there are short loops consisting 
of one split and one merge. This program rebuids the split/merge scheme from TrackMate and filters out these events specifically.
It is not fully trobleshooted and should be rather treated as a prototype.


Input: The three csv tables downloadable from TrackMate (spots, edges, tracks). The maximum size of the loop to be filtered may be adjusted.

Output: 

timeFrames_output.xlsx --- This is a rough approximation of the track scheme from TrackMate. Each time frame in a track is represented 
                                   by 0 or 1, 1 corresponding to a split or merge event.
																	 
tracks_output.xlsx --- This is a summary table containing information on the events that occured within each track.

short split = splitting event followed by one of the vesciles disappearing within the lenght set by the user

short split merge = splitting event followed by merge within the length set by the usernumber of splits, number of merges = total counts of 
splits and merges captured

long split, long split merge = corresponds to short split and short split merge, but the length of the loops exceeds the value set by the user

split sum check = the velue represents a sum of all the events captured by the software (number of splits should be equal to the sum of all split 
and split merge events) and should be 0 if there are no errors
