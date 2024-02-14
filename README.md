# K-Compress: Image Compression using K-Means

## About <a name="about"></a>


## Directory Structure <a name="directory-structure"></a>

```
├── input_image/                              <- Folder for input image in png format
├── compressed_image/                         <- Folder for compressed image
├── Image Compression using KMeans.ipynb/     <- Source code for the project
├── snapshots                                 <- Project's results on sample image
├── LICENSE                                   <- Project's License
├── README.md                                 <- The top-level README for developers using this project
```

## Table of Contents <a name="table-of-contents"></a>

1. [About](#about)
2. [Directory Structure](#directory-structure)
3. [Table of Contents](#table-of-contents)
4. [Background & Approach](#background)
5. [Results](#results)
6. [License](#license)
7. [Support & Contact](#support-contact)


## Background & Approach: <a name="background"></a>

24-bit RGB images consist of pixels, each represented by three 8-bit unsigned integers, totaling 24 bits. These integers range from 0 to 255 and denote the intensities of red, green, and blue, which collectively determine the color of the pixel.

### Approach:

These 24-bit images can contain thousands of colors. The idea is to reduce the color depth of 24-bit images to a mere 16 colors. This approach seeks to strike a balance between preserving image quality and minimizing file size, thereby exploring the tradeoff inherent in compressing image data.

This reduction enables efficient image representation and storage. Instead of storing thousands of colors, only a list of 16 selected RGB colors and a mapping of each pixel to the corresponding index of these colors need to be saved post-compression. Remarkably, merely 4 bits are required to represent the 16 possibilities, drastically reducing the storage footprint.

To overcome the limitation of Python where atomicity is 1 byte, a workaround was implemented. Since it's not possible to store 4 bits directly, they were merged to form 1 byte. Later, during the separation process, these bytes were divided back into their constituent 4 bits. This approach facilitated the handling of the compressed data efficiently within the Python environment.

Work was also undertaken to support PNG format due to its lossless nature. Unlike JPEG, which is lossy, saving the compressed image as JPEG would risk losing the indices. Therefore, saving the color map as PNG was adopted to preserve all the necessary information. Consequently, the input image was also required to be in PNG format for accurate comparison since JPEG compression might alter the image data.


### How are those 16 colors chosen?

The KMeans algorithm is employed to select 16 representative colors for compressing the image. Each pixel in the original image is treated as a data sample, and K-Means is utilized to identify 16 colors that effectively group (cluster) the pixels in the 3-dimensional RGB space. Subsequently, these cluster centroids, serving as the 16 chosen colors, are used to substitute the pixels in the original image, facilitating compression.


## Results <a name="results"></a>

<img width="629" alt="visual-results" src="https://github.com/YuganshG/Image-Compression-using-KMeans/assets/34838617/03ed780b-2f0e-4dad-b69c-2e6ff334e762">
<img width="490" alt="evaluation_results" src="https://github.com/YuganshG/Image-Compression-using-KMeans/assets/34838617/6722f542-2a8b-4bc1-bb35-24775468f44d">


## License <a name="license"></a>
This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](https://github.com/YuganshG/Image-Compression-using-KMeans/blob/main/LICENSE) file for details.

## Support & Contact <a name="support-contact"></a>
If you encounter any issues, have questions or just want to chat about machine learning? Feel free to [email](yugansh.goyal101@gmail.com) me or connect with me on [LinkedIn](https://www.linkedin.com/in/yuganshgoyal/).
