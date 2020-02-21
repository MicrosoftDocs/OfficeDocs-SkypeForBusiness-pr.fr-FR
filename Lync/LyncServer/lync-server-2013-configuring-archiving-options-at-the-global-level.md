---
title: 'Lync Server 2013 : configuration des options d’archivage au niveau global'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3798d64ba8a2252058756b04b51481e90bdf95c5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a><span data-ttu-id="f8363-102">Configuration des options d’archivage au niveau global dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8363-102">Configuring Archiving options at the global level in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8363-103">_**Dernière modification de la rubrique :** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="f8363-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="f8363-104">Lorsque vous ajoutez l’archivage à votre topologie et que vous publiez la topologie, Lync Server crée une configuration globale pour l’archivage.</span><span class="sxs-lookup"><span data-stu-id="f8363-104">When you add Archiving to your topology and publish the topology, Lync Server creates a global configuration for Archiving.</span></span> <span data-ttu-id="f8363-105">Par défaut, aucune option d’archivage n’est activée dans la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="f8363-105">By default, no Archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="f8363-106">La configuration globale contrôle les options qui sont activées pour l’ensemble de votre déploiement, sauf si vous configurez des configurations de site ou de pool, ce qui remplace la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="f8363-106">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>

<span data-ttu-id="f8363-107">Pour plus d’informations sur le fonctionnement des configurations d’archivage, notamment la hiérarchie des configurations globale, de site et de pool, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="f8363-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8363-108">Vous devez spécifier toutes les options appropriées pour les configurations d’archivage avant d’activer la fonctionnalité d’archivage.</span><span class="sxs-lookup"><span data-stu-id="f8363-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a><span data-ttu-id="f8363-109">Pour configurer les options d’archivage au niveau global</span><span class="sxs-lookup"><span data-stu-id="f8363-109">To configure archiving options at the global level</span></span>

1.  <span data-ttu-id="f8363-110">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f8363-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f8363-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8363-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="f8363-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server 2013, reportez-vous à la rubrique [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f8363-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f8363-113">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="f8363-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="f8363-114">Dans la page **Configuration de l’archivage**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="f8363-114">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f8363-115">Dans **Modifier le paramètre d’archivage - Global**, dans la zone de liste déroulante **Paramètre d’archivage**, sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="f8363-115">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="f8363-116">**Désactiver l’archivage**</span><span class="sxs-lookup"><span data-stu-id="f8363-116">**Disable archiving**</span></span>
    
      - <span data-ttu-id="f8363-117">**Archiver les sessions de messagerie instantanée**</span><span class="sxs-lookup"><span data-stu-id="f8363-117">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="f8363-118">**Archiver les sessions de messagerie instantanée et de conférence web**</span><span class="sxs-lookup"><span data-stu-id="f8363-118">**Archive IM and web conferencing sessions**</span></span>

6.  <span data-ttu-id="f8363-119">Dans la page **Modifier le paramètre d’archivage - Global**, effectuez également les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f8363-119">Also on the **Edit Archiving Setting – Global** page, do the following:</span></span>
    
      - <span data-ttu-id="f8363-120">Pour bloquer toute activité lorsque l’archivage n’est pas disponible, activez la case à cocher **Bloquer les sessions de messagerie instantanée ou de conférence web en cas d’échec de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="f8363-120">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="f8363-121">Pour utiliser Microsoft Exchange Server afin de stocker les données d’archivage, cliquez sur la case à cocher **intégration de Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="f8363-121">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="f8363-122">Pour activer le vidage des données, activez la case à cocher **Activer le vidage des données d’archivage**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f8363-122">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="f8363-123">Pour planifier le vidage après un nombre précis de jours, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis précisez le nombre de jours.</span><span class="sxs-lookup"><span data-stu-id="f8363-123">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="f8363-124">Pour limiter le vidage aux données d’archivage qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.</span><span class="sxs-lookup"><span data-stu-id="f8363-124">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="f8363-125">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="f8363-125">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

