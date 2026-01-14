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


```python predicted_label = model(input.to(model.device))


## Adjusting the Detection Threshold
You can modify the detection threshold in your code to control how confident the model must be before classifying an image as measles.
For example:
```python
import torch.nn.functional as F
# forward pass
predicted_label = model(input.to(model.device))
output = F.softmax(predicted_label, dim=1)

# get probability for measles class (assuming class index 1 = measles)
measles_prob = output[0, 1].item()

# set threshold (e.g., 0.7)
threshold = 0.7
if measles_prob >= threshold:
  print(f"measles detected (probability: {measles_prob:.2f})")
  responses["measles_detected"] = 1
else:
  print(f"no measles detected (probability: {measles_prob:.2f})")
  responses["measles_detected"] = 0
