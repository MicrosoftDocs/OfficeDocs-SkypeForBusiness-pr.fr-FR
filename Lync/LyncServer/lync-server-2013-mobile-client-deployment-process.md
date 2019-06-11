---
title: 'Lync Server 2013: processus de déploiement d’un client mobile'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobile client deployment process
ms:assetid: 6498235b-2fa9-421d-bfa0-0ccc09508dbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690982(v=OCS.15)
ms:contentKeyID: 51541484
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0d0bf17fe4906d49fefd8bd319d25d1268191e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="e8381-102">Processus de déploiement d’un client mobile dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8381-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8381-103">_**Dernière modification de la rubrique:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e8381-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e8381-104">Après l’exécution d’un déploiement de Microsoft Lync Server 2013, les utilisateurs peuvent installer l’application Lync 2013 depuis mobile Marketplace qu’elles ont l’habitude d’utiliser pour leur appareil spécifique.</span><span class="sxs-lookup"><span data-stu-id="e8381-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="e8381-105">Processus de déploiement de mobile Lync</span><span class="sxs-lookup"><span data-stu-id="e8381-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8381-106">Phase</span><span class="sxs-lookup"><span data-stu-id="e8381-106">Phase</span></span></th>
<th><span data-ttu-id="e8381-107">Étapes</span><span class="sxs-lookup"><span data-stu-id="e8381-107">Steps</span></span></th>
<th><span data-ttu-id="e8381-108">Autorisations</span><span class="sxs-lookup"><span data-stu-id="e8381-108">Permissions</span></span></th>
<th><span data-ttu-id="e8381-109">Documentation</span><span class="sxs-lookup"><span data-stu-id="e8381-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8381-110">Effectuer des tâches préconfigurées.</span><span class="sxs-lookup"><span data-stu-id="e8381-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e8381-111">Vérifiez le déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8381-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="e8381-112">Vérifier les exigences de certificat.</span><span class="sxs-lookup"><span data-stu-id="e8381-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e8381-113">Administrateur</span><span class="sxs-lookup"><span data-stu-id="e8381-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="e8381-114"><a href="lync-server-2013-planning-for-mobility.md">Planification de la mobilité dans Lync Server 2013</a> dans la documentation de planification du serveur.</span><span class="sxs-lookup"><span data-stu-id="e8381-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="e8381-115"><a href="lync-server-2013-deploying-mobility.md">Déploiement de la mobilité dans Lync Server 2013</a> dans la documentation de déploiement du serveur.</span><span class="sxs-lookup"><span data-stu-id="e8381-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="e8381-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Exigences d’infrastructure de certificat pour Lync Server 2013</a> dans la documentation de planification du serveur.</span><span class="sxs-lookup"><span data-stu-id="e8381-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8381-117">Installez l’application Lync sur un appareil de test.</span><span class="sxs-lookup"><span data-stu-id="e8381-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e8381-118">Installation requise.</span><span class="sxs-lookup"><span data-stu-id="e8381-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="e8381-119">Installez à partir du Marketplace spécifique à l’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="e8381-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e8381-120">Administrateur</span><span class="sxs-lookup"><span data-stu-id="e8381-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="e8381-121">Instructions d’installation propres à l’appareil mobile dans le <a href="lync-server-2013-deploying-mobile-clients.md">déploiement de clients mobiles dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e8381-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8381-122">Configurer le client.</span><span class="sxs-lookup"><span data-stu-id="e8381-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e8381-123">Configurer les paramètres de connexion et les informations sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="e8381-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e8381-124">Administrateur</span><span class="sxs-lookup"><span data-stu-id="e8381-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="e8381-125"><a href="lync-server-2013-deploying-mobile-clients.md">Déploiement de clients mobiles dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e8381-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8381-126">Testez des scénarios mobiles.</span><span class="sxs-lookup"><span data-stu-id="e8381-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e8381-127">Testez la messagerie instantanée et la présence.</span><span class="sxs-lookup"><span data-stu-id="e8381-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="e8381-128">Testez la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="e8381-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="e8381-129">Recherchez un contact dans l’annuaire de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="e8381-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="e8381-130">Testez les notifications de transmission.</span><span class="sxs-lookup"><span data-stu-id="e8381-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e8381-131">Administrateur</span><span class="sxs-lookup"><span data-stu-id="e8381-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="e8381-132">Instructions de vérification spécifiques à l’appareil mobile dans le <a href="lync-server-2013-deploying-mobile-clients.md">déploiement de clients mobiles dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e8381-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8381-133">Installez l’application Lync sur les téléphones mobiles.</span><span class="sxs-lookup"><span data-stu-id="e8381-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e8381-134">Installation requise.</span><span class="sxs-lookup"><span data-stu-id="e8381-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="e8381-135">Installez à partir du Marketplace spécifique à l’appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="e8381-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e8381-136">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="e8381-136">User</span></span></p></td>
<td><p><span data-ttu-id="e8381-137">Instructions d’installation propres à l’appareil mobile dans le <a href="lync-server-2013-deploying-mobile-clients.md">déploiement de clients mobiles dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e8381-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

