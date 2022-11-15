## close-related Gleason prostate cancer scores CNN

This repository contains the code of the proposal in the paper "An inception deep architecture to differentiate close-related Gleason prostate cancer scores"  [link](https://www.spiedigitallibrary.org/conference-proceedings-of-spie/11330/113300D/An-inception-deep-architecture-to-differentiate-close-related-Gleason-prostate/10.1117/12.2547113.short?SSO=1). The dataset is available on [Harvard Dataverse](https://doi.org/10.7910/DVN/OCYCMP).

The code is divided in three scripts. The first script (``create_patches.ipynb``) creates patches to train and validate the model. The second script (``Train_model.ipynb``) trains the network using the architecture inceptionv3 that is pretrained with the imagenet weights only using patches with Gleason grade 3 and 4. It is also available to be use other architectures and other Gleason grades. Finally, (``Test_model.ipynb``) the third script uses the pathologist's annotations to test the model and generate the confusion matrix and kappa values.

The weights of the proposed model are available in [Drive](https://drive.google.com/drive/folders/18qnbhzLt3cKDVh1CbfN6lPzQabs8fUJB?usp=sharing).

We assume the following dataset structure:

```
/path/to/dataset_TMA
|-- TMA_images                              # All H&E stained images (TMAs 76, 80, 111, 199, 204)
|-- Gleason_masks_train                     # Gleason annotations for training and validation (TMAs 76, 111, 199, 204)
|-- Gleason_masks_test
    |-- Gleason_masks_test_pathologist1     # Test set annotations by first pathologist (TMA 80)
    |-- Gleason_masks_test_pathologist2     # Test set annotations by secind pathologist (TMA 80)
```

If you use our work or our code please, cite as follows:

"Fabian León, Miguel Plazas, Fabio Martínez, "An inception deep architecture to differentiate close-related Gleason prostate cancer scores," Proc. SPIE 11330, 15th International Symposium on Medical Information Processing and Analysis, 113300D (3 January 2020); https://doi.org/10.1117/12.2547113"

This code is based on  [eirini git](https://github.com/eiriniar/gleason_CNN).
