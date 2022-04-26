# CasparCG_Test_Signals
This repository holds video test signals to assist checking temporal processing of 1080 HD material in a 25/50 Hz timebase within a CasparCG server. The files have been zipped to significantly reduce the volume of storage needed. The signals are also suitable for other video servers or software processes that manipulate HD video.

Each test video contains 25 seconds of content. Most of each screen is black apart from burnt-in timecode and a small patch of lines that are tv field grouped. The patch of lines move diagonally downwards over 1 second. The movement repeats for 25 seconds through the rest of the video. Recording the SDI output, for example, from a Decklink or Bluefish card enables the content of each output frame to be checked for it's source frame data.

There are 3 sets of signals, each created with a different timebase. Each signal is available as a zipped uncompressed 8-bit test and an AVC 100 Mbit intra frame compressed version. The temporal test can only work if compressed versions use an intra codec. There are two audio tracks with continuous tone of around 313.13 Hz. It is very important that any replacement tone has a non-integer number of cycles per frame so that dropped or repeated frames can be detected.

__Test set 1__ 

File names: CCGRecTest_1080i25_01.mov and CCGRecTest_1080i25_01-1080i25_AVC-Intra_100.mxf

Each frame is interlaced with a total of 1080 active lines. CasparCG channels should pass this signal transparently when the channel mode is set as 1080i5000. Each source frame has two sets of lines, placed on alternate lines of the source graphic to create the interlace. Immediately below the block is a centred number indicating which field contains the block of lines. Lower in the frame is a centred number that shows the source frame number.

__Test set 2__

File names: CCGRecTest_1080p25_01.mov and CCGRecTest_1080p25_01-1080p25 AVC-Intra 100.mxf

Each frame is progressive scanned with a total of 1080 active lines. CasparCG channels should pass this signal transparently when the channel mode is set as 1080p2500. Each source frame has two sets of lines that overlap in the central area of a block. There are fine fingers to the left and right of the block that should appear on field 1 (left of block of lines) or field 2 (right of block of lines) if the video is de-interlaced. Immediately below the block is a centred number indicating the frame number withn a one second burst of frames. If the decoded output of a test shows a solid block where the number is to the right of block centre the block was extracted from just the lines that would be field 1 in an interlaced display. A correct transfer of the progressive frame will have a block with fingers to the left and right of the block, with the source frame ID centred below the block.

__Test set 3__ 

File names: CCGRecTest_1080p50_01.mov and CCGRecTest_1080p50_01-1080p50 AVC-Intra 100.mxf

Each frame is progressive scanned with a total of 1080 active lines. CasparCG channels should pass this signal transparently when the channel mode is set as 1080p5000. Each source frame has two sets of lines that overlap in the central area of a block. There are fine fingers to the left and right of the block that should appear on field 1 (left of block of lines) or field 2 (right of block of lines) if the video is de-interlaced. Immediately below the block is a centred number indicating the frame number withn a one second burst of frames. If the decoded output of a test shows a solid block where the number is to the right of block centre the block was extracted from just the lines that would be field 1 in an interlaced display. A correct transfer of the progressive frame will have a block with fingers to the left and right of the block, with the source frame ID centred below the block.
