# Run-TransE-on-FB15K
<h2>Summary</h2>
In windows environment, Run the TransE model on the FB15K data set

<h2>Preparation</h2>
<li>Compatible python + cuda + pytorch</li>
<li>这里巨坑，我走了太多弯路，这三个的版本必须严格匹配才能跑。最大的一个坑就是，python37 直接下torch默认下载的是给CPU用的，必须找给cuda用的，还得注意这三个的版本严格兼容。最后我是去网上一元钱租了一个GPU做的，网上租的GPU这三个都是适配好的。</li>
<li>我用的是python38 + cuda11.8 + pytorch2.0.0</li>

<h2>Check the environment</h2>

<li>Import pytorch, Type in the terminal:</li>

```
python
import torch
```
<li>Check out the version of torch</li>

```
print(torch.__version__)
```
<p>The version number returned here if "+cpu" is present there is an error, it should be "+cu"</p>
<p>What I'm returning here is "2.0.0+cu118"</p>
<li>Check whether torch is compatible with cuda</li>

```
troch.cuda.is_available()
```
<p>If True is returned, proceed</p>

```
exit()
```
<h2>Quick start</h2>

<li>Download OpenKE source code</li>

```
git clone https://github.com/thunlp/OpenKE.git
```
<li>Go to the openke directory</li>

```
cd OpenKE
cd openke
```
<li>Compiling C++ files</li>

```
bash make.sh
```
<li>Go to superior directory</li>

```
cd ../
```
<li>Create the directory "checkpoint"</li>

```
mkdir checkpoint
```
<h3>Training</h3>
<li> Run the TransE model on the FB15K data set</li>

```
cp examples/train_transe_FB15K237.py ./
python train_transe_FB15K237.py
```
<p>Other models can be trained with similar commands</p>
