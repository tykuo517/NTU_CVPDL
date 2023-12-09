# Solving Data Imbalance Problem via Data Augmentation
### Environment
Details list in "environment.yml"

### Image Captioning
`S1_image_captioning.ipynb`
1. Compare the performance of three different pretrained models for generating prompts.
2. Choose the best one and generates prompts for images in training set.
3. The results will be stored in `./code/image_captioning.json`.

### Data Augmentation
`S2_data_augmentation.ipynb`
- Test performance
1. Choose 20 images each category for testing performance, and the information for these images will be stored in `./code/image_select.json`.
2. Generate images using GLIGEN and compare the performance of **text-grounding** and **image-grounding** with FID.
- Data augmentation
1. Download pretrained model of GLIGEN, and place it under `./code/gligen_checkpoints`
2. Run `python gligen_inference.py` with some specified conditions generating different numbers of images each category to solve the data imbalance problem with **text-grounding** and **image-grounding** method.
3. The generated images will be in `./code/GLIGEN/generation_samples` with designated folder name.
4. The information of the images being generated for data augmentation will be stored in `image_gen.json`.
5. After generating, move the generated images to training set folder and update the annotations `train.json`.

### Train Object Detection Model
1. Download pretrained model of DINO, and place it under `./code/DINO/models`
2. Since you have two different training datasets from two generation methods, please remember to change the training set path in `./code/DINO/datasets/coco.py`
2. Run `bash train.sh ../../dataset` under `./code/DINO` path, and you will get the final checkpoint in "./code/DINO/ckpt"
3. For inference, run "./code/DINO/inference.ipynb" and two predicted result `valid_image_gen.json` and `valid_text_gen.json` will be generated.
4. Evaluate the performance and visualize it.

