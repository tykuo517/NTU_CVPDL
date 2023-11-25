# Object Detection

Environment: Details list in "environment.yml"

1. For training, run "bash train.sh ../dataset" under "./code" path, and you will get the final checkpoint in "./code/ckpt"
2. For inference, run "./code/inference.ipynb" after changing the absolute path to your "./code" path in the second cell

Then you will get two output results in "./dataset":
"output_for_validation.json"-> valid set prediction
"output.json"-> test set prediction
