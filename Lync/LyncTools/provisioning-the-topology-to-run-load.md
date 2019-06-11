---
title: Mise en service de la topologie pour exécuter le chargement
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026915b4a08073e96d29b32278adc4e260eaaea4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a>Mise en service de la topologie pour exécuter le chargement

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-04_

<div>

## <a name="provisioning-the-topology-to-run-load"></a>Mise en service de la topologie pour exécuter le chargement

Selon vos paramètres et la configuration de Lync Server 2013, il est possible que vous deviez apporter les modifications suivantes à votre environnement:

1.  Définissez la stratégie d’exécution Windows PowerShell sur non restreinte. Pour vérifier les paramètres de stratégie d’exécution, ouvrez Lync Server Management Shell et exécutez la commande suivante:

    ``` powershell
        Get-ExecutionPolicy
    ```        

    Si cette commande n’a pas pour résultat la valeur Unrestricted, exécutez la commande suivante:

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  Pour configurer efficacement Lync Server 2013, vous devez:
    
      - Familiarisez-vous avec la topologie Lync Server 2013 (par exemple, les noms d’ordinateurs, les instances de service, les noms de sites et les stratégies).
    
      - Assignez certains utilisateurs qui ont été créés dans des groupes, par exemple, des groupes de recherche de Response Group (par exemple, URI SIP).

3.  Pour exécuter le script à partir de la ligne de commande, vous pouvez utiliser les éléments suivants:

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  En règle générale, après l’exécution de l’un des scripts de ce package, les traces obtenues à partir du script seront stockées dans un fichier dans le même chemin à partir duquel le script \<a\>été appelé, nommé scriptname $h $ m $ s. txt. Par exemple, en exécutant ArchivingPolicy. ps1 à 12:15 P.M. va générer un fichier journal tel que ArchivingPolicy121500. txt.

5.  Enfin, Notez que bien que nous ayons fourni des exemples de configuration du serveur, vous êtes responsable de la modification ou de la suppression de la configuration lorsque vous avez terminé d’exécuter le chargement.

</div>

</div>

<span> </span>

</div>

</div>

</div>

