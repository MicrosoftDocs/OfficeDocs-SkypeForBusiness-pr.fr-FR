---
title: 'Lync Server 2013 : liste de vérification du déploiement pour le contrôle d’admission des appels'
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
ms.openlocfilehash: d68f13c636b24729db989f25da7055333968cbbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="c2a80-102">Liste de vérification du déploiement pour le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2a80-102">Deployment checklist for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2a80-103">_**Dernière modification de la rubrique :** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="c2a80-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="c2a80-104">Pour planifier efficacement le service Contrôle d’admission des appels (CAC), vous devez tenir compte :</span><span class="sxs-lookup"><span data-stu-id="c2a80-104">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="c2a80-105">des conditions préalables au déploiement du service Contrôle d’admission des appels (CAC) ;</span><span class="sxs-lookup"><span data-stu-id="c2a80-105">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="c2a80-106">des informations requises pour déployer le service Contrôle d’admission des appels et des décisions de configuration à prendre avant le déploiement ;</span><span class="sxs-lookup"><span data-stu-id="c2a80-106">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="c2a80-107">Conditions préalables au déploiement du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="c2a80-107">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="c2a80-108">Avant de déployer le contrôle d’admission des appels, vous devez déjà avoir déployé vos serveurs internes Lync Server 2013, y compris un pool frontal ou un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c2a80-108">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="c2a80-109">Informations requises pour le contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="c2a80-109">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="c2a80-110">Le tableau suivant résume les informations requises pour le déploiement du service Contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="c2a80-110">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="c2a80-111">Informations requises pour le déploiement du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="c2a80-111">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2a80-112">Informations</span><span class="sxs-lookup"><span data-stu-id="c2a80-112">Information</span></span></th>
<th><span data-ttu-id="c2a80-113">Résumé des informations requises</span><span class="sxs-lookup"><span data-stu-id="c2a80-113">Summary of Information Required</span></span></th>
<th><span data-ttu-id="c2a80-114">Documentation</span><span class="sxs-lookup"><span data-stu-id="c2a80-114">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2a80-115">Fonctionnalités Lync Server requises par votre organisation</span><span class="sxs-lookup"><span data-stu-id="c2a80-115">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c2a80-116">Fonctionnalités à prendre en charge par votre organisation</span><span class="sxs-lookup"><span data-stu-id="c2a80-116">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="c2a80-117">Fonctionnalités à activer pour les utilisateurs individuels</span><span class="sxs-lookup"><span data-stu-id="c2a80-117">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c2a80-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c2a80-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2a80-119">Topologies et composants à déployer</span><span class="sxs-lookup"><span data-stu-id="c2a80-119">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c2a80-120">Les composants liés au contrôle d’admission des problèmes sont installés automatiquement dans le cadre de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2a80-120">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c2a80-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c2a80-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2a80-122">Configuration système requise</span><span class="sxs-lookup"><span data-stu-id="c2a80-122">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c2a80-123">Configuration matérielle requise</span><span class="sxs-lookup"><span data-stu-id="c2a80-123">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="c2a80-124">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="c2a80-124">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="c2a80-125">Configuration de colocation requise</span><span class="sxs-lookup"><span data-stu-id="c2a80-125">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c2a80-126"><a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c2a80-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2a80-127">Conditions d’infrastructure requises</span><span class="sxs-lookup"><span data-stu-id="c2a80-127">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c2a80-128">Aucune configuration d’infrastructure spécifique n’est requise pour CAC</span><span class="sxs-lookup"><span data-stu-id="c2a80-128">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c2a80-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Configuration requise pour l’infrastructure pour le contrôle d’admission des appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c2a80-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2a80-130">Configuration de l’interface réseau requise</span><span class="sxs-lookup"><span data-stu-id="c2a80-130">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c2a80-131">Informations d’interface interne et externe</span><span class="sxs-lookup"><span data-stu-id="c2a80-131">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="c2a80-132">Informations de routage (notamment des informations sur le blog <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>nexthop à l’adresse, le canal de réponse client de l’équipe Microsoft Lync Server)</span><span class="sxs-lookup"><span data-stu-id="c2a80-132">Routing information (including information on the NextHop blog at <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c2a80-133"><a href="lync-server-2013-deploying-external-user-access.md">Déploiement de l’accès des utilisateurs externes dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c2a80-133"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2a80-134">Stratégie de déploiement</span><span class="sxs-lookup"><span data-stu-id="c2a80-134">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c2a80-135">Séquence de déploiement</span><span class="sxs-lookup"><span data-stu-id="c2a80-135">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="c2a80-136">Groupe de travail ou domaine</span><span class="sxs-lookup"><span data-stu-id="c2a80-136">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="c2a80-137">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c2a80-137">Security</span></span></p></li>
<li><p><span data-ttu-id="c2a80-138">Surveillance et audit</span><span class="sxs-lookup"><span data-stu-id="c2a80-138">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="c2a80-139">Considérations matérielles</span><span class="sxs-lookup"><span data-stu-id="c2a80-139">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c2a80-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Meilleures pratiques pour le contrôle d’admission des appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c2a80-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2a80-141">Processus de déploiement</span><span class="sxs-lookup"><span data-stu-id="c2a80-141">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c2a80-142">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="c2a80-142">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="c2a80-143">Informations requises</span><span class="sxs-lookup"><span data-stu-id="c2a80-143">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="c2a80-144">Processus et procédures</span><span class="sxs-lookup"><span data-stu-id="c2a80-144">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c2a80-145"><a href="lync-server-2013-configure-call-admission-control.md">Configurer le contrôle d’admission des appels dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c2a80-145"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

