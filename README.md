# Распознавание рукописного текста в школьных тетрадях
### Задача
> Алгоритм, который способен распознать рукописный текст в школьных тетрадях. В качестве входных данных вам будут предоставлены фотографии целых листов. Предсказание модели — список распознанных строк с координатами полигонов и получившимся текстом.
---

### Как должно работать решение?
> Две модели: сегментации и распознавания. Сначала сегментационная модель предсказывает полигоны маски каждого слова на фото. Затем эти слова вырезаются из изображения по контуру маски (получаются кропы на каждое слово) и подаются в модель распознавания. В итоге получается список распознанных слов с их координатами.
---

### Модели

**Instance Segmentation**
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/naradey2k/handwritten-text-recognition/blob/main/detectron2_segmentation.ipynb)

- модель [X101-FPN](https://github.com/facebookresearch/detectron2/blob/main/MODEL_ZOO.md#coco-instance-segmentation-baselines-with-mask-r-cnn) из зоопарка моделей detectron2 + аугментации + высокое разрешение

**Optical Character Recognition (OCR)**
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/naradey2k/handwritten-text-recognition/blob/main/attention_crnn.ipynb)

- архитектура Transformer OCR (CNN + Attention Decoder)

**Beam Search**
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Lednik7/nto-ai-text-recognition/blob/main/dataset/make_kenlm_dataset_latest.ipynb)

- модель [KenLM](https://github.com/kpu/kenlm), обученная на текстах тетрадей, а также [CTCDecoder](https://github.com/parlance/ctcdecode)

### Ресурсы 
**Colab PRO** с **NVIDIA Tesla V100**

Веса моделей (без поддержки ссылки):
[Google Drive](https://drive.google.com/drive/folders/1P6a0Cvnfq_Y4sqzwKrVoFoZ0JZ-z_n3O?usp=drive_link)
