---
title: 'Lync Server 2013 : Liste de vérification du déploiement pour le contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dd425d53a282cc24fed8ad2f8be9acc5bf42209
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="bf02f-102">Liste de vérification du déploiement pour le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf02f-102">Deployment checklist for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf02f-103">_**Dernière modification de la rubrique:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="bf02f-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="bf02f-104">Pour planifier efficacement le contrôle d’admission des appels, vous devez tenir compte des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="bf02f-104">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="bf02f-105">Conditions préalables pour le déploiement de CAC.</span><span class="sxs-lookup"><span data-stu-id="bf02f-105">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="bf02f-106">Informations requises pour les décisions CAC et de configuration que vous devez effectuer avant le déploiement.</span><span class="sxs-lookup"><span data-stu-id="bf02f-106">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="bf02f-107">Prérequis de déploiement pour le contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="bf02f-107">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="bf02f-108">Avant de déployer le contrôle d’admission des appels, vous devez déjà avoir déployé vos serveurs internes Lync Server 2013, y compris un pool frontal ou un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="bf02f-108">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="bf02f-109">Exigences en matière de contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="bf02f-109">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="bf02f-110">Le tableau suivant récapitule les informations requises pour le déploiement du contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="bf02f-110">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="bf02f-111">Exigences relatives aux informations pour le déploiement de contrôles d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="bf02f-111">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf02f-112">Information</span><span class="sxs-lookup"><span data-stu-id="bf02f-112">Information</span></span></th>
<th><span data-ttu-id="bf02f-113">Résumé des informations requises</span><span class="sxs-lookup"><span data-stu-id="bf02f-113">Summary of Information Required</span></span></th>
<th><span data-ttu-id="bf02f-114">Documentation</span><span class="sxs-lookup"><span data-stu-id="bf02f-114">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf02f-115">Fonctionnalités du serveur Lync requises par votre organisation</span><span class="sxs-lookup"><span data-stu-id="bf02f-115">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bf02f-116">Fonctionnalités devant être prises en charge par votre organisation</span><span class="sxs-lookup"><span data-stu-id="bf02f-116">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="bf02f-117">Fonctionnalités à activer pour les utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="bf02f-117">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bf02f-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="bf02f-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf02f-119">Topologies et composants à déployer</span><span class="sxs-lookup"><span data-stu-id="bf02f-119">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bf02f-120">Les composants liés au CAC sont automatiquement installés dans le cadre de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf02f-120">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bf02f-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="bf02f-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf02f-122">Configuration système requise</span><span class="sxs-lookup"><span data-stu-id="bf02f-122">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bf02f-123">Configuration matérielle requise</span><span class="sxs-lookup"><span data-stu-id="bf02f-123">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="bf02f-124">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="bf02f-124">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="bf02f-125">Exigences en matière de colocalisation</span><span class="sxs-lookup"><span data-stu-id="bf02f-125">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bf02f-126"><a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="bf02f-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf02f-127">Conditions d’infrastructure requises</span><span class="sxs-lookup"><span data-stu-id="bf02f-127">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bf02f-128">Aucun besoin d’infrastructure spécifique n’est nécessaire pour le CAC</span><span class="sxs-lookup"><span data-stu-id="bf02f-128">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bf02f-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Configuration requise pour l’infrastructure pour le contrôle d’admission des appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="bf02f-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf02f-130">Exigences relatives à l’interface réseau</span><span class="sxs-lookup"><span data-stu-id="bf02f-130">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bf02f-131">Informations d’interface interne et externe</span><span class="sxs-lookup"><span data-stu-id="bf02f-131">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="bf02f-132">Informations de routage (y compris les informations sur le <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>blog nexthop à partir du canal de réponse client de l’équipe Microsoft Lync Server)</span><span class="sxs-lookup"><span data-stu-id="bf02f-132">Routing information (including information on the NextHop blog at <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bf02f-133"><a href="lync-server-2013-deploying-external-user-access.md">Déploiement de l’accès des utilisateurs externes dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="bf02f-133"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf02f-134">Stratégie de déploiement</span><span class="sxs-lookup"><span data-stu-id="bf02f-134">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bf02f-135">Séquence de déploiement</span><span class="sxs-lookup"><span data-stu-id="bf02f-135">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="bf02f-136">Groupe de travail ou domaine</span><span class="sxs-lookup"><span data-stu-id="bf02f-136">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="bf02f-137">Sécurité</span><span class="sxs-lookup"><span data-stu-id="bf02f-137">Security</span></span></p></li>
<li><p><span data-ttu-id="bf02f-138">Surveillance et audit</span><span class="sxs-lookup"><span data-stu-id="bf02f-138">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="bf02f-139">Considérations en matière de matériel</span><span class="sxs-lookup"><span data-stu-id="bf02f-139">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bf02f-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Meilleures pratiques liées au contrôle d’admission des appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="bf02f-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf02f-141">Processus de déploiement</span><span class="sxs-lookup"><span data-stu-id="bf02f-141">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bf02f-142">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="bf02f-142">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="bf02f-143">Exigences relatives aux informations</span><span class="sxs-lookup"><span data-stu-id="bf02f-143">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="bf02f-144">Processus et procédures</span><span class="sxs-lookup"><span data-stu-id="bf02f-144">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bf02f-145"><a href="lync-server-2013-configure-call-admission-control.md">Configurer le contrôle d’admission des appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="bf02f-145"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

