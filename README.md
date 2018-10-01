# pix2pix-tensorflow-spell
Experimentation with pix2pix running on spell<br/>

<b>Upload training data on spell ressources</b><br/>
spell upload data<br/>
<br/>
<b>Training pix2pix with the data</b><br/>
spell run --machine-type V100 --framework tensorflow "python pix2pix.py --mode train --input_dir data/train --output_dir ckpt --which_direction BtoA --max_epochs 200" -m uploads/data
<br/>
<br/>
<b>Download the model</b><br/>
spell cp runs/RUN_ID/ckpt<br/>
<br/>
<b>Convert model to tensorflow.js/ml5js bin</b><br/>
'''with python3.7'''<br/>
python export-checkpoint.py --checkpoint ckpt --output_file model_AtoB.bin
