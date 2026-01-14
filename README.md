# Measles-detection
A deep learning model to classify measles skin lesions

The deep learning model was tuned, and the parameters were saved.
You can assess the tuned model using: 
``model.load_state_dict(torch.load('model paras.ckpt'))``

Our measles detection tool can be downloaded from the following link: [**Download Measles Detection App**](https://1drv.ms/u/c/52e4df90413ab7a1/IQD4puD3DpHXSJ5Dxx1RaBDcAZUAMZv9q0SbUoJxrNshC-s?e=CZbBlj)


## Usage You can use `app.py` to: 
- Activate the measles detection tool
- Modify the threshold
- Adapt the model to screen other infectious diseases with skin lesions and associated clinical features

### Adjusting the Threshold To adjust the threshold, edit the following line in `calculate.py` (located in the `utils/md` folder):
