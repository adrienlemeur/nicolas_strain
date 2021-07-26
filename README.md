# Instruction pour le placement des souches de Nicolas
Souche à placer : ans010, ans003, gok4

## Construction de la référence avec AMPHI
Entrée :
- Matrice de design (76 strains) : 
  - /pasteur/zeus/projets/p02/Hotpaleo/adrien/Projets/RESULTS/07-09-TRY-ONE_EPA_ypestis_pseudotuberculosis/full_72_design_ypestis_pseudotuberculosis.csv

- Génome de référence :
  - **pseudotuberculosis** : /pasteur/zeus/projets/p02/Hotpaleo/adrien/Projets/GENOMES/pseudotuberculosis_ref.fna.gz + ANNOTATION
  - **pestis** : /pasteur/zeus/projets/p02/Hotpaleo/adrien/Projets/GENOMES/Y.pestis_ref_genome.fna.gz + ANNOTATION

Sortie :
- Fichier VCF des souches de référence : results/vcfs/*.merged.rmdup.haplotyper.genotypegvcfs.vcf.gz
- Arbre de référence results/tree/ml_tree.raxml.bestTree
  - Note : Enlever manuellement la branche reference

## Placement des souches inconnues avec TRYON (pestis + pseudopestis)
2 x launcher :
- **pestis** : /pasteur/zeus/projets/p02/Hotpaleo/adrien/Projets/TRY-ON_EPA/TRYON_EPA_benchmark_ypestis_unknownshores.sh
- **pseudotuberculosis** : /pasteur/zeus/projets/p02/Hotpaleo/adrien/Projets/TRY-ON_EPA/TRYON_EPA_benchmark_ypseudotuberculosis_unknownshores.sh

Entrée :
- Matrice de design des souches à placer :
  - /pasteur/zeus/projets/p02/Hotpaleo/adrien/Projets/RESULTS/07-09-TRY-ONE_EPA_ypestis_pseudotuberculosis/nicolas_strain.csv

- Génome de référence (même que pour AMPHI) :
  - **pseudotuberculosis** : /pasteur/zeus/projets/p02/Hotpaleo/adrien/Projets/GENOMES/pseudotuberculosis_ref.fna.gz + ANNOTATION
  - **pestis** : /pasteur/zeus/projets/p02/Hotpaleo/adrien/Projets/GENOMES/Y.pestis_ref_genome.fna.gz + ANNOTATION

- Arbre de référence (sortie AMPHI) :
  - **pseudotuberculosis** : /pasteur/zeus/projets/p02/Hotpaleo/adrien/Projets/RESULTS/07-09-TRY-ONE_EPA_ypestis_pseudotuberculosis/wPseudotuberculosis_morestrains/ml_tree.raxml.bestTree
  - **pestis** : /pasteur/zeus/projets/p02/Hotpaleo/adrien/Projets/RESULTS/07-09-TRY-ONE_EPA_ypestis_pseudotuberculosis/wPestis_morestrains/ml_tree.raxml.bestTree

- VCF des souches de référence (sortie AMPHI) :
    - **pseudotuberculosis** : /pasteur/zeus/projets/p02/Hotpaleo/adrien/Projets/RESULTS/07-09-TRY-ONE_EPA_ypestis_pseudotuberculosis/wPseudotuberculosis_morestrains/ref_vcf/*.merged.rmdup.haplotyper.genotypegvcfs.vcf.gz
    - **pestis** : /pasteur/zeus/projets/p02/Hotpaleo/adrien/Projets/RESULTS/07-09-TRY-ONE_EPA_ypestis_pseudotuberculosis/wPestis_morestrains/ref_vcf/*.merged.rmdup.haplotyper.genotypegvcfs.vcf.gz
 
Sortie :

- Dossier de résultats :
  - **pseudotuberculosis** : TRY-ON_EPA/results/nicolas_strain_pseudotuberculosis
  - **pestis** : TRY-ON_EPA/results/nicolas_strain_pestis
 
    - Placement des souches individuelles (jplace) : placement/
    - Placement de toutes les souches (jplace + newick) : big_tree_placement
