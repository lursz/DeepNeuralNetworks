# Deep Neural Networks
This repository contains Deep Neural Networks course.

<!-- # Final project  -->
<!-- The final project included creating a . You can find it [here](). -->

# Table of contents

| Description  | Lecture | Assignment |
| ------------- | ------------- | ------------- |
| 01. Introduction | [lecture1](Lectures/lecture1.pdf)  | [lab1](/1_Introduction/) |
| 02. Overfitting and Underfitting | [lecture2](Lectures/lecture2.pdf)  | [lab2](/2_Overfitting_and_Underfitting/) |
| 03. Convolutional Neural Networks | [lecture3](Lectures/lecture3.pdf)  | [lab3](/3_Convolutional_Neural_Networks/) |
| 04. CNN augmentation | [lecture4](Lectures/lecture4.pdf)  | [lab4](/4_CNN_Generalization_&_Augumentation/) |
| 05. Transfer learning | [lecture5](Lectures/lecture5.pdf)  | [lab5](/5_Transfer_Learning/) |
| 06. Learning visualization | [lecture6](Lectures/lecture6.pdf)  | [lab6](/6_Visualization/) |
| 07. Recurrent neural networks | [lecture7](Lectures/lecture7.pdf)  | [lab7](/7_RNN/) |
| 08. Generative adversarial networks | [lecture8](Lectures/lecture8.pdf)  | [lab8](/8_GAN/) |
| 09. Transformer networks | [lecture9](Lectures/lecture9.pdf)  | [lab9](/9_Transformer/) |


# Troubleshooting
Acquaint yourself with the following section in case you encounter any issues.
### Troubles installing TensorFlow on GPU

<details>
<summary>TensorFlow on GPU Guide</summary>
</br>


```python
1. In condas base env run:
	conda install nvidia::cuda
	conda install anaconda::cudnn
2. Export cuda path (anaconda / miniconda):
	LD_LIBRARY_PATH=$HOME/anaconda3/lib:$LD_LIBRARY_PATH
		or
	LD_LIBRARY_PATH=$HOME/miniconda3/lib:$LD_LIBRARY_PATH
3. Create new conda env and install tensorflow:
	pip install tensorflow[and-cuda]
4. Verify with:
	python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))"
5. Enjoy!
```
</details>


<details>
<summary>(In case guide above fails) TensorFlow on GPU Comprehensive Guide</summary>
</br>


```python
Windows 10 or 11 Only...

1. Install Nvidia Driver 
	a. Download Automatic Driver Updates File form here :-
    	https://www.nvidia.com/en-in/geforce/drivers/
        It will automatically finds best suitable driver for your system
      
2. Install wsl(Windows Subsystem for linux) on your windows 10 or greater
	a. open powershell or cmd in adminstrator
    b. wsl --install
    c. Enter credentials and usernames(Imp to remember)
    d. Reboot System
 
3. Install Anaconda
	a. Open cmd as user not adminstrator and type wsl
    b. type "curl https://repo.anaconda.com/archive/Anaconda3-2021.11-Linux-x86_64.sh --output anaconda.sh"
    c. type "bash anaconda.sh" in wsl
    d. Enter and say yes to all like[Do you approve the license terms? [yes|no], Do you wish the installer to initialize Anaconda3]
    e. activate installation by type "source ~/.bashrc"
    f. Now you will get (base)
    
4. Environment and Cuda, Cudnn(GO on pasting every line in (base))
	a. conda create --name tf python=3.9
    b. conda activate tf
    c. nvidia-smi (To Check GPU )
    d. conda install -c conda-forge cudatoolkit=11.8.0
    e. pip install nvidia-cudnn-cu11==8.6.0.163
    f. mkdir -p $CONDA_PREFIX/etc/conda/activate.d
    g. CUDNN_PATH=$(dirname $(python -c "import nvidia.cudnn;print(nvidia.cudnn.__file__)"))
    h. echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_PREFIX/lib/:$CUDNN_PATH/lib' > $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
	
5. Installing Tensorflow in env
	a. pip install --upgrade pip
    b. pip install tensorflow==2.14.1
    c. python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))" (To Check GPU)
    
    
Problems:-
	a. No GPU detected after running 5. and c. command:-
    	Rerun 4. g. and h. every time when you launch or activate environment i.e tf
```
</details>
