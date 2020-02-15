---
title: 'Lync Server 2013 : processus de déploiement de clients mobiles'
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
ms.openlocfilehash: 841b0349818fd94d828e3aaa93b3f7c9a99f9f00
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="1a44b-102">Processus de déploiement de client mobile dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a44b-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a44b-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="1a44b-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="1a44b-104">Une fois le déploiement de Microsoft Lync Server 2013 terminé, les utilisateurs peuvent installer l’application Lync 2013 à partir du Marketplace mobile qu’ils sont habitués à utiliser pour leur appareil spécifique.</span><span class="sxs-lookup"><span data-stu-id="1a44b-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="1a44b-105">Processus de déploiement de Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="1a44b-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a44b-106">Phase</span><span class="sxs-lookup"><span data-stu-id="1a44b-106">Phase</span></span></th>
<th><span data-ttu-id="1a44b-107">Étapes</span><span class="sxs-lookup"><span data-stu-id="1a44b-107">Steps</span></span></th>
<th><span data-ttu-id="1a44b-108">Autorisations</span><span class="sxs-lookup"><span data-stu-id="1a44b-108">Permissions</span></span></th>
<th><span data-ttu-id="1a44b-109">Documentation</span><span class="sxs-lookup"><span data-stu-id="1a44b-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a44b-110">Exécuter les tâches antérieures à l’installation</span><span class="sxs-lookup"><span data-stu-id="1a44b-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="1a44b-111">Vérifier le déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a44b-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="1a44b-112">Vérifier les exigences de certificat</span><span class="sxs-lookup"><span data-stu-id="1a44b-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="1a44b-113">Administrateur</span><span class="sxs-lookup"><span data-stu-id="1a44b-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="1a44b-114"><a href="lync-server-2013-planning-for-mobility.md">Planification de la mobilité dans Lync server 2013</a> dans la documentation de planification du serveur.</span><span class="sxs-lookup"><span data-stu-id="1a44b-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="1a44b-115"><a href="lync-server-2013-deploying-mobility.md">Déploiement de la mobilité dans Lync server 2013</a> dans la documentation de déploiement du serveur.</span><span class="sxs-lookup"><span data-stu-id="1a44b-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="1a44b-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure Requirements for Lync Server 2013</a> dans la documentation de planification du serveur.</span><span class="sxs-lookup"><span data-stu-id="1a44b-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a44b-117">Installer l’application Lync sur un appareil test</span><span class="sxs-lookup"><span data-stu-id="1a44b-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="1a44b-118">Installer les composants requis</span><span class="sxs-lookup"><span data-stu-id="1a44b-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="1a44b-119">Installer à partir du site Marketplace spécifique à l’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="1a44b-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="1a44b-120">Administrateur</span><span class="sxs-lookup"><span data-stu-id="1a44b-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="1a44b-121">Instructions d’installation spécifiques à l’appareil mobile dans <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1a44b-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a44b-122">Configurer le client</span><span class="sxs-lookup"><span data-stu-id="1a44b-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1a44b-123">Configurer les paramètres de connexion et les informations relatives au serveur</span><span class="sxs-lookup"><span data-stu-id="1a44b-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1a44b-124">Administrateur</span><span class="sxs-lookup"><span data-stu-id="1a44b-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="1a44b-125"><a href="lync-server-2013-deploying-mobile-clients.md">Déploiement de clients mobiles dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1a44b-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a44b-126">Tester des scénarios de mobilité</span><span class="sxs-lookup"><span data-stu-id="1a44b-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="1a44b-127">Tester la messagerie instantanée et la présence.</span><span class="sxs-lookup"><span data-stu-id="1a44b-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="1a44b-128">Tester la conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="1a44b-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="1a44b-129">Rechercher un contact dans l’annuaire d’entreprise</span><span class="sxs-lookup"><span data-stu-id="1a44b-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="1a44b-130">Tester les notifications de type push</span><span class="sxs-lookup"><span data-stu-id="1a44b-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="1a44b-131">Administrateur</span><span class="sxs-lookup"><span data-stu-id="1a44b-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="1a44b-132">Instructions de vérification spécifiques à l’appareil mobile dans <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1a44b-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a44b-133">Installer l’application Lync sur les appareils mobiles</span><span class="sxs-lookup"><span data-stu-id="1a44b-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="1a44b-134">Installer les composants requis</span><span class="sxs-lookup"><span data-stu-id="1a44b-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="1a44b-135">Installer à partir du site Marketplace spécifique à l’appareil mobile</span><span class="sxs-lookup"><span data-stu-id="1a44b-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="1a44b-136">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="1a44b-136">User</span></span></p></td>
<td><p><span data-ttu-id="1a44b-137">Instructions d’installation spécifiques à l’appareil mobile dans <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="1a44b-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

