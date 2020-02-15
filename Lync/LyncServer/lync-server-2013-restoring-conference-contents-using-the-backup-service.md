---
title: 'Lync Server 2013 : restauration du contenu de conférence à l’aide du service de sauvegarde'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8fb791362718b2bce5e7c13c0cc6aab779d954f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="d24f2-102">Restauration du contenu d’une conférence à l’aide du service de sauvegarde dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d24f2-102">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d24f2-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d24f2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d24f2-p101">Si les informations de conférence stockées dans le magasin de fichiers d’un pool frontal deviennent disponibles, vous devez restaurer ces informations pour permettre aux utilisateurs hébergés sur le pool de conserver leurs données de conférence. Si le pool frontal qui a perdu les données de conférence est couplé à un autre pool frontal, vous pouvez utiliser le service de sauvegarde pour restaurer les données.</span><span class="sxs-lookup"><span data-stu-id="d24f2-p101">If the conference information stored in the file store of a Front End pool becomes unavailable. you must restore this information so that users homed on the pool retain their conference data. If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="d24f2-p102">Vous devez aussi effectuer cette tâche en cas de panne d’un pool entier et basculer ses utilisateurs sur un pool de sauvegarde. Quand ces utilisateurs sont rebasculés sur leur pool d’origine, vous devez également exécuter cette procédure pour recopier leur contenu de référence sur le pool d’origine.</span><span class="sxs-lookup"><span data-stu-id="d24f2-p102">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="d24f2-109">Supposons que Pool1 est couplé à Pool2 et que les données de conférence de Pool1 sont perdues.</span><span class="sxs-lookup"><span data-stu-id="d24f2-109">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="d24f2-110">Vous pouvez utiliser l’applet de commande suivante pour appeler le service de sauvegarde afin de restaurer le contenu :</span><span class="sxs-lookup"><span data-stu-id="d24f2-110">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="d24f2-p104">La restauration du contenu de conférence peut prendre un certain temps, qui est fonction de sa taille. Vous pouvez utiliser l’applet de commande suivante pour vérifier l’état du processus</span><span class="sxs-lookup"><span data-stu-id="d24f2-p104">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="d24f2-113">Le processus est terminé une fois que cette applet de commande a retourné une valeur d’état stable pour les données du module de conférence.</span><span class="sxs-lookup"><span data-stu-id="d24f2-113">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

