# Resnet50_ile_Nesne_Saptama
Öncelikle aşağıdaki komutlar ile gerekli kütüphaneler import edilir

#from keras.applications import ResNet50
#from keras.utils.image_utils import img_to_array
#from keras.applications import imagenet_utils
#from PIL import Image
#import numpy as np
#from io import BytesIO
#import os
#import requests

imagenette tanımlı ön eğitimli ağırlıklar ile model oluşturmak için 

#model=ResNet50(weights="imagenet")

def prepare_image(image,target):
  image=image.resize(target) #(alınan resim image değişkeni), hedef resme göre boyutlandırılır.
  image=img_to_array(image) #resim diziye dönüştürülür.
  image=np.expand_dims(image,axis=0) # 
  image=imagenet_utils.preprocess_input(image)

  return image
  
  
  resim url'ini vererek tahminde bulunmak için
  
  imageURL="https://i.ytimg.com/vi/0fEcYI4HeKA/maxresdefault.jpg"
response=requests.get(imageURL)
image=Image.open(BytesIO(response.content))
image

![image](https://user-images.githubusercontent.com/120003620/206118655-45a25cc4-21da-48a1-8936-d8bbbbc0cc27.png)

![image](https://user-images.githubusercontent.com/120003620/206118946-1a7bcae8-a529-4dac-a8c6-f277a8ff6bc1.png)
Sonuç olarak nesne %84 ihtimalle limuzin olarak saptanıyor
