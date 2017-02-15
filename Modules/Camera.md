#Camera

Slew rate

Lens shading correction (LC) module - multiplying RGB signals with 2D correction function F(x,y)

Defect Correction - diff normal and defective pixels - fixes pixels on the fly based on nearest color neighbors.

Auto white balance algorithm -

RGB to YUV conversion

transform coding

Perceptual Coding - transforms raw data to a domain that more accurate reflects the information content.
Example: sound files as freq. spectrum instead of amplitude levels over time; corresponds to human audio perception more accurately.

MP3 - compression becomes selective loss of least significant data instead of losing data across board.

More about better representation of data instead of discarding data.

Rate-distortion theory draws on Bayesian estimation and decision theory in order to model perceptual distortion and even aesthetic judgement.

Two basic lossy compression schemes:
	1. Lossy transform codecs.
	2. Lossy predictive codecs.

Ideally, lossy compression is transparent (verified via ABX test).

Video can be compressed ~ (100:1)
Audio  (10:1)
Images (10:1), but more noticeable on closer inspection.

Bitrate peeling -

Transform Coding (example: JPEG)
typically lossy, for "natural" data such as audio signals or photographic images.

JPEG - examines small blocks of the image and "averages out" the color using a discrete cosine transform to form an image with far fewer colors in total

Portable Network Graphics (PNG)

Tagged Image File Format (TIFF)

Apple Lossless (ALAC - Apple Lossless Audio Codec)

Cons of lossless compression:

and for any lossless data compression algorithm that makes at least one file smaller, there will be at least one file that it makes larger. This is easily proven with elementary mathematics using a counting argument, as follows:
1. Assume that each file is represented as a string of bits of some arbitrary length.
2. Suppose that there is a compression algorithm that transforms every file into an output file that is no longer than the original file, and that at least one file will be compressed into an output file that is shorter than the original file.
3. Let M be the least number such that there is a file F with length M bits that compresses to something shorter. Let N be the length (in bits) of the compressed version of F.
4. Because N<M, every file of length N keeps its size during compression. There are 2N such files. Together withF, this makes 2N+1 files that all compress into one of the 2N files of length N.
5. But 2N is smaller than 2N+1, so by the pigeonhole principle there must be some file of length N that is simultaneously the output of the compression function on two different inputs. That file cannot be decompressed reliably (which of the two originals should that yield?), which contradicts the assumption that the algorithm was lossless.
6. We must therefore conclude that our original hypothesis (that the compression function makes no file longer) is necessarily untrue.

Pigeonhole principle
