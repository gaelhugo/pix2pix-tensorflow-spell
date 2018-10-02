# pix2pix-tensorflow-spell
Experimentation with pix2pix running on spell<br/>

<b>Upload training data on spell ressources</b><br/>
spell upload sticks<br/>
<br/>
<b>Training pix2pix with the data</b><br/>
spell run --machine-type V100 --framework tensorflow "python pix2pix.py --mode train --input_dir sticks --output_dir ckpt --which_direction AtoB --max_epochs 200 --ngf 32 --ndf 32" -m uploads/sticks
<br/>
--ngf 32 --ndf 32 seems to work faster ?
<br/>
<br/>
<b>Download the model</b><br/>
spell cp runs/RUN_ID/ckpt<br/>
<br/>
<b>Convert model to tensorflow.js/ml5js bin</b><br/>
'''with python3.7'''<br/>
if issue with tensorflow : pip install --upgrade https://storage.googleapis.com/tensorflow/mac/cpu/tensorflow-0.12.0-py3-none-any.whl<br/><br/>
python export-checkpoint.py --checkpoint ckpt --output_file model_AtoB.bin
