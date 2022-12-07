# Resnet50_ile_Nesne_Saptama
Öncelikle aşağıdaki komutlar ile gerekli kütüphaneler import edilir

from keras.applications import ResNet50
from keras.utils.image_utils import img_to_array
from keras.applications import imagenet_utils
from PIL import Image
import numpy as np
from io import BytesIO
import os
import requests

imagenette tanımlı ön eğitimli ağırlıklar ile model oluşturmak için 

model=ResNet50(weights="imagenet")
