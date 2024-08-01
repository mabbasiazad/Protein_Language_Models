### Tasks done by ESM2

- **Masked Language Modeling:**

  [mutation_effect_enzyme](https://github.com/mabbasiazad/Protein_Language_Models/blob/master/mutation_effect_enzyme.ipynb) calculates the mutation score introduced in the paper [Language models enable zero-shot prediction of the effects of mutations on protein function](https://www.biorxiv.org/content/10.1101/2021.07.09.450648v2). It ranks the functional impact of mutated sequences compared to the original (wild-type) sequence.

- **Sequence Classification:**

  - **Training a small model (model_name = `facebook/esm2_t6_8M_UR50D`):**

    [sequence_classification_small](https://github.com/mabbasiazad/Protein_Language_Models/blob/master/sequence_classification_small.ipynb) notebook is about predicting whether a protein is (1) an enzyme, (2) a receptor protein, or (3) a structural protein. The dataset was taken from [Amelie-Schreiber](https://github.com/Amelie-Schreiber/esm2_masked_lm/blob/main/sequence_classification.ipynb).

    You can run this model on Google Colab.

  - **Training a larger model:**

    The specific problem addressed in this notebook is `subcellular localization`: Given a protein sequence, can we build a model that can predict if it lives on the outside (cell membrane) or inside of a cell? This is an important piece of information that can help us understand the function and whether it would make a good drug target.

- **Residue/Token Classification:**

  *(In progress)*
