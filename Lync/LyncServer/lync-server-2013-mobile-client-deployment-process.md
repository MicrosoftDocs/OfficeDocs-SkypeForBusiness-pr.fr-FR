---
title: 'Lync Server 2013 : processus de déploiement de clients mobiles'
description: 'Lync Server 2013 : processus de déploiement de clients mobiles.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobile client deployment process
ms:assetid: 6498235b-2fa9-421d-bfa0-0ccc09508dbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690982(v=OCS.15)
ms:contentKeyID: 51541484
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa4e9e1d272915e06009df5c06480309ce104e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563480"
---
# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="34a57-103">Processus de déploiement de client mobile dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34a57-103">Mobile client deployment process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34a57-104">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="34a57-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="34a57-105">Une fois le déploiement de Microsoft Lync Server 2013 terminé, les utilisateurs peuvent installer l’application Lync 2013 à partir du Marketplace mobile qu’ils sont habitués à utiliser pour leur appareil spécifique.</span><span class="sxs-lookup"><span data-stu-id="34a57-105">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="34a57-106">Processus de déploiement de Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="34a57-106">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34a57-107">Phase</span><span class="sxs-lookup"><span data-stu-id="34a57-107">Phase</span></span></th>
<th><span data-ttu-id="34a57-108">Étapes</span><span class="sxs-lookup"><span data-stu-id="34a57-108">Steps</span></span></th>
<th><span data-ttu-id="34a57-109">Autorisations</span><span class="sxs-lookup"><span data-stu-id="34a57-109">Permissions</span></span></th>
<th><span data-ttu-id="34a57-110">Documentation</span><span class="sxs-lookup"><span data-stu-id="34a57-110">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34a57-111">Exécuter les tâches antérieures à l’installation</span><span class="sxs-lookup"><span data-stu-id="34a57-111">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="34a57-112">Vérifier le déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="34a57-112">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="34a57-113">Vérifier les exigences de certificat</span><span class="sxs-lookup"><span data-stu-id="34a57-113">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="34a57-114">Administrateur</span><span class="sxs-lookup"><span data-stu-id="34a57-114">Administrator</span></span></p></td>
<td><p><span data-ttu-id="34a57-115"><a href="lync-server-2013-planning-for-mobility.md">Planification de la mobilité dans Lync server 2013</a> dans la documentation de planification du serveur.</span><span class="sxs-lookup"><span data-stu-id="34a57-115"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="34a57-116"><a href="lync-server-2013-deploying-mobility.md">Déploiement de la mobilité dans Lync server 2013</a> dans la documentation de déploiement du serveur.</span><span class="sxs-lookup"><span data-stu-id="34a57-116"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="34a57-117"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure Requirements for Lync Server 2013</a> dans la documentation de planification du serveur.</span><span class="sxs-lookup"><span data-stu-id="34a57-117"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a57-118">Installer l’application Lync sur un appareil test</span><span class="sxs-lookup"><span data-stu-id="34a57-118">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="34a57-119">Installer les composants requis</span><span class="sxs-lookup"><span data-stu-id="34a57-119">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="34a57-120">Installer à partir du site Marketplace spécifique à l’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="34a57-120">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="34a57-121">Administrateur</span><span class="sxs-lookup"><span data-stu-id="34a57-121">Administrator</span></span></p></td>
<td><p><span data-ttu-id="34a57-122">Instructions d’installation spécifiques à l’appareil mobile dans <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="34a57-122">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a57-123">Configurer le client</span><span class="sxs-lookup"><span data-stu-id="34a57-123">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="34a57-124">Configurer les paramètres de connexion et les informations relatives au serveur</span><span class="sxs-lookup"><span data-stu-id="34a57-124">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="34a57-125">Administrateur</span><span class="sxs-lookup"><span data-stu-id="34a57-125">Administrator</span></span></p></td>
<td><p><span data-ttu-id="34a57-126"><a href="lync-server-2013-deploying-mobile-clients.md">Déploiement de clients mobiles dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="34a57-126"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34a57-127">Tester des scénarios de mobilité</span><span class="sxs-lookup"><span data-stu-id="34a57-127">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="34a57-128">Tester la messagerie instantanée et la présence.</span><span class="sxs-lookup"><span data-stu-id="34a57-128">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="34a57-129">Tester la conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="34a57-129">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="34a57-130">Rechercher un contact dans l’annuaire d’entreprise</span><span class="sxs-lookup"><span data-stu-id="34a57-130">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="34a57-131">Tester les notifications de type push</span><span class="sxs-lookup"><span data-stu-id="34a57-131">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="34a57-132">Administrateur</span><span class="sxs-lookup"><span data-stu-id="34a57-132">Administrator</span></span></p></td>
<td><p><span data-ttu-id="34a57-133">Instructions de vérification spécifiques à l’appareil mobile dans <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="34a57-133">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34a57-134">Installer l’application Lync sur les appareils mobiles</span><span class="sxs-lookup"><span data-stu-id="34a57-134">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="34a57-135">Installer les composants requis</span><span class="sxs-lookup"><span data-stu-id="34a57-135">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="34a57-136">Installer à partir du site Marketplace spécifique à l’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="34a57-136">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="34a57-137">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="34a57-137">User</span></span></p></td>
<td><p><span data-ttu-id="34a57-138">Instructions d’installation spécifiques à l’appareil mobile dans <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="34a57-138">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

