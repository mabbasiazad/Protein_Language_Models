### Tasks done by ESM2

[ESM-2](https://www.biorxiv.org/content/10.1101/2022.07.20.500902v1) is a pLM trained using unsupervied masked language modelling on 250 Million protein sequences by researchers at [Facebook AI Research (FAIR)](https://www.biorxiv.org/content/10.1101/2022.07.20.500902v1).

It is available in several sizes, ranging from 8 Million to 15 Billion parameters. The smaller models are suitable for various sequence and token classification tasks. The FAIR team also adapted the 3 Billion parameter version into the ESMFold protein structure prediction algorithm.

In this repository, I have used the ESM2 model for the following tasks:

- **Masked Language Modeling**

  [mutation_effect_enzyme](https://github.com/mabbasiazad/Protein_Language_Models/blob/master/mutation_effect_enzyme.ipynb) calculates the mutation score introduced in the paper [Language models enable zero-shot prediction of the effects of mutations on protein function](https://www.biorxiv.org/content/10.1101/2021.07.09.450648v2). It ranks the functional impact of mutated sequences compared to the original (wild-type) sequence.

- **Sequence Classification**

  - **Training a small model (model_name = `facebook/esm2_t6_8M_UR50D`)**

    [sequence_classification_small](https://github.com/mabbasiazad/Protein_Language_Models/blob/master/sequence_classification_small.ipynb) notebook is about predicting whether a protein is (1) an enzyme, (2) a receptor protein, or (3) a structural protein. The dataset was taken from [Amelie-Schreiber](https://github.com/Amelie-Schreiber/esm2_masked_lm/blob/main/sequence_classification.ipynb).

    You can run this model on Google Colab.

  - **Training a larger model (model_name = "facebook/esm2_t33_650M_UR50D")**

    To run this model we need more compute resources then what is available on Google Colab. So, I ran the [sequence_classification_large](https://github.com/mabbasiazad/Protein_Language_Models/tree/master/sequence_classification_large/finetune_esm_on_deeploc) notebook in AWS SageMaker. The GPU instance used are mentined in the notebook.

    The specific problem addressed in this notebook is `subcellular localization`: Given a protein sequence, can we build a model that can predict if it lives on the outside (cell membrane) or inside of a cell? This is an important piece of information that can help us understand the function and whether it would make a good drug target.

    The source of the notebook is [aws-healthcare-lifescience-ai-ml-sample-notebooks](https://github.com/aws-samples/aws-healthcare-lifescience-ai-ml-sample-notebooks/tree/main/workshops/Protein_Language_Modelling/finetune_esm_on_deeploc)

- **Residue/Token Classification:**

  *The aim is to predict the binding site of proteins with ESM2 model*
  *(In progress)*
