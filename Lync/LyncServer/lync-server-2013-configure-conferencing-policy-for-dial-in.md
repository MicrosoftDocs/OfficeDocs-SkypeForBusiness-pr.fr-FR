---
title: 'Lync Server 2013 : Configuration de la stratégie de conférence rendez-vous'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 107c5fcf4b341c652cd4044fe47f4b650cf5adb4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="4b9d6-102">Configuration de la stratégie de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b9d6-102">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b9d6-103">_**Dernière modification de la rubrique :** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="4b9d6-103">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="4b9d6-p101">Une stratégie de conférence est un paramètre de compte d’utilisateur qui spécifie les modalités de la conférence pour les participants. Vous pouvez créer des stratégies de conférence avec une étendue de site ou d’utilisateur. Les paramètres de stratégie de conférence englobent de nombreux aspects de la planification de la conférence et de la participation. Plusieurs paramètres de stratégies de conférence prennent en charge la conférence rendez-vous pour les participants. Lorsque vous configurez une conférence rendez-vous, vous devez vérifier que ces champs sont correctement définis pour votre organisation, et vous devez les modifier uniquement en cas de nécessité.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-p101">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="4b9d6-109">Vérifiez les champs suivants dans votre stratégie de conférence :</span><span class="sxs-lookup"><span data-stu-id="4b9d6-109">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="4b9d6-110">**Permettre aux participants d’inviter des utilisateurs**   anonymes ce paramètre permet aux organisateurs de la réunion d’inviter des participants anonymes (non authentifiés) aux réunions.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-110">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="4b9d6-111">Ce paramètre est facultatif pour les conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-111">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="4b9d6-112">Ce paramètre est sélectionné par défaut dans la stratégie de conférence globale par défaut.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-112">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="4b9d6-113">**Activer les conférences**   rendez-vous RTC ce paramètre permet aux utilisateurs d’accéder à la partie audio d’une conférence en composant un numéro de téléphone PSTN.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-113">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="4b9d6-114">Ce paramètre est requis pour les conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-114">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="4b9d6-115">Ce paramètre est sélectionné par défaut dans la stratégie de conférence globale par défaut.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-115">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="4b9d6-116">**Permettre aux participants anonymes d’appeler**   ce paramètre permet aux utilisateurs anonymes déjà joints à la réunion d’appeler un numéro de téléphone pour se connecter à la partie audio de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-116">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="4b9d6-117">Ce paramètre est facultatif pour les conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-117">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="4b9d6-118">Ce paramètre n’est pas sélectionné par défaut dans la stratégie de conférence globale par défaut.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-118">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="4b9d6-119">**Permettre aux participants non activés pour les appels vocaux d’entreprise de composer**   ce paramètre permet aux participants et aux organisateurs d’une réunion qui ne sont pas activés pour les appels sortants dans un numéro de téléphone pour accéder à la partie audio de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-119">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="4b9d6-120">Le numéro de téléphone est autorisé en fonction de la politique vocale affectée à l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-120">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="4b9d6-121">Ce paramètre n’est pas sélectionné par défaut dans la stratégie de conférence globale par défaut.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-121">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="4b9d6-122">La valeur par défaut du paramètre est Disabled.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-122">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b9d6-123">Pour activer cette fonctionnalité, un organisateur de la réunion qui n’est pas activé pour voix entreprise doit avoir reçu une stratégie vocale appropriée pour autoriser les appels sortants d’une conférence organisée par cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-123">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="4b9d6-124">Une stratégie vocale peut être affectée à un utilisateur qui n’est pas activé pour voix entreprise via Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-124">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="4b9d6-125">Si une stratégie vocale n’est pas explicitement attribuée à l’utilisateur, la stratégie de voix du site est utilisée pour autoriser la demande de numérotation.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-125">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="4b9d6-126">S’il n’y a aucune stratégie de voix du site, la stratégie vocale globale est utilisée.&nbsp;</span><span class="sxs-lookup"><span data-stu-id="4b9d6-126">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="4b9d6-127">La procédure décrite dans cette section explique comment modifier une stratégie de conférence.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-127">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="4b9d6-128">Pour plus d’informations sur la configuration de tous les paramètres définissant l’utilisation des participants dans la stratégie de conférence par défaut, voir [créer ou modifier un ensemble de paramètres de configuration de réunion dans Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4b9d6-128">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="4b9d6-129">Pour plus d’informations sur la création d’une stratégie de conférence pour un utilisateur ou un groupe d’utilisateurs spécifiques, voir [créer ou modifier une stratégie de conférence dans Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="4b9d6-129">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="4b9d6-130">Pour obtenir la liste de tous les paramètres de stratégie de conférence disponibles, voir [référence des paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="4b9d6-130">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="4b9d6-131">Pour modifier la stratégie de conférence pour les appels entrants</span><span class="sxs-lookup"><span data-stu-id="4b9d6-131">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="4b9d6-132">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle **CS-ServerAdministrator** ou **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="4b9d6-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="4b9d6-133">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4b9d6-134">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4b9d6-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4b9d6-135">Dans la barre de navigation de gauche, cliquez sur **Conférences**.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-135">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="4b9d6-136">Dans l’onglet **stratégie de conférence** , double-cliquez sur un nom de stratégie de conférence pour ouvrir la boîte de dialogue Modifier la stratégie de **Conférence** .</span><span class="sxs-lookup"><span data-stu-id="4b9d6-136">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="4b9d6-137">Vérifiez que les champs de la Conférence rendez-vous sont appropriés pour votre organisation, puis modifiez les paramètres le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-137">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="4b9d6-138">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="4b9d6-138">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

