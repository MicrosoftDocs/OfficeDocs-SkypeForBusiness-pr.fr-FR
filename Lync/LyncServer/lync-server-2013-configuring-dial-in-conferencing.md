---
title: 'Lync Server 2013 : configuration de la Conférence rendez-vous'
description: 'Lync Server 2013 : configuration de la Conférence rendez-vous.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring dial-in conferencing
ms:assetid: 79a98c5d-a0a8-4729-828d-b9166842432c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398600(v=OCS.15)
ms:contentKeyID: 48184587
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9c3353caa1344b717b0f64c271149f078f194e5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557940"
---
# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="66f67-103">Configuration de la Conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f67-103">Configuring dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66f67-104">_**Dernière modification de la rubrique :** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="66f67-104">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="66f67-105">Cette section vous guide tout au long de la configuration de la Conférence rendez-vous Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66f67-105">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="66f67-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="66f67-106">In This Section</span></span>

  - [<span data-ttu-id="66f67-107">Conditions préalables et autorisations pour la configuration de la Conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f67-107">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="66f67-108">Liste de vérification du déploiement pour les conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f67-108">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="66f67-109">Configurer des plans de numérotation pour les conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f67-109">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="66f67-110">Vérifier que les plans de numérotation Lync Server 2013 ont des régions affectées</span><span class="sxs-lookup"><span data-stu-id="66f67-110">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="66f67-111">Module Vérifier les paramètres de stratégie de code confidentiel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f67-111">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="66f67-112">Configurer la stratégie de conférence pour les appels entrants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f67-112">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="66f67-113">Configurer les numéros d’accès aux conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f67-113">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="66f67-114">Module Vérifier les paramètres de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f67-114">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="66f67-115">Module Modifier le mappage des clés pour les commandes DTMF dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f67-115">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="66f67-116">Module Activer et désactiver les annonces de participation et de sortie de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f67-116">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="66f67-117">Module Vérifier les conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f67-117">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="66f67-118">Déploiement du complément de réunion en ligne pour Lync 2013</span><span class="sxs-lookup"><span data-stu-id="66f67-118">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="66f67-119">Configurer les paramètres de compte d’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f67-119">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="66f67-120">Recommandation Créer des annuaires de conférences</span><span class="sxs-lookup"><span data-stu-id="66f67-120">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="66f67-121">Module Bienvenue les utilisateurs à la Conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f67-121">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="66f67-122">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="66f67-122">Related Sections</span></span>

[<span data-ttu-id="66f67-123">Déploiement de Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66f67-123">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

