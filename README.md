# 样本与方法

### 样本的准备
对于BS-L001_81和BS-L001_82，我们使用了reformat.sh tossbrokenreads=t verifypaired=t allowidenticalnames=t qin=33 minlength=10 trimreaddescription=t 命令过滤了原始fastq文件。Evo和Illumina数据未做处理

### 参考基因组
对于Evo和Illumina样本，我们使用E.coli ATCC 8739 参考基因组。对于 BS-L001样本，我们使用了10种Genebank genome混合而成，它们分别为：

- Bacillus cereus https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_000008005.1/
- Bifidobacterium adolescentis https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_000010425.1/
- Clostridium beijerinckii https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_000767745.1/
- Deinococcus radiodurans ATCC 13939 https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_020546685.1/
- Enterococcus faecalis T5 https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_000393015.1/
- Lactobacillus gasseri https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_000014425.1/
- Cereibacter sphaeroides 2.4.1 https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_003324715.1/
- Staphylococcus epidermidis (ATCC 12228) https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_009873455.1/
- Streptococcus mutans UA-159 https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_024762155.1/
- Escherichia coli str. K-12 substr. MG1655 https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_000005845.2/

### 比对和过滤
我们使用bwa mem -M命令进行比对，比对之后未去重，使用samtools view -bh -f 3 -F 3852命令过滤比对结果。

### cycle和碱基质量信息的提取
由于时间限制，我们每个样本只使用的100,000个随机位点的cycle和碱基质量信息，我们使用一个in-house脚本提取相关信息，使用R和ggplot2做图
