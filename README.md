# BrainTumor_sagittal_t1wce_Yolov10
From dataset https://www.kaggle.com/datasets/davidbroberts/brain-tumor-object-detection-datasets/data?select=sagittal_t1wce_2_class
a model is obtained, based on yolov10 to indicate a brain tumor type: sagittal_t1wce

 === Installation:
 
 Download all project datasets to a folder on disk.

Install yolov10 (if not yet installed) following the instructions given at: https://blog.roboflow.com/yolov10-how-to-train/ which may be reduced to !pip install -q git+https://github. com/THU-MIG/yolov10.git

If you already have ultralytics installed, it would be advisable to upgrade ultralytics, unless you have applications based on yolov10 without updating, which could be affected by the update (in this case you could consider copying over a new environment and work in this new environment).

For that you must have an upgraded version of ultralytics and the proper version of lap:

inside conda in the scripts directory of the user environment:

python pip-script.py install --no-cache-dir "lapx>=0.5.2"

upgrade ultralytics:

python pip-script.py install --upgrade ultralytics And download from https://github.com/THU-MIG/yolov10/releases the yolov10n.pt.
In case this operation causes problems, these files are attached with the rest of the project files.

Unzip the Test1.zip folder. Some zip decompressors duplicate the name of the folder to be decompressed: a folder that contains another folder with the same name, should only contain one.
In these cases it will be enough to cut the innermost folder and copy it to the project folder.

=== Test: 

Execute: 

EvaluateTEST_sagittal_t1wce_2_class_Yolov10.py 

The x-rays are presented on the screen with a red box indicating the prediction positive, a blue box negative and with a green box the label of the image that must indicate true position .

The console indicates the classes that have been detected and their confidence and the class with the image ws labeled.

=== Training

The project comes with an optimized model: last14epoch9hits.pt

To obtain any other model the following must be executed:

unzip sagittal_t1wce_2_class.zip

Some zip decompressors duplicate the name of the folder to be decompressed: a folder that contains another folder with the same name, when should only contain one. In these cases it will be enough to cut the innermost folder and copy it to the project folder.

This training file is used instead of the original downloadable from https://www.kaggle.com/datasets/davidbroberts/brain-tumor-object-detection-datasets/data?select=sagittal_t1wce_2_class since in the original the valid folder appears as test, to test with test records that have not been involved in the training process, the last 12 records from the test folder (with their labels) were cut and pasted onto the test folder Test1, thus ensuring a test folder with images that had not been treated with the training.

The training uses the yaml file:

sagittal_t1wce_2.yaml

In sagittal_t1wce_2.yaml the absolute addresses of the project appear assuming that it has been installed on disk C:, if it has another location these absolute addresses will have to be changed.

Execute: 

Train_sagittal_t1wce_2_class_Yolov10.py

This program has been adapted from https://medium.com/@huzeyfebicakci/custom-dataset-training-with-yolov10-a-deep-dive-into-the-latest-evolution-in-real- time-object-ab8c62c6af85 It assumes that the project is located in the folder "C:/BrainTumor_sagittal_t1wce_Yolov10", otherwise the assignment must be changed by modifying line 23 The parameter multi_scale has been changed to true.

The LOG_Train_Resume50epoch.docx file is attached with a training log with 50 epoch. A mAP50 of 0.528 has been reached with a mAP50-95 of 0.397.


=== References

https://www.kaggle.com/datasets/davidbroberts/brain-tumor-object-detection-datasets/data?select=sagittal_t1wce_2_class

https://medium.com/@huzeyfebicakci/custom-dataset-training-with-yolov10-a-deep-dive-into-the-latest-evolution-in-real-time-object-ab8c62c6af85


https://github.com/ablanco1950/Fracture.v1i_Reduced_YoloFromScratch

https://github.com/ablanco1950/Kidney_Stone-Yolov10

https://github.com/ablanco1950/PointOutWristPositiveFracture_on_xray
