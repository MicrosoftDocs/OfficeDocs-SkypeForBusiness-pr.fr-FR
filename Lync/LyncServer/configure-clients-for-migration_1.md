---
title: Configuration des clients pour la migration
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710a5cf6cb23b91431b340c44ebe6ff2738b0822
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a><span data-ttu-id="43757-102">Configuration des clients pour la migration</span><span class="sxs-lookup"><span data-stu-id="43757-102">Configure clients for migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43757-103">_**Dernière modification de la rubrique:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="43757-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="43757-104">Cette rubrique contient les étapes de déploiement de client recommandées avant de procéder à la migration vers Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43757-104">This topic contains the recommended client deployment steps you should take prior to migrating to Lync Server 2013.</span></span> <span data-ttu-id="43757-105">Ces modifications de configuration doivent être apportées à Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="43757-105">These configuration changes should be made on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="43757-106">Il est très important que vous effectuiez ces étapes avant de procéder à la migration.</span><span class="sxs-lookup"><span data-stu-id="43757-106">It is very important that you perform these steps prior to migrating.</span></span> <span data-ttu-id="43757-107">Pour plus d’informations, reportez-vous à la section [planification des clients et des appareils dans Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="43757-107">For details, see [Planning for clients and devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span></span>

<div>

## <a name="to-configure-clients-prior-to-migration"></a><span data-ttu-id="43757-108">Pour configurer des clients avant la migration</span><span class="sxs-lookup"><span data-stu-id="43757-108">To configure clients prior to migration</span></span>

1.  <span data-ttu-id="43757-109">Déployez les mises à jour les plus récentes du serveur Office Communications Server 2007 R2, des clients et des appareils (HotFix):</span><span class="sxs-lookup"><span data-stu-id="43757-109">Deploy the most recent Office Communications Server 2007 R2 server, client, and device updates (hotfixes):</span></span>
    
      - [<span data-ttu-id="43757-110">Appliquer des mises à jour d’Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="43757-110">Apply Office Communications Server 2007 R2 updates</span></span>](apply-office-communications-server-2007-r2-updates.md)
    
      - [<span data-ttu-id="43757-111">Description du package de mise à jour cumulative pour Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="43757-111">Description of the cumulative update package for Communicator 2007 R2</span></span>](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [<span data-ttu-id="43757-112">Obtention des mises à jour logicielles pour les appareils</span><span class="sxs-lookup"><span data-stu-id="43757-112">Obtaining Software Updates for Devices</span></span>](http://go.microsoft.com/fwlink/?linkid=335809)

2.  <span data-ttu-id="43757-113">Sur Office Communications Server 2007 R2, utilisez le filtrage de version de client pour autoriser uniquement les clients Office Communications Server 2007 R2 avec les mises à jour les plus récentes pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="43757-113">On Office Communications Server 2007 R2, use Client Version Filtering to allow only Office Communications Server 2007 R2 clients with the most current updates installed to sign in.</span></span>

3.  <span data-ttu-id="43757-114">Sur Office Communications Server 2007 R2, utilisez le filtrage de version de client pour empêcher les clients Lync Server 2013 de se connecter.</span><span class="sxs-lookup"><span data-stu-id="43757-114">On Office Communications Server 2007 R2, use Client Version Filtering to block Lync Server 2013 clients from signing in.</span></span> <span data-ttu-id="43757-115">Suivez la procédure décrite dans la rubrique Configuration du filtrage des [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) versions du **client** à l’adresse pour ajouter les filtres de version indiqués dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="43757-115">Follow the steps described in **Configuring Client Version Filtering** at [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) to add the version filters listed in the following table.</span></span> <span data-ttu-id="43757-116">Pour chaque filtre de version, attribuez le **bloc**d’action.</span><span class="sxs-lookup"><span data-stu-id="43757-116">For each version filter, assign the action **Block**.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="43757-117">Client</span><span class="sxs-lookup"><span data-stu-id="43757-117">Client</span></span></th>
    <th><span data-ttu-id="43757-118">En-tête de l’agent utilisateur</span><span class="sxs-lookup"><span data-stu-id="43757-118">User agent header</span></span></th>
    <th><span data-ttu-id="43757-119">Version</span><span class="sxs-lookup"><span data-stu-id="43757-119">Version</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="43757-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="43757-120">Lync 2013</span></span></p></td>
    <td><p><span data-ttu-id="43757-121">OC</span><span class="sxs-lookup"><span data-stu-id="43757-121">OC</span></span></p></td>
    <td><p><span data-ttu-id="43757-122">15.\*\*.. \*</span><span class="sxs-lookup"><span data-stu-id="43757-122">15.*.*.\*</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="43757-123">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="43757-123">Lync Web App</span></span></p></td>
    <td><p><span data-ttu-id="43757-124">CWA</span><span class="sxs-lookup"><span data-stu-id="43757-124">CWA</span></span></p></td>
    <td><p><span data-ttu-id="43757-125">5.\*\*.. \*</span><span class="sxs-lookup"><span data-stu-id="43757-125">5.*.*.\*</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="43757-126">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="43757-126">Lync Phone Edition</span></span></p></td>
    <td><p><span data-ttu-id="43757-127">OCPhone</span><span class="sxs-lookup"><span data-stu-id="43757-127">OCPhone</span></span></p></td>
    <td><p><span data-ttu-id="43757-128">4.\*\*.. \*</span><span class="sxs-lookup"><span data-stu-id="43757-128">4.*.*.\*</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

