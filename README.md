# Nvdia-CUDA-Gpu-Setup/Kurulumları

---------------------GPU Kurulumu Öncesinde Yapılması ve Belirlenmesi Gerekenler------------------------------

- Anaconda Spyder Derleyicisi üzerinden kurulum işlem adımlarıdır. Diğer derleyiciler ve sürümler için kendi paylaşım sayfalarına ve sürüm notlarına bakınız. 
- https://www.anaconda.com/ ve https://anaconda.org/anaconda/spyder üzerinden programları edinebilirsiniz.
- Mail adresleriniz ile sistemlere kayıt olmanız bilgi paylaşımı açısından net bilgilere erişiminizde fayda sağlayacaktır.
- Mevcut sisteminizdeki python sürümlerini ve kütüphane sürümlerini stabil versiyonlara gelitirilmesi gerekmektedir.
- Bu bağlamda stabil işlem adımları için aşağıdaki yönergelere bakabilirsiniz.
- Stabil işlem adımlarını elde edilmesinde işletim sisteminin türü, kaç bit üzerinden çalıştığı ve sürüm notlarını önceden edininiz....
- Benim sistemlerimde çalışan en stabil sürüm aşağıdaır.
- Bu bir açık kaynak paylaşımdır. Tüm sistemler adına çalışıp çalıştırılmaması veya önceden çalışan bir sistemin üzerine kurulması - inşa edilmesinde bazı sürümlerin birbirini desteklememe gibi durumlar ile karşılaşılmaktadır.
- En stabil işletim sistemi sürümü için bilgi paylaşımları araştırılmalıdır.
- Sürüm notları ve yazılm gelişitirilmesi için kendi stabil işletim sistemi ve sürümlerinizin bilgilerine ihtiyacınız bulunmaktadır.
- Benim kullanıdğım stabil sürümler ile sizlerin stabil sürümleri farklı donanım ve yazılm sürümlerinden kullanımından kaynaklı olabilir. En iyi stabil sürümler için işinizi çözen sürümleri araştırmanız ve uygulamanız gerekmektedir.
- Buradaki işlem aşamalarını kendi kurulum sürecinize göre kurgulayabilirsiniz. Kurulum işlem aşamaları aşagıdadır. 

--------------------------------------------------------------------------------------------------------------------------------------------------

- Bilgi paylaşıldıkça çoğaalır ve gelişir!!!

-------------------------------<<---GPU Kurulum basamaklarında ilk yapılacaklar-->>--------------------------------

- prompt çalıştırılarak yeni bir çalışma alanı oluşturacağız. Bu'da  conda create -n gpucalismasi python=3.7
- activate gpucalismasi
- conda install tensorflow-gpu=1.15 (Cuda paketleri yüklü değilse uzun süre bekleme ile hata alınır!!!)

NOT: tensorflow-gpu=1.15 --> cudann-7.6.5 ve cuda10.0.0 sürümlerini destekler. diğerleri çalışmaz.
	

GPU Kurulum basamaklarında ikinci yapılacaklar-->>

1. https://www.tensorflow.org/install/gpu​ // GPU Kurulum belgeleri hakkında bilgi

2. https://developer.nvidia.com/cuda-gpus​ // Ekran kartımın kapasitesi nedir

3. https://www.nvidia.com/download/index.aspx?lang=en-us​ // Driver kur

4. https://www.tensorflow.org/install/source#gpu​ //hangi cuda bize lazım. // Kurulum

5. https://developer.nvidia.com/cuda-toolkit-archive // Cudalar dünyası.

6. https://developer.nvidia.com/rdp/cudnn-archive​ //cuDNN dünyası.

