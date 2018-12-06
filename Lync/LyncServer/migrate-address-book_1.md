---
title: Migration du carnet d’adresses
TOCTitle: Migration du carnet d’adresses
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205198(v=OCS.15)
ms:contentKeyID: 49298621
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration du carnet d’adresses

 

_**Dernière rubrique modifiée :** 2012-10-02_

**Pour migrer des règles de normalisation de carnet d’adresses personnalisées**

1.  Recherchez le fichier Company\_Phone\_Number\_Normalization\_Rules.txt à la racine du dossier partagé de carnet d’adresses et copiez-le à la racine du dossier partagé de carnet d’adresses de votre pool pilote Lync Server 2013.
    
    > [!NOTE]  
    > Les exemples de règles de normalisation de carnet d’adresses ont été installés dans votre répertoire de fichiers de composants web ABS. Le chemin d’accès est <strong>$lettre_lecteur_installation:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</strong>. Ce fichier peut être copié et renommé en <strong>Company_Phone_Number_Normalization_Rules.txt</strong> dans le répertoire racine du dossier partagé du carnet d’adresses. Par exemple, pour le carnet d’adresses partagé dans <strong>$serveurX</strong>, le chemin d’accès sera similaire à ceci : <strong>\\$serveurX \LyncFileShare\2-WebServices-1\ABFiles</strong>.

2.  Ouvrez le fichier Company\_Phone\_Number\_Normalization\_Rules.txt dans un éditeur de texte, tel que le Bloc-notes.

3.  Certains types d’entrées ne fonctionneront pas correctement dans Lync Server 2013. Recherchez dans le fichier les types d’entrées décrites à cette étape, modifiez-les selon les besoins, puis enregistrez les modifications dans le dossier partagé de carnet d’adresses de votre pool pilote.
    
    Les chaînes qui comportent des espaces ou des signes de ponctuation provoquent l’échec des règles de normalisation car ces caractères sont supprimés de la chaîne fournie comme entrée aux règles de normalisation. Si vous avez des chaînes qui comportent des espaces ou des signes de ponctuation obligatoires, vous devez modifier ces chaînes. Par exemple, la chaîne suivante provoque l’échec de la règle de normalisation :
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    La chaîne suivante ne provoque pas l’échec de la règle de normalisation :
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

