Détection des Maladies des Cabosses de Cacao par Traitement d'Images
Présentation
Ce projet vise à détecter et classifier les maladies des cabosses de cacao à partir d'images annotées. Il utilise des techniques avancées de traitement d'images, d'augmentation de données, d'extraction de caractéristiques et d'apprentissage profond avec des modèles CNN pré-entraînés (MobileNetV2, EfficientNetB0). Le but est de fournir un outil robuste pour l'identification automatique des maladies, facilitant ainsi la surveillance et la gestion des plantations de cacao.

Équipe
Amoussou Eli Enock Emalin

Dohoun Amoin Maeva

Yeo Ditchaba

Fonctionnalités principales
Chargement et visualisation des images et annotations
Chargement des images originales et des fichiers d'annotations au format texte, avec affichage des boîtes englobantes colorées selon les labels des maladies détectées.

Segmentation des cabosses
Extraction des régions d'intérêt (cabosses) à partir des images complètes en fonction des boîtes englobantes, redimensionnées à 224x224 pixels.

Augmentation des données
Augmentation des images des classes minoritaires par rotations multiples (±45°, ±90°, 135°, 180°, 225°) pour équilibrer le dataset et améliorer la robustesse des modèles.

Extraction de caractéristiques CNN
Utilisation de modèles pré-entraînés MobileNetV2 et EfficientNetB0 sans la couche finale pour extraire des vecteurs de caractéristiques, suivie d’un classifieur personnalisé avec couches denses, batch normalization et activation ELU.

Optimisation avec EMA (Exponential Moving Average)
Implémentation d’un optimiseur avec moyenne mobile exponentielle des poids pour stabiliser l’apprentissage et améliorer la généralisation des modèles.

Utilisation
Chargement des données
Le script charge les images et leurs annotations, puis affiche les boîtes englobantes colorées selon le type de maladie détectée.

Segmentation
Extraction des cabosses à partir des images complètes pour créer un dataset d’images individuelles annotées.

Augmentation des données
Augmentation des classes minoritaires par rotations pour équilibrer le dataset.

Entraînement des modèles CNN
Entraînement des modèles MobileNetV2 et EfficientNetB0 avec un classifieur personnalisé et optimisation EMA.

Extraction des caractéristiques
Extraction des vecteurs de caractéristiques pour chaque image, utilisables pour des tâches de classification ou d’analyse ultérieures.

Structure du projet
├── Cocoa/                  # Dossier contenant les images et annotations
├── models/                 # Dossier pour sauvegarder les modèles entraînés
│   └── cnn/
├── scripts/                # Scripts Python pour le traitement, l'entraînement, etc.
├── README.md               # Ce fichier
└── requirements.txt        # Liste des dépendances (optionnel)

Résultats attendus
Visualisation claire des annotations avec boîtes englobantes colorées.

Dataset équilibré après augmentation avec environ 3741 images segmentées.

Modèles CNN entraînés atteignant une précision élevée (>95% après quelques époques).

Extraction de vecteurs de caractéristiques de taille 256 pour chaque image.

Remarques
Le projet utilise des poids pré-entraînés sur ImageNet pour accélérer l’apprentissage.

L’optimiseur EMA est utilisé pour stabiliser les poids pendant l’entraînement.

Le dataset initial présente un déséquilibre important entre les classes, corrigé par augmentation.

Le code peut être adapté pour d’autres types d’images ou maladies en modifiant les annotations et classes.
