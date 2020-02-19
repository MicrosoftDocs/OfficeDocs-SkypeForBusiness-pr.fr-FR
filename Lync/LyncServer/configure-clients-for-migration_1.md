---
title: Configurer les clients pour la migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 542ee4d581d4df26a528a14fda5de792c2a2ad09
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a><span data-ttu-id="5e68f-102">Configurer les clients pour la migration</span><span class="sxs-lookup"><span data-stu-id="5e68f-102">Configure clients for migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e68f-103">_**Dernière modification de la rubrique :** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="5e68f-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="5e68f-104">Cette rubrique contient les étapes de déploiement de clients recommandées que vous devez prendre avant de migrer vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e68f-104">This topic contains the recommended client deployment steps you should take prior to migrating to Lync Server 2013.</span></span> <span data-ttu-id="5e68f-105">Ces modifications de configuration doivent être effectuées sur Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="5e68f-105">These configuration changes should be made on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="5e68f-106">Il est très important que vous suiviez ces étapes avant de procéder à la migration.</span><span class="sxs-lookup"><span data-stu-id="5e68f-106">It is very important that you perform these steps prior to migrating.</span></span> <span data-ttu-id="5e68f-107">Pour plus d’informations, reportez-vous à la rubrique [Planning for clients and Devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="5e68f-107">For details, see [Planning for clients and devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span></span>

<div>

## <a name="to-configure-clients-prior-to-migration"></a><span data-ttu-id="5e68f-108">Pour configurer les clients avant la migration</span><span class="sxs-lookup"><span data-stu-id="5e68f-108">To configure clients prior to migration</span></span>

1.  <span data-ttu-id="5e68f-109">Déployez les dernières mises à jour du serveur, du client et du périphérique Office Communications Server 2007 R2 (correctifs) :</span><span class="sxs-lookup"><span data-stu-id="5e68f-109">Deploy the most recent Office Communications Server 2007 R2 server, client, and device updates (hotfixes):</span></span>
    
      - [<span data-ttu-id="5e68f-110">Appliquer les mises à jour d’Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="5e68f-110">Apply Office Communications Server 2007 R2 updates</span></span>](apply-office-communications-server-2007-r2-updates.md)
    
      - [<span data-ttu-id="5e68f-111">Description du package de mise à jour cumulative pour Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="5e68f-111">Description of the cumulative update package for Communicator 2007 R2</span></span>](https://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [<span data-ttu-id="5e68f-112">Obtention de mises à jour logicielles pour les périphériques</span><span class="sxs-lookup"><span data-stu-id="5e68f-112">Obtaining Software Updates for Devices</span></span>](https://go.microsoft.com/fwlink/?linkid=335809)

2.  <span data-ttu-id="5e68f-113">Sur Office Communications Server 2007 R2, utilisez le filtrage de version du client pour autoriser uniquement les clients Office Communications Server 2007 R2 sur lesquels les mises à jour les plus récentes sont installées.</span><span class="sxs-lookup"><span data-stu-id="5e68f-113">On Office Communications Server 2007 R2, use Client Version Filtering to allow only Office Communications Server 2007 R2 clients with the most current updates installed to sign in.</span></span>

3.  <span data-ttu-id="5e68f-114">Sur Office Communications Server 2007 R2, utilisez le filtrage de version du client pour bloquer la connexion des clients Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e68f-114">On Office Communications Server 2007 R2, use Client Version Filtering to block Lync Server 2013 clients from signing in.</span></span> <span data-ttu-id="5e68f-115">Suivez les étapes décrites dans **Configuring Client version Filtering** à [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) la rubrique pour ajouter les filtres de version répertoriés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="5e68f-115">Follow the steps described in **Configuring Client Version Filtering** at [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) to add the version filters listed in the following table.</span></span> <span data-ttu-id="5e68f-116">Pour chaque filtre de version, assignez l’action **Bloquer**.</span><span class="sxs-lookup"><span data-stu-id="5e68f-116">For each version filter, assign the action **Block**.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="5e68f-117">Client</span><span class="sxs-lookup"><span data-stu-id="5e68f-117">Client</span></span></th>
    <th><span data-ttu-id="5e68f-118">En-tête d’agent utilisateur</span><span class="sxs-lookup"><span data-stu-id="5e68f-118">User agent header</span></span></th>
    <th><span data-ttu-id="5e68f-119">Version</span><span class="sxs-lookup"><span data-stu-id="5e68f-119">Version</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5e68f-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="5e68f-120">Lync 2013</span></span></p></td>
    <td><p><span data-ttu-id="5e68f-121">O</span><span class="sxs-lookup"><span data-stu-id="5e68f-121">OC</span></span></p></td>
    <td><p><span data-ttu-id="5e68f-122">15.*.*. \*</span><span class="sxs-lookup"><span data-stu-id="5e68f-122">15.*.*.\*</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5e68f-123">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="5e68f-123">Lync Web App</span></span></p></td>
    <td><p><span data-ttu-id="5e68f-124">CWA</span><span class="sxs-lookup"><span data-stu-id="5e68f-124">CWA</span></span></p></td>
    <td><p><span data-ttu-id="5e68f-125">5.*.*. \*</span><span class="sxs-lookup"><span data-stu-id="5e68f-125">5.*.*.\*</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5e68f-126">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="5e68f-126">Lync Phone Edition</span></span></p></td>
    <td><p><span data-ttu-id="5e68f-127">OCPhone</span><span class="sxs-lookup"><span data-stu-id="5e68f-127">OCPhone</span></span></p></td>
    <td><p><span data-ttu-id="5e68f-128">4.*..* \*</span><span class="sxs-lookup"><span data-stu-id="5e68f-128">4.*.*.\*</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

