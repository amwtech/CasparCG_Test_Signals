# CasparCG_Test_Signals
This repository holds video test signals to assist checking temporal processing of PAL (576 line) and 1080 HD material in a 25/50 Hz timebase in a CasparCG server. The files have been zipped to significantly reduce the volume of storage needed. The signals are also suitable for other video servers or software processes that manipulate PAL or HD video.

Each test video contains 15 seconds of content. Most of each screen is black apart from burnt-in timecode and a small patch of lines that are tv field grouped. The patch of lines move diagonally downwards over 1 second. The movement repeats for 25 seconds through the rest of the video. Recording the SDI output, for example, from a Decklink or Bluefish card, enables the source frame(s) used for each output frame to be displayed.

There are five sets of signals, each created with a different timebase. Each signal is available as a zipped uncompressed 8-bit test and an AVC 100 Mbit intra frame compressed version. The temporal test can only work fully if compressed versions use an intra codec. There are two audio tracks with continuous tone of 330 Hz. This frequency allows seamless looping of the test signal when testing for audio issues. It is very important that any replacement tone has a non-integer number of cycles per frame so that dropped or repeated frames can be detected, but there must be an integer number of cycles in the 5 second clip.

![Source_Patterns](https://user-images.githubusercontent.com/86308191/168492129-9ea3a426-b216-4b24-915b-cedd15c3d6a3.png)

The image above shows a magnified example of the three patterns used in the test signals. The yellow text identifies the scan type used in the associated soure file. The i25 uses two blocks of lines, the number below the block identifying the target output field in an interlaced operation. The p25 and p50 patterns also have 1 scan-line high fingers that will show on field 1 (label X) and field 2 (label Y) when displayed on an interlaced system. The frame number within a 1 second block is centered below the block or blocks of lines.

![i25_processed](https://user-images.githubusercontent.com/86308191/168492448-8bee26ee-bd94-4bc0-a421-ce2b2c73b57a.png)

The still image above shows the block display when the signal output processing to SDI gets the interlace timing wrong. The ouput frame has been created from field 2 of source frame 1, and field 1 of source frame 2. Each block has been vertically displayed to place the content in the correct position for the output interlace lines. This is shown by the grey lines above and below the the blocks, the grey created by an interpolation to the black background.

__Test set 1__

File names: CCGT_01_Src_576i25.mov and CCGT_01__Src_576i25_ProRes422.mov

Each frame is interlaced with a total of 576 active lines. CasparCG channels should pass this signal transparently when the channel mode is set as PAL. 

__Test set 2__

File names: CCGT_01_Src_576p25.mov and CCGT_01__Src_576p25_ProRes422.mov

Each frame is created with a total of 576 active lines for progressive scan output. CasparCG channels should pass this signal transparently when the channel mode is set as PAL.

__Test set 3__ 

File names: CCGT_01_Src_1080i25.mov and CCGT_01_Src_1080i25_AVCIntra100.mxf

Each frame is interlaced with a total of 1080 active lines. CasparCG channels should pass this signal transparently when the channel mode is set as 1080i5000.

__Test set 4__

File names: CCGT_01_Src_1080p25.mov and CCGT_01_Src_1080p25_AVCIntra100.mxf

Each frame is progressive scanned with a total of 1080 active lines. CasparCG channels should pass this signal transparently when the channel mode is set as 1080p2500. 

__Test set 5__ 

File names: CCGT_01_Src_1080p50.mov and CCGT_01_Src_1080p50_AVCIntra100.mxf

Each frame is progressive scanned with a total of 1080 active lines. CasparCG channels should pass this signal transparently when the channel mode is set as 1080p5000.
