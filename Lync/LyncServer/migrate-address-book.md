---
title: Migrer le carnet d’adresses
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2293b7ad3e5ac14071bae4d5ecb935c24cfbb335
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>Migrer le carnet d’adresses

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-09_

En règle générale, le carnet d’adresses de Lync Server 2010 est migré en même temps que le reste de votre topologie. Toutefois, vous devrez peut-être effectuer certaines étapes après la migration si vous avez personnalisé les éléments suivants dans votre environnement Lync Server 2010:

  - Définissez la propriété WMI **PartitionbyOU** pour regrouper les entrées du carnet d’adresses par unité d’organisation.

  - Personnalisé les règles de normalisation du carnet d’adresses.

  - La valeur par défaut du paramètre **UseNormalizationRules** a été remplacée par false.

**Entrées du carnet d’adresses groupé**

Si vous définissez la propriété WMI **PartitionbyOU** sur true pour créer des carnets d’adresses pour chaque unité d’organisation, vous devez configurer l’attribut Active Directory **msRTCSIP-GroupingId** sur les utilisateurs et les contacts si vous voulez continuer à regrouper les entrées du carnet d’adresses. Il est possible que vous souhaitiez regrouper les entrées du carnet d’adresses afin de limiter l’étendue des recherches dans le carnet d’adresses. Pour utiliser l’attribut **msRTCSIP-GroupingId** , écrivez un script pour remplir l’attribut, en attribuant la même valeur à tous les utilisateurs que vous voulez regrouper. Par exemple, attribuez une valeur unique à tous les utilisateurs d’une unité d’organisation.

**Règles de normalisation du carnet d’adresses**

Si vous avez personnalisé des règles de normalisation du carnet d’adresses dans votre environnement Lync Server 2010, vous devez migrer les règles personnalisées vers votre pool de pilotes. Si vous n’avez pas personnalisé les règles de normalisation du carnet d’adresses, vous n’avez rien à migrer pour le service de carnet d’adresses. Les règles de normalisation par défaut de Lync Server 2013 sont les mêmes que celles par défaut de Lync Server 2010. Suivez la procédure décrite plus loin dans cette section pour migrer des règles de normalisation personnalisées.

<div>


> [!NOTE]  
> Si votre organisation utilise le contrôle d’appel distant et que vous avez personnalisé des règles de normalisation du carnet d’adresses, vous devez effectuer la procédure décrite dans cette rubrique avant de pouvoir utiliser le contrôle d’appel distant. Cette procédure requiert l’appartenance au groupe RTCUniversalServerAdmins ou aux droits équivalents.



</div>

**UseNormalizationRules défini sur false**

Si vous définissez la valeur de **UseNormalizationRules** sur false pour que les utilisateurs puissent utiliser les numéros de téléphone tels qu’ils sont définis dans les services de domaine Active Directory (AD FS) sans que Lync Server 2013 applique des règles de normalisation, vous devez définir **UseNormalizationRules **et les paramètres **IgnoreGenericRules** sur true. Suivez la procédure décrite plus loin dans cette section pour définir ces paramètres sur true.

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Pour migrer des règles de normalisation personnalisées du carnet d’adresses

1.  Recherchez le fichier\_.\_txt\_du numéro\_de téléphone de l’entreprise à la racine du dossier partagé du carnet d’adresses, puis copiez-le à la racine du dossier partagé du carnet d’adresses dans votre pool de pilotes 2013 de Lync Server.
    
    <div>
    

    > [!NOTE]  
    > Les règles de normalisation de votre carnet d’adresses sont installées dans votre répertoire de fichiers de composants Web ABS. Le chemin d’accès est <STRONG>$installedDriveLetter: \Program Files\Microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt,</STRONG>. Ce fichier peut être copié et renommé &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;dans le répertoire racine du dossier partagé du carnet d’adresses. Par exemple, dans le carnet d’adresses <STRONG></STRONG>partagé dans&nbsp;$serverX, le chemin d’accès est semblable à ce qui suit: <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.

    
    </div>

2.  Utilisez un éditeur de texte, tel que le bloc-notes,\_pour\_ouvrir\_le fichier\_de règles de normalisation des numéros de téléphone de l’entreprise.

3.  Certains types d’entrée ne fonctionnent pas correctement dans Lync Server 2013. Parcourez le fichier pour obtenir les types d’entrée décrits dans cette étape, modifiez-les comme vous le souhaitez et enregistrez les modifications apportées au dossier partagé du carnet d’adresses dans votre pool de pilotes.
    
    Les chaînes qui comprennent des espaces blancs ou des signes de ponctuation peuvent entraîner l’échec des règles de normalisation, car ces caractères sont supprimés de la chaîne qui est en entrée dans les règles de normalisation. Si vous avez des chaînes qui incluent des espaces blancs ou des signes de ponctuation requis, vous devez modifier les chaînes. Par exemple, la chaîne suivante entraînera l’échec de la règle de normalisation:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    La chaîne suivante n’entraînera pas l’échec de la règle de normalisation:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Pour définir UseNormalizationRules et IgnoreGenericRules sur true

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Effectuez l’une des actions suivantes :
    
      - Si votre déploiement inclut uniquement Lync Server 2013, exécutez l’applet de commande suivante au niveau global pour modifier les valeurs de **UseNormalizationRules** et **IgnoreGenericRules** sur true:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Si votre déploiement inclut une combinaison de Lync Server 2013 et de Lync Server 2010 ou Office Communications Server 2007 R2, exécutez l’applet de commande suivante et affectez-la à chaque pool Lync Server 2013 dans la topologie:
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Attendez la fin de la réplication du magasin de gestion centrale sur tous les pools.

4.  Modifiez le fichier de règles de normalisation du téléphone,\_«\_\_règles\_de normalisation du numéro de téléphone de l’entreprise. txt», pour que votre déploiement efface le contenu. Le fichier se trouve sur le partage de fichiers de chaque pool Lync Server 2013. Si le fichier n’est pas présent, créez-en un dans la section\_«\_\_règles\_de normalisation des numéros de téléphone de l’entreprise. txt».

5.  Attendez quelques minutes pour que tous les pools du serveur principal lisent les nouveaux fichiers.

6.  Exécutez l’applet de commande suivante sur chaque pool Lync Server 2013 dans votre déploiement:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

