# pix2pix-tensorflow-spell
Experimentation with pix2pix running on spell<br/>

<b>Upload training data on spell ressources</b><br/>
spell upload data<br/>
<br/>
<b>Training pix2pix with the data</b><br/>
spell run --machine-type V100 --framework tensorflow "python pix2pix.py --mode train --input_dir data/train --output_dir ckpt --which_direction AtoB --max_epochs 200" -m uploads/data
