# Tika Image and Video Object Detection and Captioning Dockers

This repository contains Docker File Image source for the use of image and video object identification and detection and image and video captioning using [Tensorflow](http://tensorflow.org/) and the [Apache Tika](http://tika.apache.org/) toolkit. Combined with our [Image Captioning Project by USC Data Science](http://github.com/USCDataScience/img2text.git) we provide a full implementation of the [Show and Tell: A Neural Image Caption Generator](https://arxiv.org/abs/1411.4555) paper. To our knowledge there is no other implementation of this paper available in the public domain.

# To Build the Dockers
  1. `docker build -f InceptionRestDockerfile -t uscdatascience/inception-rest-tika .` - Builds the Inception v4 model Image detection capability. 
  2. `docker build -f Im2txtRestDockerfile  -t uscdatascience/im2txt-rest-tika .` - Builds the Show and Tell model Image Text Captioning capability. 
  3. `docker build -f InceptionVideoRestDockerfile -t uscdatascience/inception-video-rest-tika .` - Builds a Docker with OpenCV and Tensorflow that can be used to idenitfy objects in Videos.

# To Test the Dockers
  1. `docker run -it -p 8764:8764 uscdatascience/inception-rest-tika` - then run the tests in [ObjectRecognitionParserTest class](https://github.com/apache/tika/blob/master/tika-parsers/src/test/java/org/apache/tika/parser/recognition/ObjectRecognitionParserTest.java)
  2. `docker run -it -p 8764:8764 uscdatascience/im2txt-rest-tika` - then run the tests in [ObjectRecognitionParserTest class](https://github.com/apache/tika/blob/master/tika-parsers/src/test/java/org/apache/tika/parser/recognition/ObjectRecognitionParserTest.java)
  3. `docker run -it -p 8764:8764 uscdatascience/inception-video-rest-tika` - then run the tests in [TensorflowVideoRecParserTest class](https://github.com/apache/tika/blob/master/tika-parsers/src/test/java/org/apache/tika/parser/recognition/tf/TensorflowVideoRecParserTest.java)

# Citation:

If you use this work, please cite first [USC Data Science](https://github.com/USCDataScience/tika-dockers) and then:

```
@article{DBLP:journals/corr/VinyalsTBE14,
  author    = {Oriol Vinyals and
               Alexander Toshev and
               Samy Bengio and
               Dumitru Erhan},
  title     = {Show and Tell: {A} Neural Image Caption Generator},
  journal   = {CoRR},
  volume    = {abs/1411.4555},
  year      = {2014},
  url       = {http://arxiv.org/abs/1411.4555},
  archivePrefix = {arXiv},
  eprint    = {1411.4555},
  timestamp = {Wed, 07 Jun 2017 14:41:10 +0200},
  biburl    = {http://dblp.org/rec/bib/journals/corr/VinyalsTBE14},
  bibsource = {dblp computer science bibliography, http://dblp.org}
}
```

See Also
========
The [Tika Advanced Object Recognition Page](https://wiki.apache.org/tika/FrontPage#Object_Recognition_.28Computer_Vision.29_support) for more advanced tutorials on how to use the Dockers with Tika.

Questions, comments?
===================
Send them to [Chris A. Mattmann](mailto:chris.a.mattmann@jpl.nasa.gov) or [Thejan Wijesinghe](mailto:thejan.k.wijesinghe@gmail.com).

Contributors
============
* Chris A. Mattmann, JPL & USC
* Thejan Wijesinghe, University of Moratuwa

License
===
This project is licensed under the [Apache License, version 2.0](http://www.apache.org/licenses/LICENSE-2.0).
