---
title: Introduction
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 912c6a1704438106a3ffbb178d9f03a536489757
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="introduction"></a><span data-ttu-id="9daf2-102">Introduction</span><span class="sxs-lookup"><span data-stu-id="9daf2-102">Introduction</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9daf2-103">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="9daf2-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="9daf2-104">L’outil de contrainte et de performances de Lync Server 2013 (appelé LyncPerfTool) peut simuler la charge utilisateur des types suivants :</span><span class="sxs-lookup"><span data-stu-id="9daf2-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9daf2-105">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="9daf2-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="9daf2-106">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="9daf2-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9daf2-107">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="9daf2-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="9daf2-108">Voix sur IP (VoIP), y compris la simulation de réseau téléphonique commuté (PSTN)</span><span class="sxs-lookup"><span data-stu-id="9daf2-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9daf2-109">Conférence client Web Access</span><span class="sxs-lookup"><span data-stu-id="9daf2-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="9daf2-110">Microsoft Lync 2013 attendant</span><span class="sxs-lookup"><span data-stu-id="9daf2-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9daf2-111">Groupes Response Group</span><span class="sxs-lookup"><span data-stu-id="9daf2-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="9daf2-112">Développement de la liste de distribution</span><span class="sxs-lookup"><span data-stu-id="9daf2-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9daf2-113">Requête de téléchargement du carnet d’adresses et de carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="9daf2-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="9daf2-114">Enhanced 9-1-1 (E9-1-1) calls and location Profile (plan de numérotation)</span><span class="sxs-lookup"><span data-stu-id="9daf2-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9daf2-115">La</span><span class="sxs-lookup"><span data-stu-id="9daf2-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="9daf2-116">Affichage de plusieurs flux à partir d’une conférence</span><span class="sxs-lookup"><span data-stu-id="9daf2-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9daf2-117">L’outil de contrainte et de performances de Lync Server 2013 prend en charge la génération de charge et la Fédération entre les pools via une configuration avancée uniquement.</span><span class="sxs-lookup"><span data-stu-id="9daf2-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="9daf2-118">L’outil ne simule pas non plus la charge utilisateur pour les clients suivants :</span><span class="sxs-lookup"><span data-stu-id="9daf2-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="9daf2-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="9daf2-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="9daf2-120">Lync 2013 conversation permanente</span><span class="sxs-lookup"><span data-stu-id="9daf2-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="9daf2-121">Par conséquent, l’outil de contrainte et de performances de Lync Server 2013 ne prend pas en charge le test des composants suivants :</span><span class="sxs-lookup"><span data-stu-id="9daf2-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="9daf2-122">Lync 2013 conversation permanente</span><span class="sxs-lookup"><span data-stu-id="9daf2-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="9daf2-123">Scénarios d’intégration Exchange</span><span class="sxs-lookup"><span data-stu-id="9daf2-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="9daf2-124">Applications et fichiers inclus avec l’outil de contrainte et de performances de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9daf2-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="9daf2-125">Les applications suivantes sont incluses dans l’outil de contrainte et de performances de Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="9daf2-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9daf2-126">Outil</span><span class="sxs-lookup"><span data-stu-id="9daf2-126">Tool</span></span></th>
<th><span data-ttu-id="9daf2-127">Description</span><span class="sxs-lookup"><span data-stu-id="9daf2-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9daf2-128">UserProvisioningTool. exe</span><span class="sxs-lookup"><span data-stu-id="9daf2-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="9daf2-129">Outil de mise en service utilisateur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9daf2-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="9daf2-130">Cet outil permet de créer des utilisateurs et des contacts.</span><span class="sxs-lookup"><span data-stu-id="9daf2-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9daf2-131">UserProfileGenerator. exe</span><span class="sxs-lookup"><span data-stu-id="9daf2-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="9daf2-132">L’outil de configuration de chargement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9daf2-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="9daf2-133">Cet outil permet de configurer les caractéristiques de la charge utilisateur à simuler.</span><span class="sxs-lookup"><span data-stu-id="9daf2-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9daf2-134">LyncPerfTool. exe</span><span class="sxs-lookup"><span data-stu-id="9daf2-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="9daf2-135">L’outil de contrainte et de performances de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9daf2-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="9daf2-136">LyncPerfTool est l’outil qui simule la charge utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9daf2-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9daf2-137">Default. TMX</span><span class="sxs-lookup"><span data-stu-id="9daf2-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="9daf2-138">Default. TMX est requis pour utiliser l’outil de journalisation Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9daf2-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9daf2-139">Exemple de scripts de mise en service</span><span class="sxs-lookup"><span data-stu-id="9daf2-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="9daf2-140">Ces exemples permettent de configurer la topologie pour exécuter des tests de charge, en fonction de scénarios spécifiques.</span><span class="sxs-lookup"><span data-stu-id="9daf2-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

