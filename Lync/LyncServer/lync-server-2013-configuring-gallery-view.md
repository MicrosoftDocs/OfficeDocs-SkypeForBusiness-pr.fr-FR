---
title: 'Lync Server 2013 : configuration de la vue de la Galerie'
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
ms.openlocfilehash: 096272a2347c400a81e6d4684873c5f5828136a5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="250a2-102">Configuration de la vue de la galerie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="250a2-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="250a2-103">_**Dernière modification de la rubrique :** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="250a2-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="250a2-104">Dans Lync Server 2013, vous configurez la vidéoconférence d’affichage de galerie dans la stratégie de conférence.</span><span class="sxs-lookup"><span data-stu-id="250a2-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="250a2-105">La vue Galerie est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="250a2-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="250a2-106">Si vous ne souhaitez pas autoriser la vue Galerie ou si vous voulez l’autoriser pour certains utilisateurs seulement, vous devez désactiver la fonctionnalité dans la stratégie de conférence.</span><span class="sxs-lookup"><span data-stu-id="250a2-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="250a2-107">Lorsque la vidéo d’un participant à la Conférence n’est pas disponible, l’expérience de visualisation de la Galerie des utilisateurs peut être améliorée si vous déployez des photos haute résolution, une nouvelle fonctionnalité de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="250a2-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="250a2-108">Les photos haute résolution offrent une alternative aux petites photos de contact de résolution limitée stockées dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="250a2-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="250a2-109">Les photos haute résolution sont stockées dans la boîte aux lettres Exchange 2013 d’un utilisateur et, par conséquent, vous devez intégrer Lync Server 2013 à Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="250a2-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="250a2-110">Pour plus d’informations, reportez-vous à l’article du blog NextHop, « intégration d' [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987)Exchange 2013 et de Lync Server 2013 », à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="250a2-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="250a2-111">Le contenu de chaque blog et les URL correspondantes peuvent faire l'objet de modifications sans préavis.</span><span class="sxs-lookup"><span data-stu-id="250a2-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="250a2-112">Vous pouvez afficher ou modifier les paramètres d’affichage de la galerie à l’aide du panneau de configuration Lync Server 2013 ou de l’une des applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="250a2-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="250a2-113">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="250a2-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="250a2-114">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="250a2-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="250a2-115">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="250a2-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="250a2-116">Configurez la vue Galerie à l’aide des paramètres de stratégie de conférence suivants :</span><span class="sxs-lookup"><span data-stu-id="250a2-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="250a2-117">**AllowMultiview**   ce paramètre détermine si un utilisateur est autorisé à organiser les conférences vidéo de la Galerie.</span><span class="sxs-lookup"><span data-stu-id="250a2-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="250a2-118">Ce paramètre s’applique aux réunions planifiées et ad hoc créées par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="250a2-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="250a2-119">Exemples :</span><span class="sxs-lookup"><span data-stu-id="250a2-119">Examples:</span></span>
    
      - <span data-ttu-id="250a2-120">Ce paramètre est défini sur true pour l’utilisateur A, qui est hébergé sur un pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="250a2-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="250a2-121">Les réunions organisées par l’utilisateur A permettent aux utilisateurs d’envoyer et de recevoir plusieurs flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="250a2-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="250a2-122">Ce paramètre est défini sur false pour l’utilisateur B, qui est hébergé sur un pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="250a2-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="250a2-123">Les réunions organisées par l’utilisateur B ont un flux vidéo unique semblable à l’expérience de vidéoconférence fournie par Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="250a2-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="250a2-p106">Ce paramètre détermine quelles sont les personnes qui peuvent organiser des réunions autorisant plusieurs flux vidéo. Les participants aux réunions qui autorisent plusieurs flux vidéo peuvent être autorisés ou non à recevoir plusieurs flux vidéo, en fonction de leurs autorisations individuelles (voir la description du paramètre EnableMultiviewJoin).</span><span class="sxs-lookup"><span data-stu-id="250a2-p106">This parameter determines who can organize meetings that allow multiple video streams. Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="250a2-126">**EnableMultiviewJoin**   ce paramètre contrôle si un participant à une réunion reçoit l’expérience vidéo en mode Galerie dans les réunions qui l’autorisent.</span><span class="sxs-lookup"><span data-stu-id="250a2-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="250a2-127">Ce paramètre contrôle l’expérience de l’utilisateur dans les réunions auxquelles il participe.</span><span class="sxs-lookup"><span data-stu-id="250a2-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="250a2-128">Exemples :</span><span class="sxs-lookup"><span data-stu-id="250a2-128">Examples:</span></span>
    
      - <span data-ttu-id="250a2-129">Ce paramètre est défini sur true pour l’utilisateur C. l’utilisateur C peut recevoir plusieurs flux vidéo lorsqu’il participe à une réunion organisée ou démarrée par l’utilisateur A. l’utilisateur C reçoit un seul flux vidéo semblable à l’expérience de vidéoconférence fournie par Lync Server 2010. participation à une réunion organisée ou démarrée par l’utilisateur B.</span><span class="sxs-lookup"><span data-stu-id="250a2-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="250a2-130">Ce paramètre est défini sur false pour l’utilisateur D. User D reçoit un flux vidéo unique semblable à l’expérience de vidéoconférence fournie par Lync Server 2010 lorsqu’il participe à une réunion organisée par l’utilisateur A ou l’utilisateur B.</span><span class="sxs-lookup"><span data-stu-id="250a2-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="250a2-131">La procédure suivante est un exemple d’utilisation de Lync Server Management Shell pour activer la conférence vidéo sur les vues de la Galerie.</span><span class="sxs-lookup"><span data-stu-id="250a2-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="250a2-132">Pour modifier la stratégie de conférence de la visioconférence dans la vue Galerie</span><span class="sxs-lookup"><span data-stu-id="250a2-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="250a2-133">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="250a2-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="250a2-134">À partir de la ligne de commande, exécutez l’applet de commande suivante pour modifier la stratégie de conférence :</span><span class="sxs-lookup"><span data-stu-id="250a2-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

