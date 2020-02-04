---
title: 'Lync Server 2013 : activation ou désactivation de l’intégration avec le stockage Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5c8a52aabb504ce63ef6e340b5a68e9e8c4c0e7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a><span data-ttu-id="cfced-102">Activation ou désactivation de l’intégration de Lync Server 2013 avec le stockage Exchange</span><span class="sxs-lookup"><span data-stu-id="cfced-102">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfced-103">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="cfced-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="cfced-104">Dans Lync Server 2013 panneau de configuration, vous utilisez des configurations d’archivage pour activer et désactiver l’intégration avec le stockage Exchange.</span><span class="sxs-lookup"><span data-stu-id="cfced-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable integration with Exchange storage.</span></span> <span data-ttu-id="cfced-105">Cela inclut les configurations d’archivage suivantes :</span><span class="sxs-lookup"><span data-stu-id="cfced-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="cfced-106">Configuration globale créée par défaut lors du déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cfced-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="cfced-107">Configurations facultatives de niveau de site et de niveau groupe que vous pouvez créer et utiliser pour spécifier la façon dont l’archivage est implémenté pour des sites ou des groupes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="cfced-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="cfced-108">Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou les opérations.</span><span class="sxs-lookup"><span data-stu-id="cfced-108">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="cfced-109">Pour activer ou désactiver l’intégration avec Microsoft Exchange Storage</span><span class="sxs-lookup"><span data-stu-id="cfced-109">To enable or disable integration with Microsoft Exchange storage</span></span>

1.  <span data-ttu-id="cfced-110">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="cfced-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cfced-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cfced-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cfced-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cfced-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cfced-113">Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="cfced-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="cfced-114">Cliquez sur le nom de la configuration de site, de pool ou globale appropriée dans la liste des configurations d’archivage, puis sur **Modifier**, sur **Afficher les détails** et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="cfced-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="cfced-115">Pour activer l’intégration avec le stockage Exchange 2013, activez la case à cocher **intégration Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="cfced-115">To enable integration with Exchange 2013 storage, select the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="cfced-116">Pour désactiver l’intégration avec le stockage Exchange 2013, décochez la case **intégration de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="cfced-116">To disable integration with Exchange 2013 storage, clear the **Microsoft Exchange integration** check box.</span></span>

5.  <span data-ttu-id="cfced-117">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="cfced-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cfced-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cfced-118">See Also</span></span>


[<span data-ttu-id="cfced-119">Fonctionnement de l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfced-119">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="cfced-120">Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools</span><span class="sxs-lookup"><span data-stu-id="cfced-120">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

