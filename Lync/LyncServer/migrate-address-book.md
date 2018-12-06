﻿---
title: Migration du carnet d’adresses
TOCTitle: Migration du carnet d’adresses
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205160(v=OCS.15)
ms:contentKeyID: 49298496
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration du carnet d’adresses

 

_**Dernière rubrique modifiée :** 2012-10-09_

En général, le carnet d’adresses Lync Server 2010 est migré avec le reste de votre topologie. Cependant, vous pouvez être amené à effectuer certaines étapes post-migration si vous avez personnalisé les éléments suivants dans votre environnement Lync Server 2010 :

  - définir la propriété WMI **PartitionbyOU** pour regrouper les entrées de carnet d’adresses par unité d’organisation ;

  - personnaliser les règles de normalisation du carnet d’adresses ;

  - remplacer par False la valeur par défaut du paramètre **UseNormalizationRules**.

**Entrées de carnet d’adresses groupées**

Si vous affectez la valeur True à la propriété WMI **PartitionbyOU** afin de créer des carnets d’adresses pour chaque unité d’organisation, vous devez définir l’attribut Active Directory **msRTCSIP-GroupingId** sur les utilisateurs et contacts si vous souhaitez continuer de regrouper les entrées de carnet d’adresses. Il peut être préférable de regrouper les entrées de carnet d’adresses pour limiter l’étendue des recherches dans les carnets d’adresses. Pour utiliser l’attribut **msRTCSIP-GroupingId** , écrivez un script pour remplir l’attribut, en affectant la même valeur pour tous les utilisateurs que vous souhaitez regrouper. Par exemple, affectez une valeur unique pour tous les utilisateurs d’une même unité d’organisation.

**Règles de normalisation de carnet d’adresses**

Si vous avez personnalisé des règles de normalisation de carnet d’adresses dans votre environnement Lync Server 2010, vous devez migrer les règles personnalisées vers votre pool pilote. Si vous n’avez pas personnalisé de règles de normalisation de carnet d’adresses, vous n’avez rien à migrer pour le service Carnet d’adresses. Les règles de normalisation par défaut pour Lync Server 2013 sont identiques aux règles par défaut pour Lync Server 2010. Suivez la procédure décrite dans la suite de cette section pour migrer des règles de normalisation personnalisées.

> [!NOTE]  
> Si votre organisation utilise le contrôle d’appel distant et que vous avez personnalisé des règles de normalisation de carnet d’adresses, vous devez appliquer la procédure de cette rubrique pour pouvoir utiliser le contrôle d’appel distant. Cette procédure requiert l’appartenance au groupe RTCUniversalServerAdmins ou des droits équivalents.

**Valeur False affectée à UseNormalizationRules**

Si vous affectez la valeur False à **UseNormalizationRules** afin que les utilisateurs puissent utiliser des numéros de téléphone tels qu’ils sont définis dans les services de domaine Active Directory sans que Lync Server 2013 applique des règles de normalisation, vous devez affecter la valeur True aux paramètres **UseNormalizationRules** et **IgnoreGenericRules**. Suivez la procédure décrite dans la suite de cette section pour affecter la valeur True à ces paramètres.

## Pour migrer des règles de normalisation de carnet d’adresses personnalisées

1.  Recherchez le fichier Company\_Phone\_Number\_Normalization\_Rules.txt à la racine du dossier partagé de carnet d’adresses et copiez-le à la racine du dossier partagé de carnet d’adresses de votre pool pilote Lync Server 2013.
    
    > [!NOTE]  
    > Les exemples de règles de normalisation de carnet d’adresses ont été installés dans votre répertoire de fichiers de composants web ABS. Le chemin d’accès est <strong>$lettre_lecteur_installation:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</strong>. Ce fichier peut être copié et renommé en <strong>Company_Phone_Number_Normalization_Rules.txt</strong> dans le répertoire racine du dossier partagé du carnet d’adresses. Par exemple, pour le carnet d’adresses partagé dans <strong>$serveurX</strong>, le chemin d’accès sera similaire à ceci : <strong>\\$serveurX \LyncFileShare\2-WebServices-1\ABFiles</strong>.

2.  Ouvrez le fichier Company\_Phone\_Number\_Normalization\_Rules.txt dans un éditeur de texte, tel que le Bloc-notes.

3.  Certains types d’entrées ne fonctionneront pas correctement dans Lync Server 2013. Recherchez dans le fichier les types d’entrées décrites à cette étape, modifiez-les selon les besoins, puis enregistrez les modifications dans le dossier partagé de carnet d’adresses de votre pool pilote.
    
    Les chaînes qui comportent des espaces ou des signes de ponctuation provoquent l’échec des règles de normalisation car ces caractères sont supprimés de la chaîne fournie comme entrée aux règles de normalisation. Si vous avez des chaînes qui comportent des espaces ou des signes de ponctuation obligatoires, vous devez modifier ces chaînes. Par exemple, la chaîne suivante provoque l’échec de la règle de normalisation :
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    La chaîne suivante ne provoque pas l’échec de la règle de normalisation :
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

## Pour affecter la valeur True à UseNormalizationRules et IgnoreGenericRules

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Effectuez l’une des actions suivantes :
    
      - Si votre déploiement comprend uniquement Lync Server 2013, exécutez l’applet de commande suivante au niveau global pour remplacer les valeurs des paramètres **UseNormalizationRules** et **IgnoreGenericRules** par True :
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Si votre déploiement comprend une combinaison de Lync Server 2013 et de Lync Server 2010 ou d’Office Communications Server 2007 R2, exécutez l’applet de commande suivante et affectez-la à chaque pool Lync Server 2013 de la topologie :
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Attendez que la réplication du magasin central de gestion se produise sur tous les pools.

4.  Modifiez le fichier des règles de normalisation des numéros de téléphone, « Company\_Phone\_Number\_Normalization\_Rules.txt » afin que votre déploiement efface le contenu. Ce fichier se trouve sur le partage de fichiers de chaque pool Lync Server 2013. Si ce fichier n’est pas présent, créez un fichier vide nommé « Company\_Phone\_Number\_Normalization\_Rules.txt ».

5.  Attendez quelques minutes que tous les pools de serveurs frontaux lisent les nouveaux fichiers.

6.  Exécutez l’applet de commande suivante sur chaque pool Lync Server 2013 de votre déploiement :
    
        Update-CsAddressBook

