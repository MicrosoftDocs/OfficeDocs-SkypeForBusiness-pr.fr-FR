---
title: 'Lync Server 2013 : déploiement des types d’adresses IP sur un serveur Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd057c79132200dbe5be8ee2551a711d8fb8e95c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a><span data-ttu-id="0b6ab-102">Déployer des types d’adresses IP sur un serveur Edge pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b6ab-102">Deploy IP address types on an Edge Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b6ab-103">_**Dernière modification de la rubrique :** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="0b6ab-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="0b6ab-104">À l’aide du générateur de topologie, effectuez les étapes de la procédure suivante pour déployer des types d’adresses IP sur un serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="0b6ab-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on an Edge Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="0b6ab-105">Pour déployer des types d’adresses IP sur un serveur Edge</span><span class="sxs-lookup"><span data-stu-id="0b6ab-105">To deploy IP address types on an Edge Server</span></span>

1.  <span data-ttu-id="0b6ab-106">Dans le générateur de topologie, sous **Pools**de serveurs Edge, cliquez avec le bouton droit sur le serveur dans un pool, puis sélectionnez **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="0b6ab-106">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="0b6ab-107">(Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**)</span><span class="sxs-lookup"><span data-stu-id="0b6ab-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="0b6ab-108">Dans la fenêtre **modifier les propriétés** , sélectionnez la configuration d’adresse IP que vous souhaitez prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="0b6ab-108">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span> <span data-ttu-id="0b6ab-109">Les figures suivantes montrent une configuration double pile pour l’interface interne et l’interface externe.</span><span class="sxs-lookup"><span data-stu-id="0b6ab-109">The following figures show a dual stack configuration for the internal interface and the external interface.</span></span>
    
    <span data-ttu-id="0b6ab-110">**Interface interne de serveur Edge à double pile**</span><span class="sxs-lookup"><span data-stu-id="0b6ab-110">**Dual stacked Edge Server internal interface**</span></span>
    
    <span data-ttu-id="0b6ab-111">![Page de propriétés générales de Lync Server](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Page de propriétés générales de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="0b6ab-111">![Lync Server general properties page](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server general properties page")</span></span>
    
    <span data-ttu-id="0b6ab-112">**Interface externe de serveur Edge à double pile**</span><span class="sxs-lookup"><span data-stu-id="0b6ab-112">**Dual stacked Edge Server external interface**</span></span>
    
    <span data-ttu-id="0b6ab-113">![Page tronçon suivant/configuration externe de Lync Server](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Page tronçon suivant/configuration externe de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="0b6ab-113">![Lync Server next hop/external configuration page](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server next hop/external configuration page")</span></span>

3.  <span data-ttu-id="0b6ab-114">Pour chaque type d’adresse que vous sélectionnez, vous devez fournir les adresses internes et externes appropriées.</span><span class="sxs-lookup"><span data-stu-id="0b6ab-114">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

