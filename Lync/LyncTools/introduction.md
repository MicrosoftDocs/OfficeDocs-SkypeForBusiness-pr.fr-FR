---
title: Introduction
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d496d0aeaabd8ef7502cae8db89f2668d0574499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a><span data-ttu-id="344fc-102">Introduction</span><span class="sxs-lookup"><span data-stu-id="344fc-102">Introduction</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="344fc-103">_**Dernière modification de la rubrique:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="344fc-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="344fc-104">L’outil de stress et de performance de Lync Server 2013 (appelé LyncPerfTool) peut simuler la charge utilisateur des types suivants:</span><span class="sxs-lookup"><span data-stu-id="344fc-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="344fc-105">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="344fc-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="344fc-106">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="344fc-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="344fc-107">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="344fc-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="344fc-108">Voix sur IP (VoIP), y compris la simulation de réseau téléphonique commuté (PSTN)</span><span class="sxs-lookup"><span data-stu-id="344fc-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="344fc-109">Conférences de clients d’accès Web</span><span class="sxs-lookup"><span data-stu-id="344fc-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="344fc-110">Microsoft Lync 2013 attendant</span><span class="sxs-lookup"><span data-stu-id="344fc-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="344fc-111">Response Groups</span><span class="sxs-lookup"><span data-stu-id="344fc-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="344fc-112">Extension de liste de distribution</span><span class="sxs-lookup"><span data-stu-id="344fc-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="344fc-113">Requête de téléchargement du carnet d’adresses et du carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="344fc-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="344fc-114">9-1-1 d’amélioration (E9-1-1): profil d’emplacement et d’emplacement (plan de numérotation)</span><span class="sxs-lookup"><span data-stu-id="344fc-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="344fc-115">Multivue</span><span class="sxs-lookup"><span data-stu-id="344fc-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="344fc-116">Affichage de plusieurs flux d’une conférence</span><span class="sxs-lookup"><span data-stu-id="344fc-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="344fc-117">L’outil de stress et de performance de Lync Server 2013 prend en charge la génération et la Fédération par pool via la configuration avancée uniquement.</span><span class="sxs-lookup"><span data-stu-id="344fc-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="344fc-118">L’outil ne simule pas non plus la charge des utilisateurs pour les clients suivants:</span><span class="sxs-lookup"><span data-stu-id="344fc-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="344fc-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="344fc-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="344fc-120">Conversation permanente Lync 2013</span><span class="sxs-lookup"><span data-stu-id="344fc-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="344fc-121">Par conséquent, l’outil de stress et de performance de Lync Server 2013 ne prend pas en charge le test des composants suivants:</span><span class="sxs-lookup"><span data-stu-id="344fc-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="344fc-122">Conversation permanente Lync 2013</span><span class="sxs-lookup"><span data-stu-id="344fc-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="344fc-123">Scénarios d’intégration Exchange</span><span class="sxs-lookup"><span data-stu-id="344fc-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="344fc-124">Applications et fichiers inclus dans l’outil de stress et de performance de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="344fc-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="344fc-125">Les applications suivantes sont incluses dans l’outil de stress et de performance de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="344fc-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="344fc-126">Il</span><span class="sxs-lookup"><span data-stu-id="344fc-126">Tool</span></span></th>
<th><span data-ttu-id="344fc-127">Description</span><span class="sxs-lookup"><span data-stu-id="344fc-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="344fc-128">UserProvisioningTool. exe</span><span class="sxs-lookup"><span data-stu-id="344fc-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="344fc-129">Outil de mise en service des utilisateurs de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="344fc-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="344fc-130">Cet outil permet de créer des utilisateurs et des contacts.</span><span class="sxs-lookup"><span data-stu-id="344fc-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="344fc-131">UserProfileGenerator. exe</span><span class="sxs-lookup"><span data-stu-id="344fc-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="344fc-132">Outil de configuration de chargement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="344fc-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="344fc-133">Cet outil permet de configurer les caractéristiques de la charge d’utilisateur pour la simulation.</span><span class="sxs-lookup"><span data-stu-id="344fc-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="344fc-134">LyncPerfTool. exe</span><span class="sxs-lookup"><span data-stu-id="344fc-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="344fc-135">Outil de stress et de performance de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="344fc-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="344fc-136">LyncPerfTool est l’outil qui simule la charge utilisateur.</span><span class="sxs-lookup"><span data-stu-id="344fc-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="344fc-137">Default. TMX</span><span class="sxs-lookup"><span data-stu-id="344fc-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="344fc-138">Default. TMX est requis pour l’utilisation de l’outil de journalisation Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="344fc-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="344fc-139">Exemples de scripts de mise en service</span><span class="sxs-lookup"><span data-stu-id="344fc-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="344fc-140">Ces exemples sont utilisés pour configurer la topologie pour exécuter des tests de charge, en fonction de scénarios spécifiques.</span><span class="sxs-lookup"><span data-stu-id="344fc-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

