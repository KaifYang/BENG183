
# 3D Genome Structure And Hi-C Analysis
1. [Introduction](#231)
2. [3D Chromosome Structure](#232)<br>
    2.1. [Chromosomal Territories](#2321)<br>
    2.2. [A/B Compartment](#2322)<br>
    2.3. [Chromatin Loops](#2323)<br>
    2.4. [TADs](#2324)<br>
    2.5. [LADs](#2325)<br>
    2.6. [NADs](#2326)
3. [Hi-C Analysis](#233)
4. [Real-life Example](#234)




## 1. Introduction<a name="231"></a> 

From a 3D perspective, the genome has different genomic conformation, showing different interaction patterns that can be revealed by Hi-C results. 
The Larger scale conformations are structures like: chromosome territories and A/B compartments. 
The smaller scale conformations are structures like: loop, TADs, LADs, etc.



## 2. 3D Chromosome Structure <a name="232"></a>

![](/assets/1-s2.0-S1360138518300827-gr1b2_lrg.jpg)
[Figure1](https://doi.org/10.1016/j.tplants.2018.03.014). Schematic Representation of Chromosome Conformation Capture (3C) and 3C-Derived Methods. These methods help to elucidate nuclear organization by detecting physical interactions between genetic elements located throughout the genome. Abbreviations: IP, immunoprecipitation; RE, restriction enzyme. **Figure by Sotelo-Silveira, Mariana, et al. Trends in Plant Science (2018).**

To better understand the difference between these methods, I'd like to distingush them between the following couple of aspects:

#### 1) Large Conformations - Chromosomal Territories<a name="2321"></a>
Each chromosome occupies specific regions of the nucleus, forming individual territories and rarely intermix. As a result, the interaction between loci on the same chromosome is more frequent. The chromosomal territory helps regulate gene expression by redistributing genes and co-localizing genes with their transcription machinery.

#### 2) Large Conformations - A/B Compartments<a name="2322"></a>
The whole genome can be separated into two self-interacting spatial compartments: A and B. Usually, the A compartments tend to be gene-rich and contain histone markers for active transcription. In other words, A compartments are open and expression-active chromatins. B compartments, on the other hand, tend to be gene-poor and contain histone markers for gene silencing. In general, B compartments are closed and expression-inactive chromatins. Usually, we expect interactions between loci to occur within the same compartment. Regions in compartment A tend to interact with regions in compartment A, and regions in compartment B tend to interact with regions in compartment B. 

#### 3) Small Conformations - Chromatin Loops<a name="2323"></a>
Genome forms a loop structure to bring together two far away elements to a spatial proximity in order to facilitate regulatory effect.
A loop is a site where a protein specifically binds to two different sequences in the genome. As a result, we can see strong associations/interactions between these sites. 

#### 4) Small Conformations - Topologically Associating Domains<a name="2324"></a>
TADs are self-interacting genomic regions. DNA sequences interact with each other more frequently within TADs. Many studies indicate that TADs restrict interactions of regulatory sequences to their target genes. Moreover, TAD boundaries are associated with high CTCF binding and more frequent appearance of certain genes such as the housekeeping genes. However, the function of TADs is still not fully understood and we need more research. According to the computer simulation, we find that chromatin loop extrusion can help generate TADs through cohesin motors.

#### 5) Small Conformations - Lamin Associated Domains<a name="2325"></a>
Genomic regions that are adjacent to the nuclear lamina, in which DNA heavily interacts with NL and form a condensed chromatin layer. LADs are associated with gene repression because the post-translational histone modification, H3K27me3, is enriched in LADs chromatin. 


#### 6) Small Conformations - Nucleolar Associated Domains<a name="2326"></a>
NADs are regions in which DNA sequences interact with nucleolus. This structure, frequently including large multi-gene clusters, usually express characteristics of constitutive heterochromatin and are correlated with low gene expression. The part of the chromosome that contains ribosomal RNA genes is usually inside the NADs. NADs can be further differentiated into two types. Type I NADs are usually associated with both nucleolar periphery and nuclear lamina. This type of NADs are usually constitutive heterochromatin, leading to late DNA replication and little gene expression. Type II NADs are usually associated with nucleoli. This type of NADs, in contrast, leads to earlier DNA replication and greater gene expression. (Saksouk et al.)

## 2.3.3 Hi-C<a name="233"></a>
Hi-C is the highest through-put version of 3C-derived technologies. Due to the decreasing cost of 2nd generation sequencing, hi-c is widely used.

The principle of Hi-C can be illustrated as:
![](/assets/hic.gif)


##### Hi-C critical steps [8] 
- Fixation: keep DNA conformed
- Digestion: enzyme frequency and penetratin
- Fill-in: biotin for junction enrichment
- Ligation: freeze interactions in sequence
- Biotin removal: junctions only
- Fragment size: small fragments sequence better
- Adapter ligation: paired-end and indexing
- PCR: create enough material for flow cell

##### Hi-C derived techniques 
- Hi-C original: [Lieberman-Aiden et al., Science 2010](doi: 10.1126/science.1181369)
- Hi-C 1.0: [Belton-JM et al., Methods 2012](doi: 10.1016/j.ymeth.2012.05.001)
- In situ Hi-C: [Rao et al., Cell 2014](doi: 10.1016/j.cell.2014.11.021)
- Single cell Hi-C: [Nagano et al., Genome Biology 2015](https://doi.org/10.1186/s13059-015-0753-7)
- DNase Hi-C [Ma, Wenxiu, Methods et al](https://www.ncbi.nlm.nih.gov/pubmed/25437436)
- Hi-C 2.0: [Belaghzal et al., Methods 2017](https://www.ncbi.nlm.nih.gov/pubmed/28435001)
- DLO-Hi-C: [Lin et al., Nature Genetics 2018](https://doi.org/10.1038/s41588-018-0111-2)
- Hi-C improving: [Golloshi et al., Methods 2018](https://www.biorxiv.org/content/biorxiv/early/2018/02/13/264515.full.pdf)
- Arima 1-day Hi-C: [Ghurye et al., BioRxiv 2018](https://www.biorxiv.org/content/early/2018/02/07/261149)

## 2.3.4 ChIA-PET<a name="234"></a> 
ChIA-PET is another method that combines ChIP and pair-end sequencing to analysis the chromtin interaction. It allows for targeted binding factors such as: estrogen receptor alpha, CTCF-mediated loops, RNA polymerase II, and a combination of key architectural factors. on the one hand, it has the benefit of achieving a higher resolution compared to Hi-C, as only ligation products involving the immunoprecipitated molecule are sequenced, on the other hand, ChIA-PET has systematic biases due to ChIP process:
- Only one type of binding factor selected
- Different antibodies
- ChIP conditions


## 2.3.5 Selected methods comparison<a name="235"></a> 
<table>
 <tbody>
    <tr>
        <th>Method</td>
        <th>Targets</td>
        <th>Resolution</td>
        <th>Notes</td>
    </tr>
    <tr>
        <td>3C <a href="http://refhub.elsevier.com/S2001-0370(17)30093-4/rf0535">[3]</a></td>
        <td>one-vs-one</td>
        <td>~1–10 kb<br></td>
        <td><ul><li>Sequence of bait locus must be known</li><li>Easy data analysis</li><li>Low throughput</li></ul></td>
    </tr>
    <tr>
    <td>4C <a href="http://refhub.elsevier.com/S2001-0370(17)30093-4/rf0545">[4]</a></td>
    <td>one-vs-all</td>
    <td>~2 kb</td>
    <td><ul><li>Sequence of bait locus must be known</li><li>Detects novel contacts</li><li>Long-range contacts</li></ul></td>
    </tr>
    <tr>
    <td>5C <a href="http://refhub.elsevier.com/S2001-0370(17)30093-4/rf0550">[5]</a></td>
    <td>many-vs-many</td>
    <td>~1 kb</td>
    <td><ul><li>High dynamic range</li><li>Complete contact map of a locus</li><li>3C with ligation-mediated amplification (LMA) of a ‘carbon copy’ library of oligos designed across restriction fragment junctions of interest
3C</li></ul></td>
    </tr>
    <tr>
    <td>Hi-C <a href="http://refhub.elsevier.com/S2001-0370(17)30093-4/rf0300">[6]</a></td>
    <td>all-vs-all</td>
    <td>0.1–1 Mb</td>
    <td><ul><li>Genome-wide nucleosome core positioning</li><li>Relative low resolution</li><li>High cost</li></ul></td>
    </tr>
    <tr>
    <td>ChIA-PET <a href="http://refhub.elsevier.com/S0168-9525(15)00063-3/sbref1405">[7]</a></td>
    <td>Interaction of whole genome mediated by protein</td>
    <td>Depends on read depth and the size of the genome region bound by the protein of interest</td>
    <td><ul><li>Lower noise with ChIP</li><li>Biased method since selected protein</li></ul></td>
    </tr>
 </tbody>
</table>

















# Referrence
[1] Schmitt, Anthony D., Ming Hu, and Bing Ren. "Genome-wide mapping and analysis of chromosome architecture." Nature reviews Molecular cell biology 17.12 (2016): 743.<br>

[2] Risca, Viviana I., and William J. Greenleaf. "Unraveling the 3D genome: genomics tools for multiscale exploration." Trends in Genetics 31.7 (2015): 357-372.<br>

[3] Dekker J, Rippe K, Dekker M, Kleckner N. Capturing chromosome conformation. Science 2002;295(5558):1306–11.<br>

[4] Simonis M, Klous P, Homminga I, Galjaard RJ, Rijkers EJ, Grosveld F, et al. High-res- olution identification of balanced and complex chromosomal rearrangements by 4C technology. Nature Methods 2009;6(11):837–42.<br>

[5] Dostie J, Richmond TA, Arnaout RA, Selzer RR, Lee WL, Honan TA, et al. Chromo- some Conformation Capture Carbon Copy (5C): a massively parallel solution for mapping interactions between genomic elements. Genome Res 2006;16(10): 1299–309.<br>

[6] Lieberman-Aiden E, van Berkum NL, Williams L, Imakaev M, Ragoczy T, Telling A, et al. Comprehensive mapping of long-range interactions reveals folding principles of the human genome. Science 2009;326(5950):289–93.<br>

[7] Fullwood, M.J. et al. (2009) An oestrogen-receptor-alpha-bound human chromatin interactome. Nature 462, 58–64.<br>

[8] https://github.com/hms-dbmi/hic-data-analysis-bootcamp/blob/master/HiC-Protocol.pptx.

