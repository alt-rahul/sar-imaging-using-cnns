# Despeckling SAR Images Using CNNs

This is repo is a implementation in PyTorch of the paper, [SAR Image Despeckling Using a Convolutional Neural Network](https://ieeexplore.ieee.org/document/8053792).

However, the results from this CNN model will vary from the results proposed in the paper as a [different dataset](https://ieee-dataport.org/open-access/virtual-sar-synthetic-dataset-deep-learning-based-speckle-noise-reduction-algorithms) was used and the implementation slightly varies. 

To build the model and run this notebook yourself, replace `clean_dir` and `noise_dir` with the correct local path to your dataset and run all cells. 

If you would just like to test the model, then follow these steps (without needing to spend multiple hours trying to train it with a cheap gpu):

1. Run only the cell that creates the model 
2. Initilize an instance of the model through the subsequent code

    ```python
    torch.manul_seed(69)
    model = SARDespeckleModel(
        input_shape=1,
        hidden_units=64,
        output_shape=1,
    )
    ```
3. Load the parameters of the trained model and replace `MODEL_SAVE_PATH` with the local path of the model downloaded from the _models_ folder.

    ```python
    model.load_state_dict(torch.load(f=MODEL_SAVE_PATH))
    ```
4. Enjoy