---
title: 'Lync Server 2013 : configuration de l’affichage Galerie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06054e1728245c87e8bf35419d3890f4e379543a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="937a7-102">Configurer le mode Galerie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="937a7-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="937a7-103">_**Dernière modification de la rubrique :** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="937a7-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="937a7-104">Dans Lync Server 2013, vous configurez la conférence vidéo d’affichage de la galerie dans la stratégie de conférence.</span><span class="sxs-lookup"><span data-stu-id="937a7-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="937a7-105">L’option vue Galerie est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="937a7-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="937a7-106">Si vous ne voulez pas autoriser le mode Galerie, ou si vous voulez l’autoriser pour certains utilisateurs, vous devez désactiver la fonctionnalité dans la stratégie de conférence.</span><span class="sxs-lookup"><span data-stu-id="937a7-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="937a7-107">Lorsque la vidéo d’un participant à la Conférence n’est pas disponible, il est possible d’améliorer l’affichage de la Galerie de la Galerie des utilisateurs si vous déployez des photos haute résolution, une nouvelle fonctionnalité dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="937a7-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="937a7-108">Les photos haute résolution constituent une alternative aux photos de contact plus petites et limitées stockées dans les services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="937a7-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="937a7-109">Les photos haute résolution sont stockées dans la boîte aux lettres Exchange 2013 d’un utilisateur et nécessitent donc l’intégration de Lync Server 2013 avec Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="937a7-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="937a7-110">Pour plus d’informations, consultez l’article de blog NextHop intitulé « intégration d’Exchange 2013 et Lync Server [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987)2013 ».</span><span class="sxs-lookup"><span data-stu-id="937a7-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="937a7-111">Le contenu des blogs et leurs URL peuvent être modifiés sans préavis.</span><span class="sxs-lookup"><span data-stu-id="937a7-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="937a7-112">Vous pouvez afficher ou modifier les paramètres d’affichage de la galerie en utilisant le panneau de configuration de Lync Server 2013 ou en utilisant l’une des applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="937a7-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="937a7-113">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="937a7-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="937a7-114">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="937a7-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="937a7-115">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="937a7-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="937a7-116">Configurer le mode Galerie avec les paramètres de stratégie de conférence suivants :</span><span class="sxs-lookup"><span data-stu-id="937a7-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="937a7-117">**AllowMultiview**   ce paramètre détermine si un utilisateur est autorisé à organiser des conférences vidéo d’affichage Galerie.</span><span class="sxs-lookup"><span data-stu-id="937a7-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="937a7-118">Ce paramètre s’applique aux réunions planifiées et ponctuelles créées par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="937a7-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="937a7-119">Donnés</span><span class="sxs-lookup"><span data-stu-id="937a7-119">Examples:</span></span>
    
      - <span data-ttu-id="937a7-120">Ce paramètre est défini sur true pour l’utilisateur A qui est hébergé sur un pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="937a7-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="937a7-121">Réunions organisées par l’utilisateur permet aux utilisateurs de joindre et de recevoir plusieurs flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="937a7-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="937a7-122">Ce paramètre est défini sur false pour l’utilisateur B, qui est hébergé sur un pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="937a7-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="937a7-123">Les réunions organisées par l’utilisateur B sont dotées d’un flux vidéo unique qui est semblable à l’interface de visioconférence fournie par Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="937a7-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="937a7-124">Ce paramètre détermine qui peut organiser des réunions qui autorisent plusieurs flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="937a7-124">This parameter determines who can organize meetings that allow multiple video streams.</span></span> <span data-ttu-id="937a7-125">Les participants à des réunions qui autorisent plusieurs flux vidéo peuvent, ou ne peuvent pas être autorisés à recevoir plusieurs flux vidéo, en fonction de leurs autorisations individuelles (voir la description du paramètre EnableMultiviewJoin).</span><span class="sxs-lookup"><span data-stu-id="937a7-125">Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="937a7-126">**EnableMultiviewJoin**   ce paramètre détermine si un participant à une réunion reçoit l’interface vidéo d’affichage de la galerie dans les réunions qui le permettent.</span><span class="sxs-lookup"><span data-stu-id="937a7-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="937a7-127">Ce paramètre contrôle l’utilisation de l’utilisateur dans les réunions auxquelles il participe.</span><span class="sxs-lookup"><span data-stu-id="937a7-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="937a7-128">Donnés</span><span class="sxs-lookup"><span data-stu-id="937a7-128">Examples:</span></span>
    
      - <span data-ttu-id="937a7-129">Ce paramètre est défini sur true pour l’utilisateur C. l’utilisateur c peut recevoir plusieurs flux vidéo lorsque vous participez à une réunion organisée ou démarrée par l’utilisateur A. l’utilisateur dispose d’un flux vidéo unique similaire à l’interface de visioconférence fournie par Lync Server 2010. participation à une réunion organisée ou démarrée par l’utilisateur B.</span><span class="sxs-lookup"><span data-stu-id="937a7-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="937a7-130">Ce paramètre est défini sur false pour l’utilisateur D. User d reçoit un flux vidéo unique qui est semblable à l’interface de visioconférence fournie par Lync Server 2010 lors de la participation à une réunion organisée par l’utilisateur A ou par l’utilisateur B.</span><span class="sxs-lookup"><span data-stu-id="937a7-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="937a7-131">Vous trouverez ci-dessous un exemple d’utilisation de Lync Server Management Shell pour activer la vidéoconférence d’affichage Galerie.</span><span class="sxs-lookup"><span data-stu-id="937a7-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="937a7-132">Pour modifier la stratégie de conférence pour les conférences vidéo sur l’affichage Galerie</span><span class="sxs-lookup"><span data-stu-id="937a7-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="937a7-133">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="937a7-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="937a7-134">Dans la ligne de commande, exécutez l’applet de commande suivante pour modifier la stratégie de conférence :</span><span class="sxs-lookup"><span data-stu-id="937a7-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

