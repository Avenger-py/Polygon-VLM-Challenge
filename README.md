# Polygon-VLM-Challenge

## Input Images
![img1](https://github.com/user-attachments/assets/ffe9296a-5986-4da2-9d8c-43303b1289ac)  

![img2 (1)](https://github.com/user-attachments/assets/8429e00d-5f5b-424b-8bef-74b1a86ec4fc)

## Output

![image](https://github.com/user-attachments/assets/431dd5e0-b06d-451a-ae5c-452f4c9e5ae6)

## Method

__Opencv__ 
1. Detect and approximate polygons, assign ID to each polygon, overlay the IDs on the polygon in both the images and save them. 
2. Detect nodes/corners.  
3. Calculate number of nodes (```corner_count```) per polygon using euclidean distance.

__VLM (Gemini)__
1. Use ```corner_count``` and ```polygon_map_input_img.jpg``` (the image with nodes & labelled polygons) to generate a polygon ID - node ID mapping (```node_dict```) with a single Gemini call.
2. In the second call, Gemini uses ```node_dict``` and ```labelled_polygon.jpg``` (image with colored & labelled polygons) to answer user queries about nodes of any polygon.
