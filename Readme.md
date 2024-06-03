## progression
### object detection
I trained a detection yolov8 model with labeled data that I have recived.
!(img)[output-dect.gif]
This detection is made on a test video with a duration of 23s.
### segmentation
For segmentation I used yolov8-seg model. The dataset was made with labelme. I plan to use it on the crops of the detection model.
!(img)[output-seg.gif]

### feature extraction
I make a dataframe analyzing the coutours of the segmented parts. Most of the data I get with fit of the smallest possible rectangle or an ellipse. The data for the neck still needs improvents.


	<class 'pandas.core.frame.DataFrame'>
	Index: 169 entries, 0 to 168
	Data columns (total 14 columns):
	 #   Column            Non-Null Count  Dtype  
	---  ------            --------------  -----  
	 0   frame             169 non-null    int64  
	 1   head_area         169 non-null    float64
	 2   head_length       169 non-null    float64
	 3   head_width        169 non-null    float64
	 4   head_ratio        169 non-null    float64
	 5   head_orientation  169 non-null    float64
	 6   ovality           169 non-null    float64
	 7   smoothness        169 non-null    float64
	 8   neck_area         169 non-null    float64
	 9   neck_length       169 non-null    float64
	 10  neck_width        169 non-null    float64
	 11  neck_orientation  169 non-null    float64
	 12  neck_normal       169 non-null    float64
	 13  tail_length       169 non-null    float64
	dtypes: float64(13), int64(1)
	memory usage: 19.8 KB

### next tasks
- extracting **form** features (head/neck/tail - defects) with fourier descriptors and with splines. I want to compare the techniques and test its feasibility for this task.
- try to extract a 3d shape of the head 
- the segmentation model is trained for head, neck, tail and cytoplasmatic droplets. I need to augment the acrosom to the dataset and retrain it. 
- by end of June I want to have the table of contents for the thesis finished and approved. If possible, I'll have written some parts.
