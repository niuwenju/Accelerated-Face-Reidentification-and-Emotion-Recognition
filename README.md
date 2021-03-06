# Accelerated-Face-Reidentification-and-Emotion-Recognition
A highly fast and realtime face recognition, reidentification solution with emotion identification developed to run inference on IP cameras.
The program intends to be a real-time performer on IP camera feed, where faces are detected and a 128-D vector representation is generated, which gets compared to face embeddings stored in a Mongo database.
The user can snap pictures of people's face and use the ```create_encoding.py``` file to generate face embeddings and store it in a MongoDB with a name attached to each face.
Performance is accelerated using the OpenVINO toolkit from Intel, which enebles faster CPU inference that lets users run AI modules such as this with minimal hardware.
## Pre-requisites
1. OpenVINO Toolkit
2.OpenCV 3.4
3. imutils
4. face_recognition
5. MongoDB
## Running the inference
1. Create a MongoDB database in the name 'Main_DB'
2. Generate embeddings of the faces to be detected by running ```python create_encoding.py -i <path-to-image> -n <name-of-the person>```. This generates a 128-D vector by using a CNN and stores it in the database along with the name of the person.
3. To start the inference on any camera, run ```python reid.py```(default is set to webcam; change it to your preference in Line-54 under ```src``` flag).
## Note
Before running the code please make sure you have properly configured OpenVINO on your Intel based device where you plan to run the inference. Tutorials on setting up OpenVINO can be found [here](https://software.intel.com/en-us/articles/OpenVINO-Install-Linux)
