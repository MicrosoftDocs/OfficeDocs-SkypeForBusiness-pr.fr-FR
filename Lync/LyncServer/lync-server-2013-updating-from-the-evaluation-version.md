---
title: 'Lync Server 2013 : mise à jour à partir de la version d’évaluation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21fa1c35cff49205a7287841ac90c5dd9f0a4510
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506691"
---
# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>Mise à jour à partir de la version d’évaluation de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-20_

Si vous avez installé la version d’évaluation de Microsoft Lync Server 2013, vous aurez peut-être besoin de mettre à jour cette installation en tant que copie sous licence du logiciel ; Cela est dû au fait que la version d’évaluation expire 180 jours après son installation. Toutefois, vous ne devrez pas désinstaller complètement la version d’évaluation, puis installer la version sous licence. Au lieu de cela, une fois que vous avez obtenu une clé de licence valide, vous pouvez mettre à jour la version d’évaluation de Lync Server 2013 en exécutant la procédure suivante sur chaque ordinateur jouant le rôle de serveur frontal, directeur ou serveur Edge Lync Server. Il n’est pas nécessaire de mettre à jour les ordinateurs ayant d’autres rôles serveur, tels qu’un serveur de surveillance ou un serveur d’archivage.

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>Mise à jour à partir de la version d’évaluation de Microsoft Lync Server 2013

Pour mettre à jour un ordinateur à partir de la version d’évaluation de Lync Server 2013 vers la version sous licence du logiciel, procédez comme suit :

**Mise à jour à partir de la version d’évaluation de Microsoft Lync Server 2013**

1.  Ouvrez une session sur l’ordinateur en tant qu’administrateur local.

2.  Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Dans Lync Server Management Shell, tapez la commande suivante, puis appuyez sur entrée :
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    Il se peut que vous deviez spécifier le chemin d’accès complet au fichier server.msi. Ce fichier se trouve dans le dossier Setup des fichiers d’installation des médias de volume Lync Server.

4.  Une fois l’installation terminée, tapez la commande suivante depuis l’invite de commande, puis appuyez sur ENTRÉE :
    
        Enable-CsComputer

5.  Répétez cette procédure sur tout autre serveur frontal, directeur ou serveur Edge exécutant une copie d’évaluation de Lync Server. Cette procédure doit également être exécutée sur les serveurs de succursale déployés à l’aide des fichiers d’installation multimédia de Lync Server.

Si vous n’êtes pas certain que la version d’évaluation de Lync Server est en cours d’exécution sur un ordinateur donné, vous pouvez vérifier qu’en exécutant la commande suivante à partir de Lync Server Management Shell :

    Get-CsServerVersion

L’applet de commande [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) analyse l’ordinateur local et spécifie les éléments suivants :

  - Que la clé de licence en volume Lync Server a été installée sur l’ordinateur, ce qui signifie qu’aucune mise à jour n’est nécessaire.

  - Que la clé de licence d’évaluation Lync Server a été installée, ce qui signifie que l’ordinateur doit être mis à jour.

  - Aucune clé de licence en volume n’est requise sur l’ordinateur. La mise à jour de la version d’évaluation vers la version sous licence est uniquement nécessaire sur les serveurs frontaux, les directeurs et les serveurs Edge.

</div>

</div>

<span> </span>

</div>

</div>

</div>

