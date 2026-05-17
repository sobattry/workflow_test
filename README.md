# workflow_test

## Bulk Donwload Instruction

### 1. Download all 5 parts using a loop
BASE_URL="https://github.com/sobattry/workflow_test/releases/download/torch-2.0.1-cu118-25973161149"
for suffix in {a..e}; do
  wget "${BASE_URL}/torch-2.0.1.whl.part_a${suffix}"
done

### Or
wget https://github.com/sobattry/workflow_test/releases/download/torch-2.0.1-cu118-25973161149/torch-2.0.1.whl.part_aa
wget https://github.com/sobattry/workflow_test/releases/download/torch-2.0.1-cu118-25973161149/torch-2.0.1.whl.part_ab
wget https://github.com/sobattry/workflow_test/releases/download/torch-2.0.1-cu118-25973161149/torch-2.0.1.whl.part_ac
wget https://github.com/sobattry/workflow_test/releases/download/torch-2.0.1-cu118-25973161149/torch-2.0.1.whl.part_ad
wget https://github.com/sobattry/workflow_test/releases/download/torch-2.0.1-cu118-25973161149/torch-2.0.1.whl.part_ae

### 2. Recombine the parts into the original wheel
cat torch-2.0.1.whl.part_* > torch-2.0.1+cu118-cp311-cp311-linux_x86_64.whl

### Or
cat torch-2.0.1.whl.part_aa torch-2.0.1.whl.part_ab torch-2.0.1.whl.part_ac torch-2.0.1.whl.part_ad torch-2.0.1.whl.part_ae > torch-2.0.1+cu118-cp311-cp311-linux_x86_64.whl
### 3. (Optional) Clean up the split parts
rm torch-2.0.1.whl.part_*

