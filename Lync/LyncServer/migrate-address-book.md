---
title: Migrer le carnet d’adresses
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee0dc4d50fb3b60d4f6a9581d497df11da630122
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Faire migrer le carnet d’adresses

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-09_

En règle générale, le carnet d’adresses Lync Server 2010 est migré avec le reste de votre topologie. Toutefois, vous devrez peut-être effectuer certaines étapes de post-migration si vous avez personnalisé les éléments suivants dans votre environnement Lync Server 2010 :

  - définir la propriété WMI **PartitionbyOU** pour regrouper les entrées de carnet d’adresses par unité d’organisation ;

  - personnaliser les règles de normalisation du carnet d’adresses ;

  - remplacer par False la valeur par défaut du paramètre **UseNormalizationRules**.

**Entrées de carnet d’adresses groupées**

If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries. You might want to group address book entries to limit the scope of Address Book searches. To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together. For example, assign a single value for all the users in an OU.

**Règles de normalisation de carnet d’adresses**

Si vous avez personnalisé des règles de normalisation de carnet d’adresses dans votre environnement Lync Server 2010, vous devez migrer les règles personnalisées vers votre pool pilote. Si vous n’avez pas personnalisé de règles de normalisation de carnet d’adresses, vous n’avez rien à migrer pour le service Carnet d’adresses. Les règles de normalisation par défaut pour Lync Server 2013 sont les mêmes que les règles par défaut pour Lync Server 2010. Suivez la procédure décrite plus loin dans cette section pour migrer des règles de normalisation personnalisées.

<div>


> [!NOTE]  
> If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.



</div>

**Valeur False affectée à UseNormalizationRules**

Si vous définissez la valeur de **UseNormalizationRules** sur false afin que les utilisateurs puissent utiliser les numéros de téléphone tels qu’ils sont définis dans les services de domaine Active Directory sans que Lync Server 2013 n’applique les règles de normalisation, vous devez définir les paramètres **UseNormalizationRules** et **IgnoreGenericRules** sur true. Suivez la procédure décrite plus loin dans cette section pour affecter la valeur True à ces paramètres.

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Pour migrer des règles de normalisation de carnet d’adresses personnalisées

1.  Recherchez le \_ fichier de \_ normalisation des numéros de téléphone de l’entreprise \_ \_Rules.txt à la racine du dossier partagé du carnet d’adresses, puis copiez-le à la racine du dossier partagé du carnet d’adresses dans votre pool pilote Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Les exemples de règles de normalisation de carnet d’adresses ont été installés dans votre répertoire de fichiers de composants web ABS. Le chemin d’accès est <STRONG>$lettre_lecteur_installation:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>. Ce fichier peut être copié et renommé en tant que &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; dans le répertoire racine du dossier partagé carnet d’adresses. Par exemple, le carnet d’adresses partagé dans <STRONG>$serverX</STRONG>, &nbsp; le chemin d’accès est similaire à : <STRONG> \\ $serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.

    
    </div>

2.  À l’aide d’un éditeur de texte, tel que le bloc-notes, ouvrez le fichier de normalisation des numéros de téléphone de la société \_ \_ \_ \_Rules.txt.

3.  Certains types d’entrées ne fonctionnent pas correctement dans Lync Server 2013. Recherchez dans le fichier les types d’entrées décrites à cette étape, modifiez-les selon les besoins, puis enregistrez les modifications dans le dossier partagé de carnet d’adresses de votre pool pilote.
    
    Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    La chaîne suivante ne provoque pas l’échec de la règle de normalisation :
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Pour affecter la valeur True à UseNormalizationRules et IgnoreGenericRules

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Effectuez l’une des opérations suivantes :
    
      - Si votre déploiement inclut uniquement Lync Server 2013, exécutez l’applet de commande suivante au niveau global pour modifier les valeurs de **UseNormalizationRules** et **IgnoreGenericRules** sur true :
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Si votre déploiement inclut une combinaison de Lync Server 2013 et Lync Server 2010 ou Office Communications Server 2007 R2, exécutez l’applet de commande suivante et affectez-la à chaque pool Lync Server 2013 dans la topologie :
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Attendez que la réplication du magasin central de gestion se produise sur tous les pools.

4.  Modifiez le fichier de règles de normalisation téléphonique, « Company \_ Phone \_ Number \_ Normalization \_Rules.txt », pour que votre déploiement efface le contenu. Le fichier se trouve sur le partage de fichiers de chaque pool Lync Server 2013. Si le fichier n’est pas présent, créez un fichier vide nommé « Company \_ Phone \_ Number \_ Normalization \_Rules.txt ».

5.  Attendez quelques minutes que tous les pools frontaux aient lu les nouveaux fichiers.

6.  Exécutez l’applet de commande suivante sur chaque pool Lync Server 2013 de votre déploiement :
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

