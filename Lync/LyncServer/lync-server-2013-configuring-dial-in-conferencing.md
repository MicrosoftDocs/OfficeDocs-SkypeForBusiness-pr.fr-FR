---
title: 'Lync Server 2013 : Configuration de conférences rendez-vous'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring dial-in conferencing
ms:assetid: 79a98c5d-a0a8-4729-828d-b9166842432c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398600(v=OCS.15)
ms:contentKeyID: 48184587
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ca8b82fe77e578f1ac513d00583c42dd56162a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="eae70-102">Configuration de conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae70-102">Configuring dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eae70-103">_**Dernière modification de la rubrique:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="eae70-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="eae70-104">Cette section vous guide dans la configuration de la Conférence rendez-vous Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eae70-104">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eae70-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="eae70-105">In This Section</span></span>

  - [<span data-ttu-id="eae70-106">Configuration requise et autorisations pour la configuration de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae70-106">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="eae70-107">Liste de vérification du déploiement pour la conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae70-107">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="eae70-108">Configuration des plans de numérotation pour les conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae70-108">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="eae70-109">Vérifier que le plan de numérotation Lync Server 2013 a des régions affectées</span><span class="sxs-lookup"><span data-stu-id="eae70-109">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="eae70-110">(Facultatif) Vérification des paramètres de stratégie de code confidentiel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae70-110">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="eae70-111">Configuration de la stratégie de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae70-111">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="eae70-112">Configuration des numéros d’accès aux conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae70-112">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="eae70-113">(Facultatif) Vérification des paramètres de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae70-113">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="eae70-114">(Facultatif) Modification du mappage des clés des commandes DTMF dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae70-114">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="eae70-115">(Facultatif) Activation et désactivation des annonces indiquant qu’un utilisateur rejoint ou quitte une conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae70-115">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="eae70-116">(Facultatif) Vérification de la conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae70-116">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="eae70-117">Déploiement du complément de réunion en ligne pour Lync 2013</span><span class="sxs-lookup"><span data-stu-id="eae70-117">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="eae70-118">Configuration des paramètres des comptes d’utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae70-118">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="eae70-119">(Recommended) Create Conference Directories</span><span class="sxs-lookup"><span data-stu-id="eae70-119">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="eae70-120">(Facultatif) Accueil des utilisateurs dans les conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae70-120">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="eae70-121">Sections associées</span><span class="sxs-lookup"><span data-stu-id="eae70-121">Related Sections</span></span>

[<span data-ttu-id="eae70-122">Déploiement de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae70-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

