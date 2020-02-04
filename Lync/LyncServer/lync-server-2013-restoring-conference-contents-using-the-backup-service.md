---
title: 'Lync Server 2013 : Restauration du contenu d’une conférence avec le service de sauvegarde'
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
ms.openlocfilehash: 873ca354ca592eb6bc317b579a0a6f5008e6a172
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="bfded-102">Restauration du contenu d’une conférence avec le service de sauvegarde dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfded-102">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfded-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bfded-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bfded-104">Si les informations de la Conférence stockées dans le magasin de fichiers d’un pool frontal deviennent indisponibles.</span><span class="sxs-lookup"><span data-stu-id="bfded-104">If the conference information stored in the file store of a Front End pool becomes unavailable.</span></span> <span data-ttu-id="bfded-105">vous devez restaurer ces informations de sorte que les utilisateurs hébergés sur le pool conservent leurs données de conférence.</span><span class="sxs-lookup"><span data-stu-id="bfded-105">you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="bfded-106">Si le pool frontal qui a perdu les données de conférence est associé à un autre pool frontal, vous pouvez utiliser le service de sauvegarde pour restaurer les données.</span><span class="sxs-lookup"><span data-stu-id="bfded-106">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="bfded-107">Vous devez également effectuer cette tâche si un pool entier a échoué et que vous devez faire basculer ses utilisateurs vers un pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="bfded-107">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="bfded-108">Lorsque les utilisateurs ont basculé vers leur pool d’origine, vous devez utiliser cette procédure pour copier le contenu de la Conférence sur leur pool d’origine.</span><span class="sxs-lookup"><span data-stu-id="bfded-108">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="bfded-109">Supposez que Pool1 est associé à Pool2, et les données de conférence en Pool1 sont perdues.</span><span class="sxs-lookup"><span data-stu-id="bfded-109">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="bfded-110">Vous pouvez utiliser l’applet de commande suivante pour appeler le service de sauvegarde et restaurer le contenu :</span><span class="sxs-lookup"><span data-stu-id="bfded-110">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="bfded-111">La restauration du contenu de la Conférence risque de prendre un certain temps en fonction de la taille de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="bfded-111">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="bfded-112">Pour vérifier l’état du processus, vous pouvez utiliser l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="bfded-112">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="bfded-113">Le processus est réalisé lorsque cette cmdlet renvoie une valeur d’état stable pour le module de conférence de données.</span><span class="sxs-lookup"><span data-stu-id="bfded-113">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

