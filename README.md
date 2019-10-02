# QuadTree
(Please definitely check the bottom part of this file that has titled "IMPORTANT".)

A program that provides filters, and compressions to given ppm file.

# How to compile and run the program:
You will receive an image file on the command line following the -i fl
ag as your input: java Main -i test.ppm.
In addition, support the following 
args:

1. -o <filename> indicates the root name of the output file that your program should write to
2. -c indicates that you should perform image compression
3. -e for edge detection

For example:
java Main -c -i test.ppm -o out will generate 8 compressed images of test.ppm named out-1.ppm,
out-2.ppm, ..., out-8.ppm, where out-1.ppm is the image with the lowest resolution/highest com-
pression and so on. java Main -e -i test.ppm -o out will generate one output image called
out.ppm which is the result of applying edge detection to test.ppm. You may assume that only one
of -c or -e will be given. Order of the 
ags should not matter, i.e. java Main -o out -e -i test.ppm
is equivalent to java Main -e -i test.ppm -o out

# Filters:

1)Edge detection

2)Change average image color to grey scale.

3)Change image to negative.

4)Change image tint: changes average image color corresponding to rgb set which is given by parameter.

Compression:
-Compresses the image(.ppm file) given by user.
-Compression level is detected from some threshold value which is chosen by user.
-Corresponding to threshold value, image is divided into four square regions recursively.
-In addition, the mean squared error of the region is calculated and the algorithm terminates corresponding the level of error against the threshold value.

Output of compression:
-8 different compressed .ppm files are created. (out-1, out-2, out-3...)
-The resolution of original image decreases in the sequence of 8 image. (thresholds have increased by programmer in every compression step).

# IMPORTANT:
-The difference between 8 images cannot be detected from shapes of images because of the small threshold values.
-Hence, program prints to console count of divisions in every image to allow users follow up the different compression levels.
-If you want to see the difference between images easily, you can give larger threshold values(1000, 2000, 5000..) in compress method calls in the Main class.