7.C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0 dosyası içerisine cuDnn dosyası
içerisindeki (bin,include,lib) dosyalarını taşı.(https://docs.nvidia.com/deeplearning/...​)

8. Pathları düzenle: 
CTRL+ R: control sysdm.cpl
Variable Name: CUDA_PATH 

C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\bin
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\lib\x64
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\include

9. C:\Program Files\NVIDIA Corporation\NVSMI altında [ nvidia-smi.exe ] çalıştırarak Gpu’ya 
ait açıklama, driver, cuda ve processleri görebilirsiniz.

10. Prompt çalıştırılarak --> activate gpucalismasi

11. pip install ipykernel

12. python -m ipykernel install --user --name gpucalismasi --display-name "gpucalismasi"

13. conda install tensorflow-gpu==1.15

14. pip install lxml pillow matplotlib jupyter contextlib2 cython tf_slim (kur)

15. https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf1_detection_zoo.md (indir)

16. https://github.com/tensorflow/models/tree/master/research/object_detection/samples/configs  (bu dosyayı GİTHUB'TAN raw formatında indireceğiz. Config dosyası old. için)

17. https://github.com/tensorflow/models (indir)

18. https://github.com/protocolbuffers/protobuf/releases/tag/v3.4.0 (protoc-3.4.0-win32.zip dosyasını sayfada bularak indir)

19. C' diskinin aldında çalışma dosyası olustur. C:\Gpucalismalari

20. C:\Gpucalismalari dosyası içine; model-master zip dosyasını çıkar.

21. Model-master klasörünün tüm içeriğini C:\Gpucalismalari üst klasöre taşı.

22. protoc-3.4.0-win32.zip dosyasının bin klasörü içinden protoc.exe dosyasını C:\Gpucalismalari\research klasörü içerisine at.

23. prompt üzerinden gpucalismalari alanı aktif iken; cd C:\Gpucalismalari\research yaz.

24. C:\Gpucalismalari\research\object_detection\packages\tf1 dosyası içinde ki setup.py dosyasını C:\Gpucalismalari\research klasörü içerisine at.

25. komut satırına --> protoc object_detection/protos/*.proto --python_out=. yazarak protoc'u çalıştır. (çok kısa sürecek)

26. komut satırına ---> python setup.py build yaz.

27. komut satırına ---> python setup.py install yaz.

------------------------------------------------------------------------------ KURULUMLAR BİTİYOR------------------------------------------------

28. Anaconda navigatoru çalıştırarak ilgili sekmeden gpucalismasi bölümüne geç

29. gpucalismasi bölümünde spyder kurulu değilse ordan install et. jupyter notebook'da kurulabilir

30. Test için ilgili webcam detection programını C:\Gpucalismalari\research\object_detection dizini altına at.

31. Anaconda navigator'da gpucalismasi bölümünde spyder'a launch diyerek programı çalıştır. 

32. webcan dedector isimli programı çalıştırdığımızda cv2 diye bir hata alırız. Bu opencv kütüphanesinin kurulu olmadığını gösterir.

33. conda install opencv kurmamız gerekir. 

34. Uygulamayı çalıştırdığında webcamden alınan anlık görüntünün ingilice hazır kütüphanede işlenmesini göreceğiz.

35. C:\Gpucalismalari\research\object_detection\data içinde mscoco_label_map dosyası içinde ingilice terimleri türkçe terim yaparak yazılım güncellenebilir. 

------------------------------------------------------------------------------LABEL-IMG------------------------------------------------------------

36. C:\Gpucalismalari dosyasının altında custom bir dosya oluştur. 

37. Data – image(train,test) – training dosyalarını oluştur.

38. LABELIMG programı --> https://github.com/tzutalin/labelImg burdan inecek.

39. Githup üzerinden Label img yi indirdikten sonra labelImg-master dosyasını C:\Gpucalismalari\custom object dizini altına at ve çıkar.

40. Prompt üzerinden gpucalismasi environmetine geçtikten sonra labelImg dizinine geçmemiz gerekmektedir. 

41. cd C:\Gpucalismalari\custom object\labelImg-master yazarak ilgili dizine geçilir. 

42. conda install pyqt=5 (kur)

43. conda install -c anaconda lxml (kur)

44. pyrcc5 -o libs/resources.py resources.qrc 

45. Python labelImg.py (label img programı çalıştırılır.)

46. internetten çoklu resim indirme programını kur. Örneğin; fatkun batch donwload image eklentisini kur (denedim çalışmadı!!)

47. Crome veya başka bir tarayıcının dosya indirme yerini çalıştığımız dosyanın C:\Gpucalismalari\custom object\images dosyası olarak ayarlamamız gerekir. iş bittikten sonra eski haline çevir.

48. Bu arada resimler *.jpg formatında olmalıdır. Resimleri bir yerde topladıktan sonra Python labelImg.py ile program çalıştırılır. 

49. Prompt üzerinde --> activate gpucalismasi bölümünde misin kontrol ederek

50. cd C:\Gpucalismalari\custom object\labelImg-master yazarak ilgili dizine geçilir. 

51. Python labelImg.py (label img programı çalıştırılır.)

52. Açılan yazılımda Open Dir diyerek hangi kalsörde çalışaçağımız seçilir. Dosya seçiminden sonra tüm resimler Labelimg içine gelir.

53. Save dir diyerek kayıt yapılacak alanı belirleriz.

54. Resimler üzerinde işlemleri W-S-D tuşları ile yaparız. 

55. W- imleç getirir, S- CTRL+S ile işlem kaydedilir ve D ile bir sonraki işleme geçilir. 

56. ilgili kayıt dosyasında xml dosyaları oluşturulmuştur. XML dosyalarında ilgili görselin boyutları ile alakalı durumlar mevcuttur.

57. Resimleri ve xml dosyalarının isimleri kontrol edilerek bir sonraki aşamaya geçilir. 

58. Tüm resimlerin sayısına dikkat ederek etiketlenmiş resimleri test ve train olarak bölecez. (Örneğin %70-%30 veya %80-%20 olarak)

59. %80 train ve %20 test olarak veri setini bölerek xml dosyalarıyla birlikte train ve test klasörlerine gönderdik.

60. Oluşan bu verileri şimdi tensorflow'a göre işlemler başlayacak.

61. https://github.com/datitran/raccoon_dataset bu web sayfasından dosyaları indir. 

62. inen dosyların içinden xml_to_csv.py ve generate_tfrecord.py dosyalarını C:\Gpucalismalari\custom object içine at.

63. Promt üzerinde cd C:\Gpucalismalari\custom object bölüme gelerek, Python xml_to_csv.py çalıştırılır. Pandas'da hata verirse --> conda install pandas

64. Bu işlem ile data klasörü içerisine test_labels.csv ve train_labels.csv dosyaları oluşturulur.

65. generate_tfrecord.py dosyasını açarak  çalıştıracağız. 

66. python generate_tfrecord.py --csv_input=data/test_labels.csv --output_path=data/test.record --image_dir=images/test/ kodunu çalıştır. 

67. 66. kod ile Successfully created the TFRecords: C:\Gpucalismalari\custom object\data/test.record şeklinde test datasının başarılı şekilde çıktı almamız gerekmektedir. 

68. python generate_tfrecord.py --csv_input=data/train_labels.csv --output_path=data/train.record --image_dir=images/train/

69. 68. kod ile Successfully created the TFRecords: C:\Gpucalismalari\custom object\data/train.record çeklinde train datasının başarılı şekilde çıktı almamız gerekmektedir. 

70. record dosyaları tensorflow için lazımdır. 

-------------------------------------------------------------EĞİTİM-SÜRECİ-ÖNCESİ-ADIMLAR---------------------------------------------------------

71. https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf1_detection_zoo.md sayfasından ssd_mobilenet_v1_coco datasetini indir. 

72. C:\Gpucalismalari\custom object\training klasörü içerisinde ssd_mobilenet_v1_coco rar dosyasını aç. 

73. https://github.com/tensorflow/models/tree/master/research/object_detection/samples/configs sayfasından config dosyasını indireceğiz. 

73. ssd_mobilenet_v1_coco.config dosyasını raw olarak training dosyası içine indir. 

74. Config dosyasını düzenle

	num_classes farklı etiketlenenlerin sayısı buraya yazılacak. 

	train_config: { batch_size: 24  --> İşlemleri CPU ile yapacaksan burayı düşür. batch_size=12 iyidir. GPU ise 24 olabilir. 

	fine_tune_checkpoint: "PATH_TO_BE_CONFIGURED/model.ckpt" ---> fine_tune_checkpoint: "ssd_mobilenet_v1_coco_2018_01_28/model.ckpt" olacak.

	num_steps: 200000 --> bilgisayarın eğitim adım sayısıdır. 

	train_input_reader: { input_path: "PATH_TO_BE_CONFIGURED/mscoco_train.record-?????-of-00100" --> input_path: "data/train.record" olacak

	eval_input_reader: { input_path: "PATH_TO_BE_CONFIGURED/mscoco_val.record-?????-of-00010" --> input_path: "data/test.record" 

	
75. C:\Gpucalismalari\custom object\data klasörü içerisinde Maske.pbtxt isimli bir text dosya oluştur.

76. Oluşturulan dosya içine 
		
	item
	{
	id:1
	name:'Maske'
	}

	YAZ.............

77. Config dosyasını düzenle

	train_input_reader: tf_record_input_reader { label_map_path: "PATH_TO_BE_CONFIGURED/mscoco_label_map.pbtxt" --> label_map_path: "data/Maske.pbtxt" olacak.
	
	eval_input_reader: tf_record_input_reader { label_map_path: "PATH_TO_BE_CONFIGURED/mscoco_label_map.pbtxt" --> label_map_path: "data/Maske.pbtxt" olacak.

78. Custom object klasörümüz artık hazır veri işleme için "data", "images", "ssd_mobilenet_v1_coco_2018_01_28" ve "training" dosyalarını kopyalayıp C:\Gpucalismalari\research\object_detection buraya yapıştıracağız. 

79. C:\Gpucalismalari\research\object_detection\legacy bu dosya içeriklerini bir üst dizine çıkar. 


------------------------------------------------------------EĞİTİM-ADIMLARI------------------------------------------------------------

80. Prompt çalıştırılarak --> activate gpucalismasi

81. Set PYTHONPATH=$PYTHONPATH: ‘pwd’:’pwd’/slim yaparak path düzeltilmesi sağlanıyor.

82. cd C:\Gpucalismalari\research\object_detection diyerek dosya yoluna gidelim.

83. conda install numpy==1.19.2 ile numpy sürümünü 1.19a çekiyoruz. Yoksa "Cannot convert a symbolic Tensor (cond_2/strided_slice:0) to a numpy array" şeklinde bir hata alıyoruz.

84. C:\Gpucalismalari\research\slim klasörüyle birlikte C:\Gpucalismalari\research\object_detection klasörüne kopyala. 
	
85. C:\Gpucalismalari\research\object_detection klasör olarak kopyalanan slim'dosyasının içindeki; deployment ve nets dosyalarını bir üst klasöre kopyala. 

-------------------------------------------------------------EĞİTİM-BAŞLANGICI------------------------------------------------------------------

86. python train.py --train_dir=training/ --pipeline_config_path=training/ssd_mobilenet_v1_coco.config –logtostderr

87. 


!!! This is just the start... more is coming.


