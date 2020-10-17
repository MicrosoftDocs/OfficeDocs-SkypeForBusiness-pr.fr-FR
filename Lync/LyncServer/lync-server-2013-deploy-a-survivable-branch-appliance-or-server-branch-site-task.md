---
title: Déployer une tâche Survivable Branch Appliance ou serveur-de site de succursale
description: Déployez une tâche Survivable Branch Appliance ou serveur-de site de succursale.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy a Survivable Branch Appliance or Server - branch site task
ms:assetid: 7989ba29-0419-46dd-892c-4ad3238afd56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398599(v=OCS.15)
ms:contentKeyID: 48184586
ms.date: 10/29/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b84f603f185bd507111d4767a22e9009fc0e8b3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545300"
---
# <a name="deploy-a-survivable-branch-appliance-or-server-with-lync-server-2013---branch-site-task"></a><span data-ttu-id="0762b-103">Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec la tâche Lync Server 2013-Branch site</span><span class="sxs-lookup"><span data-stu-id="0762b-103">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0762b-104">_**Dernière modification de la rubrique :** 2014-10-28_</span><span class="sxs-lookup"><span data-stu-id="0762b-104">_**Topic Last Modified:** 2014-10-28_</span></span>

<span data-ttu-id="0762b-105">Effectuez l’une des deux procédures décrites dans cette rubrique sur le site de succursale, après avoir terminé les tâches de [déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013-tâches de site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="0762b-105">Perform one of the two procedures described in this topic at the branch site, after successfully completing the tasks in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="0762b-106">Pour exécuter cette procédure, vous devez être membre du groupe RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="0762b-106">To perform this procedure, you must be a member of the RTCUniversalSBATechnicians group.</span></span>



</div>

<div>

## <a name="to-deploy-the-survivable-branch-appliance"></a><span data-ttu-id="0762b-107">Pour déployer le Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="0762b-107">To deploy the Survivable Branch Appliance</span></span>

  - <span data-ttu-id="0762b-108">Le déploiement du Survivable Branch Appliance est activé par le fournisseur Survivable Branch Appliance via une interface utilisateur Web.</span><span class="sxs-lookup"><span data-stu-id="0762b-108">Survivable Branch Appliance deployment is enabled by the Survivable Branch Appliance vendor through a web user interface (UI).</span></span> <span data-ttu-id="0762b-109">Pour plus d’informations sur le déploiement du Survivable Branch appliance, consultez la documentation de votre fournisseur Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="0762b-109">For information about deploying the Survivable Branch Appliance, see your Survivable Branch Appliance vendor documentation.</span></span>

</div>

<div>

## <a name="to-deploy-the-survivable-branch-server"></a><span data-ttu-id="0762b-110">Pour déployer le serveur Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="0762b-110">To deploy the Survivable Branch Server</span></span>

  - <span data-ttu-id="0762b-111">Installez Lync Server 2013 sur un ordinateur exécutant Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2, tout comme vous installerez n’importe quel autre rôle serveur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0762b-111">Install Lync Server 2013 on a computer running Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2, just as you would install any other Lync Server 2013 server role.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="0762b-112">Pour plus d’informations sur l’installation de Lync Server, voir <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0762b-112">For information about installing Lync Server, see <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="0762b-113">**Étape suivante**: [Configuration des utilisateurs pour la résistance des sites de succursale dans Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="0762b-113">**Next step**: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0762b-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0762b-114">See Also</span></span>


[<span data-ttu-id="0762b-115">Annexe A : utilisation d’applets de commande pour déployer un Survivable Branch Appliance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0762b-115">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>](lync-server-2013-appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

