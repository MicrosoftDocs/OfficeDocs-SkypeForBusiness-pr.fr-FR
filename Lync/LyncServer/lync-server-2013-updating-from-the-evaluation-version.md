---
title: 'Lync Server 2013: mise à jour à partir de la version d’évaluation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b00fed276229cbaf0e960e28e622e490fb0bfbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>Mise à jour à partir de la version d’évaluation de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-06-20_

Si vous avez installé la version d’évaluation de Microsoft Lync Server 2013, vous devrez peut-être mettre à jour cette installation en tant que copie sous licence du logiciel. en effet, la version d’évaluation expire 180 jours après son installation. Néanmoins, vous n’aurez pas besoin de désinstaller complètement la version d’évaluation, puis d’installer la version sous licence. Au lieu de cela, une fois que vous avez obtenu une clé de licence valide, vous pouvez mettre à jour la version d’évaluation de Lync Server 2013 en suivant la procédure ci-dessous sur chaque ordinateur agissant en tant que serveur frontal, directeur ou serveur Edge Lync Server. Notez que vous n’avez pas besoin de mettre à jour les ordinateurs exécutant d’autres rôles serveur tels qu’un serveur de surveillance ou un serveur d’archivage.

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>Mise à jour à partir de la version d’évaluation de Microsoft Lync Server 2013

Pour mettre à jour un ordinateur à partir de la version d’évaluation de Lync Server 2013 vers la version sous licence du logiciel:

**Mise à jour à partir de la version d’évaluation de Microsoft Lync Server 2013**

1.  Ouvrez une session sur l’ordinateur en tant qu’administrateur local.

2.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Dans Lync Server Management Shell, tapez la commande suivante, puis appuyez sur entrée:
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    Notez qu’il se peut que vous deviez spécifier le chemin d’accès complet au fichier serveur. msi. Ce fichier se trouve dans le dossier d’installation des fichiers d’installation de médias de volume de Lync Server.

4.  Une fois l’installation terminée, tapez ce qui suit à l’invite de commandes, puis appuyez sur entrée:
    
        Enable-CsComputer

5.  Répétez cette procédure sur tout autre serveur principal, directeur ou serveur Edge exécutant une copie d’évaluation de Lync Server. Cette procédure doit également être effectuée sur les serveurs de succursales déployés à l’aide des fichiers d’installation de Lync Server Media.

Si vous ne savez pas si la version d’évaluation de Lync Server s’exécute sur un ordinateur donné, vous pouvez le vérifier en exécutant la commande suivante à partir de Lync Server Management Shell:

    Get-CsServerVersion

L’applet de commande [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) analyse l’ordinateur local et vous signale l’un des éléments suivants:

  - La clé de licence en volume de Lync Server a été installée sur l’ordinateur, ce qui signifie qu’aucune mise à jour n’est nécessaire.

  - La clé de licence d’évaluation de Lync Server a été installée, ce qui signifie que l’ordinateur doit être mis à jour.

  - Aucune clé de licence en volume n’est requise sur l’ordinateur. La mise à jour de la version d’évaluation vers la version sous licence est uniquement requise sur les serveurs front-end, les directeurs et les serveurs Edge.

</div>

</div>

<span> </span>

</div>

</div>

</div>

