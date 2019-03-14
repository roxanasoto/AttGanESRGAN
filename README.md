# AttnGAN

Implementación de Pytorch para el modelo AttnGAN para generar imágenes a partir de una descripción de texto. Basado en el artículo original https://arxiv.org/abs/1711.10485 y los repositorios de autores https://github.com/taoxugit/AttnGAN

### Dependencias

* Python 3.6
* Pytorch 0.4.1
* python-dateutil
* easydict
* pandas
* torchfile
* nltk
* scikit-image
        
### Data

* Metadatos para el dataSet <a href="https://drive.google.com/open?id=1O_LtUP9sch09QH3s_EBAgLEctBQ5JBSJ">birds</a> - extraer al folder data/
* Imagenes para el dataSet <a href="http://www.vision.caltech.edu/visipedia/CUB-200-2011.html">birds</a> - extraer al folder data/birds/

### Training

PreEntrenamiento DAMSM:
    
    python pretrain_DAMSM.py --cfg cfg/damsm_bird.yml --gpu 0
    
Los resultados del preEntrenamiento son guardados en la carpeta output. Despues de Completar - la seleccion de archivos enconder deberian estar hubicados  en la carpeta DAMSMencoders, y se registra la configuracion a las rutas en el archivo attn_bird.yml 
    
Training AttnGAN:
    
    python train.py --cfg cfg/attn_bird.yml --gpu 0

Las salidas del Learning se guardan en la carpeta output. despues de finalizar - ponemos el archivo de la seleccion del modelo en la carpeta models y se registra las ruts de configuracion a estos en el archivo eval_bird.yml

    
### Ejecucion
    
    python eval.py --cfg cfg/eval_bird.yml --gpu 0
    
Las imagenes generadas estan hubicadas en la carpeta results. Por defecto, la generacion se lleva acabo por frases del archivo data/birds/example_captions.txt  

Tambien puedes verlo con Jupyter Notebook для тестирования - notebooks/eval.ipynb    
  
### Ejemplos de trabajo

<img src="https://github.com/aleksey-egorov/attngan/blob/master/images/try1.png">    
<img src="https://github.com/aleksey-egorov/attngan/blob/master/images/try2.png">    
    
### Referencias

* <a href='https://arxiv.org/abs/1711.10485'>AttnGAN: Fine-Grained Text to Image Generation with Attentional Generative Adversarial Networks</a>, 2018 - Tao Xu, Pengchuan Zhang, Qiuyuan Huang, Han Zhang, Zhe Gan, Xiaolei Huang, Xiaodong He



