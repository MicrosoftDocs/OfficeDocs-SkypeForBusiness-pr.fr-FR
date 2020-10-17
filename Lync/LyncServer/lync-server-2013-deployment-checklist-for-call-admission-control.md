---
title: 'Lync Server 2013 : liste de vérification du déploiement pour le contrôle d’admission des appels'
description: 'Lync Server 2013 : liste de vérification du déploiement pour le contrôle d’admission des appels.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea5b16d41228faf01637e7e0d78f5ce56f950a19
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557690"
---
# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="0db23-103">Liste de vérification du déploiement pour le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0db23-103">Deployment checklist for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0db23-104">_**Dernière modification de la rubrique :** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="0db23-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="0db23-105">Pour planifier efficacement le service Contrôle d’admission des appels (CAC), vous devez tenir compte :</span><span class="sxs-lookup"><span data-stu-id="0db23-105">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="0db23-106">des conditions préalables au déploiement du service Contrôle d’admission des appels (CAC) ;</span><span class="sxs-lookup"><span data-stu-id="0db23-106">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="0db23-107">des informations requises pour déployer le service Contrôle d’admission des appels et des décisions de configuration à prendre avant le déploiement ;</span><span class="sxs-lookup"><span data-stu-id="0db23-107">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="0db23-108">Conditions préalables au déploiement du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="0db23-108">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="0db23-109">Avant de déployer le contrôle d’admission des appels, vous devez déjà avoir déployé vos serveurs internes Lync Server 2013, y compris un pool frontal ou un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0db23-109">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="0db23-110">Informations requises pour le contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="0db23-110">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="0db23-111">Le tableau suivant résume les informations requises pour le déploiement du service Contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="0db23-111">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="0db23-112">Informations requises pour le déploiement du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="0db23-112">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0db23-113">Informations</span><span class="sxs-lookup"><span data-stu-id="0db23-113">Information</span></span></th>
<th><span data-ttu-id="0db23-114">Résumé des informations requises</span><span class="sxs-lookup"><span data-stu-id="0db23-114">Summary of Information Required</span></span></th>
<th><span data-ttu-id="0db23-115">Documentation</span><span class="sxs-lookup"><span data-stu-id="0db23-115">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0db23-116">Fonctionnalités Lync Server requises par votre organisation</span><span class="sxs-lookup"><span data-stu-id="0db23-116">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0db23-117">Fonctionnalités à prendre en charge par votre organisation</span><span class="sxs-lookup"><span data-stu-id="0db23-117">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="0db23-118">Fonctionnalités à activer pour les utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="0db23-118">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0db23-119"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0db23-119"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0db23-120">Topologies et composants à déployer</span><span class="sxs-lookup"><span data-stu-id="0db23-120">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0db23-121">Les composants liés au contrôle d’admission des problèmes sont installés automatiquement dans le cadre de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0db23-121">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0db23-122"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0db23-122"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0db23-123">Configuration système requise</span><span class="sxs-lookup"><span data-stu-id="0db23-123">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0db23-124">Configuration matérielle requise</span><span class="sxs-lookup"><span data-stu-id="0db23-124">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="0db23-125">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="0db23-125">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="0db23-126">Configuration de colocation requise</span><span class="sxs-lookup"><span data-stu-id="0db23-126">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0db23-127"><a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0db23-127"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0db23-128">Conditions d’infrastructure requises</span><span class="sxs-lookup"><span data-stu-id="0db23-128">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0db23-129">Aucune configuration d’infrastructure spécifique n’est requise pour CAC</span><span class="sxs-lookup"><span data-stu-id="0db23-129">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0db23-130"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Configuration requise pour l’infrastructure pour le contrôle d’admission des appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0db23-130"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0db23-131">Configuration de l’interface réseau requise</span><span class="sxs-lookup"><span data-stu-id="0db23-131">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0db23-132">Informations d’interface interne et externe</span><span class="sxs-lookup"><span data-stu-id="0db23-132">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="0db23-133">Informations de routage (notamment des informations sur le blog NextHop à l’adresse <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a> , le canal de réponse client de l’équipe Microsoft Lync Server)</span><span class="sxs-lookup"><span data-stu-id="0db23-133">Routing information (including information on the NextHop blog at <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0db23-134"><a href="lync-server-2013-deploying-external-user-access.md">Déploiement de l’accès des utilisateurs externes dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0db23-134"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0db23-135">Stratégie de déploiement</span><span class="sxs-lookup"><span data-stu-id="0db23-135">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0db23-136">Séquence de déploiement</span><span class="sxs-lookup"><span data-stu-id="0db23-136">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="0db23-137">Groupe de travail ou domaine</span><span class="sxs-lookup"><span data-stu-id="0db23-137">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="0db23-138">Sécurité</span><span class="sxs-lookup"><span data-stu-id="0db23-138">Security</span></span></p></li>
<li><p><span data-ttu-id="0db23-139">Surveillance et audit</span><span class="sxs-lookup"><span data-stu-id="0db23-139">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="0db23-140">Considérations matérielles</span><span class="sxs-lookup"><span data-stu-id="0db23-140">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0db23-141"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Meilleures pratiques pour le contrôle d’admission des appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0db23-141"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0db23-142">Processus de déploiement</span><span class="sxs-lookup"><span data-stu-id="0db23-142">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0db23-143">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="0db23-143">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="0db23-144">Informations requises</span><span class="sxs-lookup"><span data-stu-id="0db23-144">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="0db23-145">Processus et procédures</span><span class="sxs-lookup"><span data-stu-id="0db23-145">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0db23-146"><a href="lync-server-2013-configure-call-admission-control.md">Configurer le contrôle d’admission des appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0db23-146"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

