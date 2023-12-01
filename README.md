# Picturing Paws: Evaluating AI Art

## Introducing AWS Rekognition
Amazon Web Services (AWS) has a service for computer vision purposes. It is a clouc based service that makes it easy to add image and video analysis to applications. It utilizes deep learning technology to automatically identify objects, people, text, scenes, and activities in images and videos. Rekognition also offers facial analysis and recognition capabilities, enabling applications to identify and compare faces for a variety of user verification, people counting, and public safety use cases. This service is designed to be highly scalable, providing fast and accurate analysis, and doesn't require machine learning expertise to use.

## Architecture Overview
First we used Dog API to generate 15 random and realistic images of different dog breeds. Next, we used prompt engineering in DALL-E 3 to generate mimicked versions of the Dog API images by specifying variable such as breed, mood/expression, action, etc and then included a tweak to generate 15 more precise photos. We then sent these images to their respective S3 buckets within the AWS cloud. We ran those buckets through Sagemaker to do a model analysis in rekognition which generated confidence scores between the real and AI images.
