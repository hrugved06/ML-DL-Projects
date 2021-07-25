# Hello People 👋🏻
=======



# A little bit background on face detection
Have you ever wondered how does your smartphone unlocks itself by just looking at your face or if you are a movie or season fan like [CSI](https://en.wikipedia.org/wiki/CSI:_Crime_Scene_Investigation) then how does they detect a known suspect passing by a mall or withdrawing money from an ATM? 

I don't know about you but I have always been curious about these questions along with many others like how does your camera takes a picture as soon as you smile(in smile detection mode)?
![Camera Face Detection](https://github.com/hrugved06/ML-DL-Projects/blob/master/Face%20detection%20using%20OpenCV/READMEimages/camera-face-detection.png)

</br>


In this article I am going to explain to you exactly what I learned and coded so that you can code these interesting ideas too. In this article I am going to focus on **face detection**.

To get you excited about the article, this is what our final output is going to look like.

![final output](https://github.com/hrugved06/ML-DL-Projects/blob/master/Face%20detection%20using%20OpenCV/READMEimages/output.png)

</br>

# Content
Now, the article is divided into three parts. The first part will briefly explain the fency and let's admit a little bit complex theory of two pre-trained classifiers of OpenCV for face detection, second part which is our favorite coding part! The last part will be the analysis of the results of both algorithms to see which algorithm is fast and which one is more reliable and accurate. So let's hop into it.

## **1.Theory :-**

A computer program that decides whether an image is positive image (face image) or negative image (non-face image) is called a classifier. A classifier is trained on a hundreds of thousands of face and non-face images to learn to classify a new image as face or non-face image correctly. `OpenCV` provides us with two pre-trained (already trained and ready to be used for detection) classifiers:

1. Haar Classifier
2. LBP Classifier

**Both of these classifiers process images in grayscales** as we don't need color information to decide if image has a face or not. As these are pretrained in OpenCV so their learned knowledge files also comes bundled with OpenCV folder from the directory. To run a classifier we need to load the knowledge files first as without that knowledge a classifier is nothing but just like a newly born baby. Each file starts with the name of classifier it belongs to. For example, `haarcascade_frontalface_alt.xml`.
</br> </br>

### Haar Classifier

It is a machine learning based approach where a classifier is trained from a lot of positive images (images with face) and negative images (images without face). The algorithm is proposed by Paul Viola and Michael Jones. 

Haar is a classifier and do you remember how a classifier is trained? Yes, with a lot of images so initially, the algorithm needs a lot of positive images (images of faces) and negative images (images without faces) to train. But you must be wondering how exactly is it trained, right? Well, it starts by extracting Haar features from each image. The windows shown in image below are used to extract features.

![Haar Features](https://github.com/hrugved06/ML-DL-Projects/blob/master/Face%20detection%20using%20OpenCV/READMEimages/haar-features.jpg)
</br> </br>

### LBP Cascade Classifier

As LBP is also a classifier so it also needs to be trained on a lot of images. LBP (Local Binary Patterns) is a visual/texture descriptor and our face too is composed of micro visual patterns. So, LBP features are extracted to form a feature vector to classify a face from a non-face. Now the big question is how to find LBP features. Let's find out!

Each training image is divided into a number of blocks as shown in image below.

![LBP Image Blocks =500x500](https://github.com/hrugved06/ML-DL-Projects/blob/master/Face%20detection%20using%20OpenCV/READMEimages/lbp-blocks.png)

For each block, LBP looks at 16 pixels (4x4 window) at a time and it is particular interested in the pixel at the center of the window. It compares the center pixel value with every neighbor pixel value under 4x4 window and for each neighbor pixel that is greater than or equal to the center pixel, it sets its value to 1 and for others it sets them to 0. Then it reads the updated pixel values (which can be either 0 or 1) in a clockwise order and forms a binary number. That binary number is then converted to a decimal number and that decimal number is the new value of center pixel. We do this for every pixel in a block. 

So after all this theory, I think it might be clear to you which classifier should you use and when. So let's compare them both so that we can make this decision. 

</br> </br>

**So, lets get to the coding part...**

</br> </br>

So, the final conclusion drawn from the model is as follows :

<TABLE  BORDER="1">
  
   <TR>
      <TH>Algorithm</TH>
      <TH>Advantages</TH>
      <TH>Disadvantages</TH>
   </TR>
   <TR>
      <TD>Haar </TD>
      <TD>
      <ol>
        <li>High detection accuracy</li>
        <li>Low false positive rate</li>
      </ol>
      </TD>
      <TD>
      <ol>
        <li>Computationally complex and slow</li>
        <li>Longer training time</li>
        <li>Less accurate on black faces</li>
        <li>Limitations in difficult lightening conditions</li>
        <li>Less robust to occlusion</li>
      </ol>
      </TD>
   </TR>
   <TR>
      <TD>LBP</TD>
      <TD>
      <ol>
        <li>Computationally simple and fast</li>
        <li>Shorter training time</li>
        <li>Robust to local illumination changes</li>
        <li>Robust to occlusion</li>
      </ol>
      </TD>
      <TD>
      <ol>
        <li>Less accurate</li>
        <li>High false positive rate</li>
      </ol>
      </TD>
   </TR>
</TABLE>

</br> </br>

## **Developed by :-**


Hey, This is Hrugved Kolhe.

<a href="https://github.com/hrugved06"><img src="https://avatars.githubusercontent.com/u/59966943?s=400&u=445f4a7598547c0ecdeb22a265dd1a3dad9e297d&v=4" width="100px;" alt=""/><br /><sub><b> Hrugved Kolhe</b></sub></a>
</br>

[![GitHub followers](https://img.shields.io/github/followers/hrugved06.svg?label=Follow%20@hrugved06&style=social)](https://github.com/hrugved06)  [![Twitter Follow](https://img.shields.io/twitter/follow/HrugVed_?style=social)](https://twitter.com/HrugVed_)

</br>
<hr style="height:2px;#8080ffborder-width:0;border-radius: 5px;color:gray;background-color:#8080ff">
</br>
