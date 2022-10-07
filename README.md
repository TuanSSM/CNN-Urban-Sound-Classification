# CNN Urban Sound Classification

> This repository contains Deep Learning Bootcamp Project done by the group Skynet-0.1

Bu depo Global AI Hub & Koç Holding Derin Öğrenme Bootcamp'inde Skynet-0.1 grubunun projesini içerir

## Gürültüden Arındırılmış Spectogramlar

Spectogramlar oluşturulurken `noisereduce` kütüphanesi ile gürültüden arındırılıp alternatif spectogramlar elde edilmiştir.

Örnek:

| Orijinal                                                    | Gürültüsüz                                                      |
| :-:                                                         | :-:                                                             |
| ![Vanilla Spectogram](media/vanilla_spectogram_example.png) | ![Noiseless Spectogram](media/noiseless_spectogram_example.png) |

## Ön İşleme

+ Elde edilen spectogramlardan beyaz padding çıkarıldı.
+ Grayscale, resize ve normalizasyon yapıldı.
+ [np.array, etiket] listelerinde orijinal ve gürültüsüz spectogramlar 2 ayrı csv dosyasına yazıldı.

## CNN

Model özeti

Model: "sequential_1"

 | Layer (type) | Output Shape | Param # |
 | :-:          | :-:          | :-:     |
 conv2d_4 (Conv2D)    | (None, 100, 100, 32)  | 320       
                                                                 
 max_pooling2d_3 (MaxPooling  (None, 50, 50, 32) | 0         
 2D)                                                             
                                                                 
 conv2d_5 (Conv2D)           (None, 50, 50, 64)        18496     
                                                                 
 max_pooling2d_4 (MaxPooling  (None, 25, 25, 64)       0         
 2D)                                                             
                                                                 
 conv2d_6 (Conv2D)           (None, 25, 25, 64)        36928     
                                                                 
 max_pooling2d_5 (MaxPooling  (None, 12, 12, 64)       0         
 2D)                                                             
                                                                 
 conv2d_7 (Conv2D)           (None, 12, 12, 64)        36928     
                                                                 
 flatten_1 (Flatten)         (None, 9216)              0         
                                                                 
 dense_5 (Dense)             (None, 64)                589888    
                                                                 
 dropout_4 (Dropout)         (None, 64)                0         
                                                                 
 dense_6 (Dense)             (None, 64)                4160      
                                                                 
 dropout_5 (Dropout)         (None, 64)                0         
                                                                 
 dense_7 (Dense)             (None, 64)                4160      
                                                                 
 dropout_6 (Dropout)         (None, 64)                0         
                                                                 
 dense_8 (Dense)             (None, 64)                4160      
                                                                 
 dropout_7 (Dropout)         (None, 64)                0         
                                                                 
 dense_9 (Dense)             (None, 10)                650       
                                                                 
=================================================================
Total params: 695,690
Trainable params: 695,690
Non-trainable params: 0
_________________________________________________________________
