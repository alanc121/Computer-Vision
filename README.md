# Computer-Vision
This assignment seeks to explore image processing. 
The primary aim of this assignment is to understand the practical implementation and theory behind image processing and the steps required to achieve this. 
A secondary aim is to familiarise yourself with MATLAB and research different techniques to carry out the tasks required.

# Question 1
This question splits each of the RGB values into separate monochrome components. Figure 1,5 and 9 illustrates the original image with RGB and no monochrome.
RGB values refers to a system for representing the colours on a computer display. Red, green, and blue can be combined in various proportions to obtain any colour in the visible spectrum. Levels of R, G, and B can each range from 0 to 100 percent of full intensity. Each level is represented by the range of decimal numbers from 0 to 255 (256 levels for each colour).
From Figure 1 we can see that there is a lot of variation in colour spanning from dark blues to yellows and many objects in the image.
By looking at Figure 2 we can see the Red component is the brightest of all the three images as it has the highest value.
Figure 3 we can infer that the Green component is the second brightest of all three images as it has the second highest value.
Figure 4 we can infer that the Blue component is the least bright of all three images as it has the lowest value.
From Figure 5 we can see that there is a little of variation in colour spanning from dark blues to yellows and we can see few objects in the image
From Figure 9 we can see that there is minimal variation this could be because there is not many objects or colours in the SVG diagram.

# Question 2
This question splits each of the YCbCr values into separate components. Figure 13, 17 and 21 illustrates the full YCbCr image.
This represents a family of colour spaces used as a part of the colour image pipeline in video and digital photography systems. Y is the luminosity component and Cb and Cr are the blue- difference and red-difference chroma components.
Figures 14, 18 and 22 represent the luminosity this affects the brightness.
From Figure 14 we can infer that there is lots of variation in luminosity as there is great variation in the image itself as it has varying degrees of brightness, as the upper region is brighter than the lower.
Figures 15, 19, 23 represent Cb, the higher the chromium value the purer the blue. Figures 16, 20, 24 represent Cr, the higher the chromium value the purer the red.

# Question 3
In this question we have been asked to reduce the sampling of the Cb and Cr (chromatic components) in the spatial domain by a factor of 8 in both dimensions. This was done by using the imresize() function by dividing by 8 and in both Cb and Cr and then upscaling by a factor of 8 and then comparing the RGB value to a YCbCr value that is converted to RGB2.
As there is not a huge difference even when zoomed in the down sampling, this is because by resizing it this essentially copies every eighth value to each of the matrices and then by combining both the reduced sample components of Cb and Cr to the Y intensity map there is not a lot of lossy compression so the difference in images is negligible to the human eye as demonstrate by Figure 25.

# Question 4
Spatial frequency is a characteristic of any structure that is periodic across position in space. The spatial frequency is a measure of how often sinusoidal components (as determined by the Fourier transform) of the structure repeat per unit of distance.
The 2D DCT was conducted through reading the file then convert the image to grayscale. Next, we perform a 2-D DCT of the grayscale image using the dct2 function. Then we display the transformed image using a logarithmic scale. Notice that most of the energy is in the upper left corner. Finally set values less than magnitude 10 in the DCT matrix to zero.
From Figure 28 and Figure 30 we see similarities in the logarithmic scale of the images this could be because they have a greater variation in colours in comparison to the SVG image. Interestingly the logarithmic scale for the SVG is displayed in an almost light ray fashion this could be because perhaps less colours and the colours that are present are more dominant.
Then further analysing Figure 29 and Figure 30 we see a greater difference as there are more points on the lots of variation image which is expected as it has greater number of colours.

# Question 5
First, we must read the images, then we use HSV as RGB values creates shadows and is more difficult to work with. These values are then split into H S V planes (Figure 34) to analyse which plane shows the best output for the pills. Initially the plan was to sum each of the layers to provide a better view of the output. However, upon doing this the author realised that using just the H plane was the clearest.
Then each HSV layer must be threshold using the binarization method to do this (Figure 35). For successful binarization we need to ensure the value is not to high otherwise we introduce too much noise.
After this then we complement the image and fill the holes for the pills as some are not filled by the method imfill() which is a morphological function which is a shape based filter which fills up the holes.
Then to further fill the holes in then a strel disc is called which represents a disc shape morphological structuring element, which is an essential part of morphological dilation and erosion operations.
The purple image for example Figure 36 illustrates this and provides a clearer view of the pills as opposed to the black and white with gap.
After this we must extract the features, this is used by calling the function regionprops this is very effective as this can extract a lot of detail from a binary image.
Then finally we draw some bounding boxes to highlight the areas detected (Figure 37). Lastly, we show calculations of each count for each difficulty level (Figure 38).
All of the results from pills_easy to pills_extreme were achieved correctly and are demonstrated in the following figures.

# Question 6
The same method was used for question 6 however there were alterations to the binarization values and the size factor for the strel disc factor. This was done as there were different size objects. The outcome was 30, which is one off the correct answer of 29.

# Conclusion
This report successfully achieved tasks 1-5 with all requirements fulfilled. Although only one attempt was made with question 6 MixedeasyPills, this was almost fully achieved. The author believes that with more time and tweaking he would have been able to also successfully complete all of question 6.
Given more time in terms of the approach the author would take would be the following: the background would have to be altered using colour thresholder as there is a different light exposure across the image. Also, perhaps it may have been possible if a different masking function for each pill colour was integrated. And as some of the pills are touching this could be fixed by using methods such as watershed or imerode().
Overall, this was a challenging but rewarding experience and the author has learnt not only how to use more tools in MATLAB but also how to effectively research autonomously.
