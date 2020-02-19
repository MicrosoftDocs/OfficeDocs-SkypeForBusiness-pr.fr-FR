---
title: 'Lync Server 2013 : processus de déploiement pour l’intégration de la messagerie unifiée Exchange hébergée'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f55e8f573b4000d56a002adb9bd40d03b2021cba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="18876-102">Processus de déploiement pour l’intégration de la messagerie unifiée Exchange hébergée à Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18876-102">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18876-103">_**Dernière modification de la rubrique :** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="18876-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="18876-104">Pour une planification efficace de l’intégration de Lync Server 2013 à la messagerie unifiée Exchange hébergée, vous devez tenir compte des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="18876-104">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="18876-105">Conditions préalables à l’intégration de Lync Server 2013 avec la messagerie unifiée Exchange hébergée</span><span class="sxs-lookup"><span data-stu-id="18876-105">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="18876-106">Étapes requises au cours du processus d’intégration</span><span class="sxs-lookup"><span data-stu-id="18876-106">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="18876-107">Conditions préalables au déploiement pour l’intégration à la messagerie unifiée Exchange hébergée</span><span class="sxs-lookup"><span data-stu-id="18876-107">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="18876-108">Avant de commencer le processus d’intégration, vous devez déjà avoir déployé Lync Server 2013 (au minimum, un pool frontal ou un serveur Standard Edition Server), un serveur Edge et des clients Lync 2013 ou Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="18876-108">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="18876-109">Processus d’intégration</span><span class="sxs-lookup"><span data-stu-id="18876-109">Integration Process</span></span>

<span data-ttu-id="18876-110">Le tableau suivant présente une vue d’ensemble du processus d’intégration de la messagerie unifiée Exchange hébergée.</span><span class="sxs-lookup"><span data-stu-id="18876-110">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="18876-111">Pour plus d’informations sur les étapes de déploiement, voir la rubrique relative à la [messagerie vocale Exchange hébergée pour les utilisateurs Lync Server 2013](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="18876-111">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18876-112">Phase</span><span class="sxs-lookup"><span data-stu-id="18876-112">Phase</span></span></th>
<th><span data-ttu-id="18876-113">Étapes</span><span class="sxs-lookup"><span data-stu-id="18876-113">Steps</span></span></th>
<th><span data-ttu-id="18876-114">Droits et autorisations</span><span class="sxs-lookup"><span data-stu-id="18876-114">Rights and permissions</span></span></th>
<th><span data-ttu-id="18876-115">Documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="18876-115">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18876-116">Configurez le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="18876-116">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="18876-117">Configurez le serveur Edge pour la fédération.</span><span class="sxs-lookup"><span data-stu-id="18876-117">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="18876-118">Répliquez manuellement les données sur le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="18876-118">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="18876-119">Configurez le fournisseur d’hébergement sur le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="18876-119">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="18876-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="18876-120">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="18876-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configuration du serveur Edge pour l’intégration à la messagerie unifiée Exchange hébergée</a></span><span class="sxs-lookup"><span data-stu-id="18876-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18876-122">Configurez la stratégie de messagerie vocale hébergée.</span><span class="sxs-lookup"><span data-stu-id="18876-122">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="18876-123">Modifiez la stratégie globale de messagerie vocale hébergée ou créez une stratégie de messagerie vocale hébergée avec une étendue de site ou par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="18876-123">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="18876-124">Lorsque les stratégies sont définies avec une étendue par utilisateur, attribuez-les à des utilisateurs ou à des groupes.</span><span class="sxs-lookup"><span data-stu-id="18876-124">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="18876-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="18876-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="18876-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Gérer les stratégies de messagerie vocale hébergée dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="18876-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18876-127">Activez les utilisateurs pour la messagerie vocale hébergée.</span><span class="sxs-lookup"><span data-stu-id="18876-127">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18876-128">Configurez les comptes des utilisateurs qui possèdent des boîtes aux lettres sur un service Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="18876-128">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="18876-129">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="18876-129">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="18876-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Activer les utilisateurs pour la messagerie vocale hébergée dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="18876-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18876-131">Configurez les objets contact hébergés.</span><span class="sxs-lookup"><span data-stu-id="18876-131">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="18876-132">Créez des objets contact de standard automatique pour la messagerie unifiée Exchange hébergée.</span><span class="sxs-lookup"><span data-stu-id="18876-132">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="18876-133">Créez des objets contact d’accès abonné pour la messagerie unifiée Exchange hébergée.</span><span class="sxs-lookup"><span data-stu-id="18876-133">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="18876-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="18876-134">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="18876-135">Pour créer, modifier ou supprimer des objets contact, l’utilisateur qui exécute la cmdlet New-CsExUmContact, Set-CsExUmContact ou Remove-CsExUmContact doit posséder l’autorisation appropriée sur l’unité d’organisation Active Directory où sont stockés les nouveaux objets contact.</span><span class="sxs-lookup"><span data-stu-id="18876-135">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="18876-136">Cette autorisation peut être accordée en exécutant la cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="18876-136">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="18876-137">Pour plus d’informations, voir la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="18876-137">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="18876-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Créer des objets contact pour la messagerie unifiée Exchange hébergée dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="18876-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

