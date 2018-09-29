# The Pyramid sketch framework


## Introduction

### VLDB version
The *sketch* is a probabilistic data structure, and is used to store and query the frequency of any item in a given multiset. Due to its memory efficiency, it has been applied to various fields in computer science, such as streaming database, network traffic measurement, etc. The key factors of sketches for data streams are accuracy, speed, and memory usage. There are various sketches in the literature, but they cannot achieve both high accuracy and high speed using limited memory, especially for skewed datasets. To address this issue, we propose a sketch framework, *the Pyramid sketch*, which can significantly improve accuracy as well as update and query speed. To verify the effectiveness and efficiency of our framework, we applied our framework to four typical sketches. Extensive experimental results show that the accuracy is improved up to 3.50 times, while the speed is improved up to 2.10 times.


### ToN version
*Sketch* is a probabilistic data structure, and is used to store and query the frequency of any item in a given multiset. Due to its high memory efficiency, it has been applied to various fields in computer science, such as stream database, network traffic measurement, etc. The key metrics of sketches for data streams are accuracy, speed, and memory usage. Various sketches have been proposed, but they cannot achieve both high accuracy and high speed using limited memory, especially for skewed datasets. To address this issue, we propose a sketch framework, *the Pyramid sketch*, which can significantly improve accuracy as well as update and query speed. To verify the effectiveness and efficiency of our framework, we applied our framework to four typical sketches. Extensive experimental results show that the accuracy is improved up to 3.50 times, while the speed is improved up to 2.10 times. We have released our source codes at Github 


## About the source codes, dataset and parameters setting

The source code contains the C++ implementation of the CM, CU, C, A sketch and PCM, PCU, PC, PA sketch (using our Pyramid sketch framework). We complete these codes on Linux 14.04.5 and compile successfully using g++ 4.8.4. 

The file stream.dat is the subset of one of the encrypted IP traces used in experiments. This small dataset contains 1M items totally and 193,894 distinct items. The maximum frequency of those items is 4426. The full dataset can be download on our homepage (http://net.pku.edu.cn/~yangtong/uploads/stream_full.dat).

We set the memory allocated to each sketch 0.1MB. The other parameters setting is the same as mentioned in the paper.


## How to run

Suppose you've already cloned the respository and start from the `Pyramid_Sketch_Framework` directory.

You just need:

	$ make 
	$ ./pyramid


## Output format

Our program will print the throughput of insertion and query of these eight sketches and the ARE and AAE of these sketches. Note that to obtain convincing results of the throughput, you are supposed to set the micro "testcycles" in the main.cpp to a larger value (e.g. 100) and run the program on a Linux server.

## Publication

[(VLDB17) Pyramid Sketch: a Sketch Framework for Frequency Estimation of Data Streams](http://www.zhouy.me/paper/pyramid-vldb17.pdf)

[Technical Report](https://github.com/zhouyangpkuer/Pyramid_Sketch_Framework/blob/master/technical_report.pdf)
