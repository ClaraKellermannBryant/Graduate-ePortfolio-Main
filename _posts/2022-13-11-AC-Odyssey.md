---
title: "Assassin's Creed Odyssey Graphics Analysis"
date: 2022-11-13T15:34:30-04:00
categories:
  - blog
tags:
  - Jekyll
  - update
---

![Fish](https://github.com/ClaraKellermannBryant/Graduate-ePortfolio-Main/blob/master/assets/images/IMG_20220615_144653847.jpg)

**Introduction**

This study conducted for Assassin's Creed Odyssey regards graphics in a security context where the emphasis is placed on how complex objects, indices, and texture mapping can be protected from external threats. Such threats continue to exploit graphics, create damage to reputation and monetary assets, as well as violating the proprietorship of copyrighted materials in the video game industry. The study is thus intended for cybersecurity personnel, software engineers, designers, and those who are beginning their journey in the video game industry to follow best practices in graphics. 

As graphics fundamentals are implemented in a wide spectrum of industries, damages similar to those for video games may arise in other areas such as aerospace and defense. It is through consideration that the recommendations for best practices be enforced in other sectors along with the video game industry. 

 AC Odyssey was chosen due to its camera nature where users can manipulate a first-person camera in the game for photos. Therefore, all images in the study originate from the game itself without the use of tools for manipulation. 

I hope that these findings from AC Odyssey assist in the adoption of security for graphics, however, it is discouraged to copy, use, and deploy the images demonstrating the findings. 

Let's begin the analysis to view rendering in AC Odyssey.





**Complex Objects**

AC Odyssey utilizes the AnvilNext 2.0 engine which supports the rendering of the object mesh. The mesh is the foundation of each smaller object that includes what could be thought of as a blueprint for developing the structures humans recognize. For example, when viewing a column in the game, users are able to identify the object as such. Passing the camera through the column, we can see that the column is made up of several planes which in turn are plotted in the world. The concern is where users can view the deconstruction of a complex object and create an advantage point to developing similar columns for competitive reasons. :

![Column](https://github.com/ClaraKellermannBryant/Graduate-ePortfolio-Main/blob/master/assets/images/IMG_20220615_132319460.jpg)

In another case with complex object deconstruction, users can view how branches in the plants are created from the first-person camera. They can also evaluate the position of the branch and determine the planes that fashion the bottom of the branch. The branch as a separate entity shown is therefore a concern about the intellectual property theft of models in the game when a  malicious user bypasses the GPU (Koller & Levoy, 2005). :

![Branch1](https://github.com/ClaraKellermannBryant/Graduate-ePortfolio-Main/blob/master/assets/images/IMG_20220615_152828260.jpg)
![Branch2](https://github.com/ClaraKellermannBryant/Graduate-ePortfolio-Main/blob/master/assets/images/IMG_20220615_153426429.jpg)

It is suggested that watermarking complex objects are a more effective approach to deterring the misuse of models or assets. Ramasamy and Arumugam (2022) found that various techniques for watermarking consist of a spatial domain embedding process, an embedding process for image transformation, LSB embedding, and additive watermarking. Developers can then apply these watermarking models for assets accordingly. 






**Indices**

Indices refer to the plotting of vertices using the index buffer to develop the surface of an object without memory storage issues. The increase in memory storage and use may exacerbate overflow attacks when complex objects are plotted solely with vertices, and the index buffer assists in preventing such threats. 

Here, one case is presently showing how indices could save memory while ensuring adjacent objects are rendered together for mitigating gaps or other design appearances.

While conducting the study on indices, I discovered a wall that is supposedly attached to rocks, though contains a gap between the top part of the wall and the base of the structure. :
![Rock1](https://github.com/ClaraKellermannBryant/Graduate-ePortfolio-Main/blob/master/assets/images/IMG_20220615_140314265.jpg)
![Rock2](https://github.com/ClaraKellermannBryant/Graduate-ePortfolio-Main/blob/master/assets/images/IMG_20220615_140544625.jpg)
Moreover, I found a plane oriented out of the rocks in the same area. :

![RockPlane](https://github.com/ClaraKellermannBryant/Graduate-ePortfolio-Main/blob/master/assets/images/IMG_20220615_140419785.jpg)

The wall and the plane from the rocks leave vulnerabilities as misusers can manipulate design flaws such as these. It is recommended that the wall should be attached to the surrounding objects with indices and the plane from the rocks is to be either positioned appropriately or removed to follow suitable procedures.






**Collisions**

Collision overlap inhibits objects in motion to pass through other objects. For example, a sphere may strike a plane and become intertwined with the plane's mesh during an animation. In the case of AC Odyssey, the avatar's vehicle of transportation (a horse), displays issues in collision detection where bounds are not defined. 

As shown here, the left hoof of the horse is within a tree and the right hoof is partially visible due to the undefined positioning of collision detection. :

![Hoof1](https://github.com/ClaraKellermannBryant/Graduate-ePortfolio-Main/blob/master/assets/images/IMG_20220615_131639158.jpg)
![Hoof2](https://github.com/ClaraKellermannBryant/Graduate-ePortfolio-Main/blob/master/assets/images/IMG_20220615_131538786.jpg)

The following image continues to analyze the right hoof of the horse entangled with the mesh of the tree. :

![RightHoof](https://github.com/ClaraKellermannBryant/Graduate-ePortfolio-Main/blob/master/assets/images/IMG_20220615_131802443.jpg)


Collision resolution and detection answer such complications with meshes by establishing bounds through initializing position, input validation, and updating the rendering.  LearnOpenGL - Collision detection (n.d.) suggests implementing the bool CheckCollision() function to ensure overlap in meshes such as those for the horse and the tree bounce back to form the collision. 






**Textures**

Texture mapping is the basis of what makes a complex object realistic or creative compared to rendering solid colors. As textures are proprietary intangibles that are owned by the persons who developed the texture, copyright laws are associated with obtaining textures. 
The images presented are taken from the first-person camera that can be extracted out of the game in violation of copyright. 

The first image is a painting texture mapped on a wall for decorative purposes. Again, the first-person camera was able to zoom in on the wall, capturing the painting's texture. The image is cropped to protect the texture from misusers in this demonstration. :


The second image is of the ground zoomed in past the grass objects to reveal one of the textures applied on floor surfaces. As shown, several grass objects appear in the image, however, the texture is significantly visible. :


The third image illustrates how the first-person camera ignores collision detection and is able to find additional textures that are hidden in the third-person camera. Using the planter example as before, a stone texture is placed beneath. A misuser could then zoom into the planter and orient the camera for obtaining the stone texture. :


The fourth image exhibits unease; when the avatar burns a certain material such as hay in the game, a fire animation occurs. The first-person camera can zoom into the burning material and reveals the gif texture mapped. :



The recommended procedures for protecting textures are to ensure that cameras cannot overlap with objects for accessing textures, deploy the watermark strategies mentioned previously, and encrypt texture data. Additionally, enforce collision measures to prohibit the camera from zooming into textures - placing objects to serve as boundaries and input validation suffice for these circumstances.







**Conclusion**

The findings have exemplified areas of concern for developers and design teams alike. As the copyright infringement of graphics intangibles is at an all-time high, the best practices discussed for each area are proposed to combat exploitation. It is therefore pertinent to enforce best practices and study AC Odyssey further in determining the outlook precursor incidents regarding graphics.





                                      
**References**        
                                               
                                                                                  
Koller, D., & Levoy, M. (2005, June). Protecting 3D Graphics Content—Corrected CACM article. Retrieved November 13, 2022, from https://graphics.stanford.edu/papers/protecting/article-html/

LearnOpenGL - Collision detection. (n.d.). Retrieved November 13, 2022, from https://learnopengl.com/In-Practice/2D-Game/Collisions/Collision-detection

Ramasamy, R., & Arumugam, V. (2022). Digital watermarking—A tutorial. IEEE Potentials, 41(4), 43–48. https://doi.org/10.1109/MPOT.2015.2435802

