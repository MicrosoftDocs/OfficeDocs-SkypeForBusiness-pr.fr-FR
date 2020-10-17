---
title: 'Lync Server 2013 : configuration de la stratégie de conférence pour les appels entrants'
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
ms.openlocfilehash: 3c42084f2e5ed8acceb73b4f417d8205b78b4b56
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515711"
---
# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="75025-102">Configurer la stratégie de conférence pour les appels entrants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75025-102">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75025-103">_**Dernière modification de la rubrique :** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="75025-103">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="75025-p101">Une stratégie de conférence est un paramètre de compte d’utilisateur qui spécifie les modalités de la conférence pour les participants. Vous pouvez créer des stratégies de conférence avec une étendue de site ou d’utilisateur. Les paramètres de stratégie de conférence englobent de nombreux aspects de la planification de la conférence et de la participation. Plusieurs paramètres de stratégies de conférence prennent en charge la conférence rendez-vous pour les participants. Lorsque vous configurez une conférence rendez-vous, vous devez vérifier que ces champs sont correctement définis pour votre organisation, et vous devez les modifier uniquement en cas de nécessité.</span><span class="sxs-lookup"><span data-stu-id="75025-p101">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="75025-109">Vérifiez les champs suivants dans votre stratégie de conférence :</span><span class="sxs-lookup"><span data-stu-id="75025-109">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="75025-110">**Autoriser les participants à inviter des utilisateurs**     anonymes Ce paramètre permet aux organisateurs de réunions d’inviter des participants anonymes (c’est-à-dire, non authentifiés) à des réunions.</span><span class="sxs-lookup"><span data-stu-id="75025-110">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="75025-111">Ce paramètre est facultatif pour la conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="75025-111">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="75025-112">Il est sélectionné par défaut dans la stratégie de conférence globale par défaut.</span><span class="sxs-lookup"><span data-stu-id="75025-112">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="75025-113">**Activer la Conférence**     rendez-vous PSTN Ce paramètre permet aux utilisateurs de participer à la partie audio d’une conférence en appelant le réseau RTC.</span><span class="sxs-lookup"><span data-stu-id="75025-113">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="75025-114">Ce paramètre est obligatoire pour la conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="75025-114">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="75025-115">Il est sélectionné par défaut dans la stratégie de conférence globale par défaut.</span><span class="sxs-lookup"><span data-stu-id="75025-115">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="75025-116">**Autoriser les participants anonymes à effectuer des appels sortants**     Ce paramètre permet aux utilisateurs anonymes qui sont déjà joints à la réunion d’appeler un numéro de téléphone pour rejoindre la partie audio de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="75025-116">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="75025-117">Ce paramètre est facultatif pour la conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="75025-117">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="75025-118">Il n’est pas sélectionné par défaut dans la stratégie de conférence globale par défaut.</span><span class="sxs-lookup"><span data-stu-id="75025-118">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="75025-119">**Autoriser les participants non activés pour voix entreprise à numéroter**     Ce paramètre permet aux participants à la réunion et aux organisateurs qui ne sont pas activés pour que voix entreprise appelle un numéro de téléphone pour participer à la partie audio de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="75025-119">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="75025-120">Celui-ci est autorisé en fonction de la stratégie de voix assignée de l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="75025-120">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="75025-121">Il n’est pas sélectionné par défaut dans la stratégie de conférence globale par défaut.</span><span class="sxs-lookup"><span data-stu-id="75025-121">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="75025-122">Sa valeur par défaut est désactivée.</span><span class="sxs-lookup"><span data-stu-id="75025-122">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75025-123">Pour activer cette fonctionnalité, l’organisateur de la réunion qui n’est pas activé pour Enterprise Voice doit disposer d’une stratégie de voix appropriée qui leur est attribuée pour autoriser des appels sortants à partir d’une conférence organisée par cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="75025-123">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="75025-124">Une stratégie de voix peut être affectée à un utilisateur qui n’est pas activé pour voix entreprise à partir de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="75025-124">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="75025-125">Si aucune stratégie de voix n’a été attribuée à l’utilisateur, la stratégie de voix du site est utilisée pour autoriser la demande d’appel sortant.</span><span class="sxs-lookup"><span data-stu-id="75025-125">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="75025-126">S’il n’existe aucune stratégie de voix de site, la stratégie de voix globale est utilisée.&nbsp;</span><span class="sxs-lookup"><span data-stu-id="75025-126">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="75025-127">La procédure de cette section explique comment modifier la stratégie de conférence.</span><span class="sxs-lookup"><span data-stu-id="75025-127">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="75025-128">Pour plus d’informations sur la configuration de tous les paramètres qui définissent l’expérience des participants dans la stratégie de conférence par défaut, voir [Create or Modify a collection of meeting Configuration Settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="75025-128">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="75025-129">Pour plus d’informations sur la création d’une stratégie de conférence pour un utilisateur ou un groupe d’utilisateurs spécifique, voir [Create or Modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="75025-129">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="75025-130">Pour obtenir la liste de tous les paramètres de stratégie de conférence disponibles, consultez la rubrique [référence des paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="75025-130">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="75025-131">Pour modifier la stratégie de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="75025-131">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="75025-132">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle **Cs-ServerAdministratorr** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="75025-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="75025-133">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75025-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="75025-134">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="75025-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="75025-135">Dans la barre de navigation de gauche, cliquez sur **Conférence**.</span><span class="sxs-lookup"><span data-stu-id="75025-135">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="75025-136">Sous l’onglet **Stratégie de conférence**, double-cliquez sur un nom de stratégie de conférence pour ouvrir la boîte de dialogue **Modifier la stratégie de conférence**.</span><span class="sxs-lookup"><span data-stu-id="75025-136">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="75025-137">Vérifiez que les champs de la conférence rendez-vous correspondent à votre organisation et modifiez les paramètres, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="75025-137">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="75025-138">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="75025-138">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

