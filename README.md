# K-Compress: Image Compression using K-Means

## About <a name="about"></a>


## Table of Contents <a name="table-of-contents"></a>

1. [About](#about)
2. [Table of Contents](#table-of-contents)
3. [Background & Approach](#background)
4. [Results](#results)
5. [License](#license)
6. [Support & Contact](#support-contact)


## Background & Approach: <a name="background"></a>

24-bit RGB images are images in which each pixel is represented by three 8-bit unsigned integers (thus, 24 bits total) (ranging from 0 to 255) specifying the intensities of red, green, and blue that form the color for the pixel.

### Approach:

8-bit images can contain thousands of colors. Here, the idea is to represent those images with just 16 colors The number of colors used to represent the image is a tradeoff between the compressed image quality and its size

By making this reduction, it is possible to represent and store an image in an efficient way. Because instead of storing all those thousands of colors, all that would be needed to be stored after compression is the list of those selected 16 RGB colors and a list that maps each pixel in the image to the corresponding index of 16 selected colors Note that only 4 bits are necessary to represent 16 possibilities

### How are those 16 colors chosen?

KMeans algorithm is used to select 16 colors that will be used to represent the compressed image. Each pixel in the original image is treated as a data sample and then using K-Means to find the 16 colors that best group (cluster) the pixels in the 3- dimensional RGB space. Once the cluster centroids have been found, then those centroids (16 colors) are used to replace the pixels in the original image


## License <a name="license"></a>
This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](https://github.com/YuganshG/Image-Compression-using-KMeans/blob/main/LICENSE) file for details.

## Support & Contact <a name="support-contact"></a>
If you encounter any issues, have questions or just want to chat about machine learning? Feel free to [email](yugansh.goyal101@gmail.com) me or connect with me on [LinkedIn](https://www.linkedin.com/in/yuganshgoyal/).
