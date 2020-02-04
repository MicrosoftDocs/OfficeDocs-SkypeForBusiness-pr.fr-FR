---
title: 'Lync Server 2013 : Configuration de conférences rendez-vous'
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
ms.openlocfilehash: d722abaf76ef915b7587039cb7732cb281a06308
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="7665e-102">Configuration de conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7665e-102">Configuring dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7665e-103">_**Dernière modification de la rubrique :** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="7665e-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="7665e-104">Cette section vous guide dans la configuration de la Conférence rendez-vous Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7665e-104">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7665e-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="7665e-105">In This Section</span></span>

  - [<span data-ttu-id="7665e-106">Configuration requise et autorisations pour la configuration de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7665e-106">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="7665e-107">Liste de vérification du déploiement pour la conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7665e-107">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="7665e-108">Configuration des plans de numérotation pour les conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7665e-108">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="7665e-109">Vérifier que le plan de numérotation Lync Server 2013 a des régions affectées</span><span class="sxs-lookup"><span data-stu-id="7665e-109">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="7665e-110">(Facultatif) Vérification des paramètres de stratégie de code confidentiel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7665e-110">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="7665e-111">Configuration de la stratégie de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7665e-111">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="7665e-112">Configuration des numéros d’accès aux conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7665e-112">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="7665e-113">(Facultatif) Vérification des paramètres de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7665e-113">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="7665e-114">(Facultatif) Modification du mappage des clés des commandes DTMF dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7665e-114">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="7665e-115">(Facultatif) Activation et désactivation des annonces indiquant qu’un utilisateur rejoint ou quitte une conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7665e-115">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="7665e-116">(Facultatif) Vérification de la conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7665e-116">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="7665e-117">Déploiement du complément de réunion en ligne pour Lync 2013</span><span class="sxs-lookup"><span data-stu-id="7665e-117">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="7665e-118">Configuration des paramètres des comptes d’utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7665e-118">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="7665e-119">(Recommended) Create Conference Directories</span><span class="sxs-lookup"><span data-stu-id="7665e-119">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="7665e-120">(Facultatif) Accueil des utilisateurs dans les conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7665e-120">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="7665e-121">Sections associées</span><span class="sxs-lookup"><span data-stu-id="7665e-121">Related Sections</span></span>

[<span data-ttu-id="7665e-122">Déploiement de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7665e-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

