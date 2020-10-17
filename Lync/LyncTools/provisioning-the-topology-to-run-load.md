---
title: Mise en service de la topologie pour exécuter la charge
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45b1c9d320ef35555e83bbd8851d77e00a452631
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509101"
---
# <a name="provisioning-the-topology-to-run-load"></a>Mise en service de la topologie pour exécuter la charge

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-04_

<div>

En fonction de vos paramètres et de la configuration existants de Lync Server 2013, vous devrez peut-être effectuer les modifications suivantes dans votre environnement :

1.  Définissez la stratégie d’exécution Windows PowerShell sur Unrestricted. Pour vérifier les paramètres de la stratégie d’exécution, ouvrez Lync Server Management Shell et exécutez la commande suivante :

    ``` powershell
        Get-ExecutionPolicy
    ```        

    Si cette commande ne renvoie pas la valeur Unrestricted, exécutez la commande suivante :

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  Pour configurer de manière efficace Lync Server 2013, vous devez :
    
      - Se familiariser avec la topologie Lync Server 2013 (par exemple, les noms d’ordinateur, les instances de service, les noms de site et les stratégies).
    
      - Affectez certains des utilisateurs qui ont été créés à des groupes, tels que les groupes de postes Response Group (par exemple, URI SIP).

3.  Pour exécuter le script à partir de la ligne de commande, vous pouvez utiliser les éléments suivants :

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  En règle générale, après l’exécution d’un des scripts de ce package, les traces résultantes du script sont stockées dans un fichier dans le même chemin d’accès que celui à partir duquel le script a été appelé \<scriptname\> $h $ m $s.txt. Par exemple, l’exécution de ArchivingPolicy.ps1 à 12:15 P.M. générera un fichier journal tel que ArchivingPolicy121500.txt.

5.  Enfin, Notez que même si nous avons fourni des exemples pour configurer le serveur, vous êtes responsable de la modification ou de la suppression de la configuration une fois le chargement terminé.

</div>

</div>

<span> </span>

</div>

</div>

</div>

