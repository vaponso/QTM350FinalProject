# Picturing Paws: Evaluating AI Art

## Introducing AWS Rekognition
Amazon Web Services (AWS) has a service for computer vision purposes. It is a cloud based service that makes it easy to add image and video analysis to applications. It utilizes deep learning technology to automatically identify objects, people, text, scenes, and activities in images and videos. Rekognition also offers facial analysis and recognition capabilities, enabling applications to identify and compare faces for a variety of user verification, people counting, and public safety use cases. This service is designed to be highly scalable, providing fast and accurate analysis, and doesn't require machine learning expertise to use.

## Architecture Overview
First we used Dog API to generate 15 random and realistic images of different dog breeds. Next, we used prompt engineering in DALL-E 3 to generate mimicked versions of the Dog API images by specifying variable such as breed, mood/expression, action, etc and then included a tweak to generate 15 more precise photos. We then sent these images to their respective S3 buckets within the AWS cloud. We ran those buckets through Sagemaker to do a model analysis in rekognition which generated confidence scores between the real and AI images.
<img src='https://drive.google.com/uc?export=view&id=1tY4cXyk2Iea5922h3YNJAb9to9M0GSie' width='2000px'>

## **Purpose**

Taking motivation from these listed issues, we wanted to evaluate DALLE-3's ability to create realistic images by using AWS Rekognition to distinguish between real and AI-generated images.

## **Hypothesis**

1. Real images will have higher confidence scores when detecting objects with label detection than the DALL-E 3 generated AI images.

2. A higher word count in DALL-E 3 prompt when creating an image for analysis will translate into a high confidence interval score.

We will try to answer these hypothesis with out results from the data analsyis on the confidence interval data we get.

## Data Analysis
We made box plots to measuring confidence scores on common labels found by Rekognition and we performed regression analysis on word count in the promts for AI image generation. 

## Conclusion
In conclusion we can see that there are many factors when choosing how Rekognition and DALL-E 3 work together. We can see that Rekognition overall will give images created by DALL-E 3 higher confidence intervals. We can also see that adjustment made from prompts kead to some interesting results in AWS Rekognition, namely that Rekognition doesn't quite like the adjusted images as much as the first AI image. This can be slightly countered by increasing the number of words for the "tweak," which is also interesting since we observed that more words for the initial prompt actually decreased the confidence score in Rekognition. These could be worth further examining. Overall, this was a fun project of combining both an AWS ML API as well as another incredibly powerful and relevant AI tool, DALL-E. AI and ML will continue to grow in the coming years, and understanding how they work will prove incredibly useful both present and future.
