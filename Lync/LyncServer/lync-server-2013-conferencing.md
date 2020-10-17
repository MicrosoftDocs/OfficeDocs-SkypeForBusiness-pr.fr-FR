---
title: Conférence Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecfca21d1cd7151cb48db8a165dbea00acdae560
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507821"
---
# <a name="conferencing-in-lync-server-2013"></a><span data-ttu-id="52978-102">Conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52978-102">Conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52978-103">_**Dernière modification de la rubrique :** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="52978-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="52978-104">Avec la Conférence unifiée dans Lync Server 2013, les utilisateurs peuvent collaborer, partager des informations et coordonner leurs efforts en temps réel.</span><span class="sxs-lookup"><span data-stu-id="52978-104">With unified conferencing in Lync Server 2013, users can collaborate, share information, and coordinate their efforts in real time.</span></span> <span data-ttu-id="52978-105">Tous vos utilisateurs peuvent recourir à l’ensemble des outils de réunion planifiée et de collaboration spontanée.</span><span class="sxs-lookup"><span data-stu-id="52978-105">All your users can use the full breadth of spontaneous collaboration, scheduled meetings, and meeting tools.</span></span> <span data-ttu-id="52978-106">Les fonctionnalités de conférence audio et vidéo peuvent être utilisées depuis n’importe quel emplacement offrant une connexion à Internet, et les utilisateurs n’ayant pas d’ordinateur à leur disposition peuvent participer aux conférences audio en se connectant via un téléphone PSTN (réseau téléphonique commuté).</span><span class="sxs-lookup"><span data-stu-id="52978-106">Voice and video conferencing capabilities can be used from any location with an Internet connection, and users away from a computer can participate in audio conferences by dialing in with a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="52978-107">Les outils de réunion intégrés dans Outlook permettent aux organisateurs de planifier une réunion ou de démarrer une conférence impromptue d’un simple clic, et de faciliter la participation des participants.</span><span class="sxs-lookup"><span data-stu-id="52978-107">Meeting tools integrated into Outlook enable organizers to schedule a meeting or start an impromptu conference with a single click, and also make it just as easy for attendees to join.</span></span> <span data-ttu-id="52978-108">Un client Web étend les fonctionnalités de conférence enrichie aux participants qui n’exécutent pas la version de bureau de Lync.</span><span class="sxs-lookup"><span data-stu-id="52978-108">A web client extends rich conference features to participants who are not running the desktop version of Lync.</span></span>

<div>

## <a name="audio-and-video-conferencing"></a><span data-ttu-id="52978-109">Conférence audio et vidéo</span><span class="sxs-lookup"><span data-stu-id="52978-109">Audio and Video Conferencing</span></span>

<span data-ttu-id="52978-110">Lync Server offre une expérience utilisateur familière aux utilisateurs de services ponts audio traditionnels, y compris les services RTC Dial-in, avec des commandes de contrôle d’appel à fréquences vocales.</span><span class="sxs-lookup"><span data-stu-id="52978-110">Lync Server provides a user experience that is familiar to users of traditional audio bridge services including PSTN dial-in services with touch-tone call control commands.</span></span> <span data-ttu-id="52978-111">Il contient en outre de puissantes fonctionnalités de planification, de participation et de gestion qui sont uniquement disponibles avec une plateforme de communications unifiées intégrée.</span><span class="sxs-lookup"><span data-stu-id="52978-111">At the same time, it incorporates powerful scheduling, joining, and management features available only with an integrated unified communications platform.</span></span>

<span data-ttu-id="52978-112">En un seul clic, les utilisateurs peuvent planifier une réunion à partir d’Outlook.</span><span class="sxs-lookup"><span data-stu-id="52978-112">With a single click, users can schedule a meeting from Outlook.</span></span> <span data-ttu-id="52978-113">Détails, tels que l’heure de la réunion, l’emplacement et les participants, suivez le modèle Outlook familier.</span><span class="sxs-lookup"><span data-stu-id="52978-113">Details, such as meeting time, location, and attendees, follow the familiar Outlook template.</span></span> <span data-ttu-id="52978-114">De plus, les informations spécifiques à la téléconférence, telles que le numéro de connexion, les ID de réunion et les rappels de code confidentiel sont automatiquement renseignées.</span><span class="sxs-lookup"><span data-stu-id="52978-114">Additionally, conference call-specific information, such as dial-in number, meeting IDs, and personal identification number (PIN) reminders, are automatically populated.</span></span>

<span data-ttu-id="52978-115">Pour vous assurer que seules les personnes autorisées participent à un appel, Lync Server offre plusieurs niveaux d’authentification pour les participants.</span><span class="sxs-lookup"><span data-stu-id="52978-115">To help ensure that only the authorized people participate in a call, Lync Server provides multiple levels of authentication for participants.</span></span> <span data-ttu-id="52978-116">Les utilisateurs qui se connectent à l’aide de Lync sont déjà authentifiés par les services de domaine Active Directory et n’ont pas besoin d’entrer un code confidentiel, un code d’accès ou un ID de réunion.</span><span class="sxs-lookup"><span data-stu-id="52978-116">Users who join by using Lync are already authenticated by the Active Directory Domain Services and do not need to enter a PIN, pass code, or meeting ID.</span></span>

<span data-ttu-id="52978-117">Lync simplifie l’expérience utilisateur de la vidéoconférence en incorporant la vidéo dans le client unifié de sorte que la planification d’une réunion avec vidéo ou la transmission spontanée de la vidéo soit transparente et facile.</span><span class="sxs-lookup"><span data-stu-id="52978-117">Lync simplifies the video conferencing user experience by incorporating video into the unified client so that scheduling a meeting with video or escalating to video spontaneously is seamless and easy.</span></span>

<span data-ttu-id="52978-118">Lync Server facilite l’ajout d’une vidéo à un appel téléphonique standard en un seul clic.</span><span class="sxs-lookup"><span data-stu-id="52978-118">Lync Server makes it easy to add video to a standard phone call in just one click.</span></span> <span data-ttu-id="52978-119">Lorsqu’une conférence ou un appel vidéo englobe plusieurs participants, chaque utilisateur peut voir simultanément les vidéos de cinq autres utilisateurs au maximum ou un présentateur peut choisir une source vidéo qui sera diffusée exclusivement à tout le monde.</span><span class="sxs-lookup"><span data-stu-id="52978-119">When there are multiple participants in a video call or a conference, each user can see video from up to five other users simultaneously, or a presenter can choose just one video source to be seen exclusively by everyone.</span></span>

<span data-ttu-id="52978-120">La vidéo haute définition (résolution 1270 x 720 ; rapport hauteur/largeur 16:9) et la vidéo VGA (résolution 640 x 480, format d’image 4:3) sont prises en charge pour les appels P2P entre les utilisateurs exécutant Lync sur des ordinateurs haut de gamme.</span><span class="sxs-lookup"><span data-stu-id="52978-120">High-definition video (resolution 1270 x 720; aspect ratio 16:9) and VGA video (resolution 640 x 480; aspect ratio 4:3) are supported for peer-to-peer calls between users running Lync on high-end computers.</span></span> <span data-ttu-id="52978-121">La résolution perçue par chaque participant lors d’une même conversation peut varier en fonction des capacités vidéo de leur matériel respectif.</span><span class="sxs-lookup"><span data-stu-id="52978-121">The resolution viewed by each participant in a single conversation may differ, depending on the video capabilities of each user’s respective hardware.</span></span>

<span data-ttu-id="52978-p108">Les administrateurs informatiques peuvent définir des stratégies pour restreindre ou désactiver la vidéo haute définition ou VGA sur certains clients, en fonction des capacités de l’ordinateur, de la bande passante du réseau et de la présence d’une caméra capable de fournir la résolution requise. Ces stratégies sont appliquées via un provisionnement intrabande.</span><span class="sxs-lookup"><span data-stu-id="52978-p108">IT administrators can set policies to restrict or disable high-definition or VGA video on clients, depending on computer capability, network bandwidth, and the presence of a camera able to deliver the required resolution. These policies are enforced through in-band provisioning.</span></span>

</div>

<div>

## <a name="web-conferencing"></a><span data-ttu-id="52978-124">Conférence web</span><span class="sxs-lookup"><span data-stu-id="52978-124">Web conferencing</span></span>

<span data-ttu-id="52978-125">Lync Server intègre des fonctionnalités de partage de conférence telles que bureau, application, pièce jointe, tableau blanc, sondage et PowerPoint dans le Lync rationalisé.</span><span class="sxs-lookup"><span data-stu-id="52978-125">Lync Server integrates conferencing sharing features such as desktop, application, attachment, whiteboard, poll and PowerPoint into the streamlined Lync.</span></span> <span data-ttu-id="52978-126">En combinant cette fonctionnalité à la conférence audio ou vidéo, vous obtenez une session hautement collaborative et efficace, et très simple à administrer.</span><span class="sxs-lookup"><span data-stu-id="52978-126">Combined with audio or video conferencing, the result is a highly immersive and collaborative session that is simple to facilitate.</span></span>

<span data-ttu-id="52978-127">Pour améliorer l’expérience globale des utilisateurs présentant ou affichant des présentations PowerPoint, Lync Server 2013 utilise Office Web Apps pour gérer les présentations PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="52978-127">To improve the overall experience of users presenting or viewing PowerPoint presentations, Lync Server 2013 employs Office Web Apps to handle PowerPoint presentations.</span></span> <span data-ttu-id="52978-128">Les utilisateurs peuvent partager une image ou copier et coller du texte à l’aide d’un tableau blanc dans la réunion Lync.</span><span class="sxs-lookup"><span data-stu-id="52978-128">Users can share a picture or copy and paste text using a Whiteboard in the Lync meeting.</span></span> <span data-ttu-id="52978-129">Les présentateurs peuvent effectuer des sondages dans la réunion Lync pour demander des commentaires auprès des participants.</span><span class="sxs-lookup"><span data-stu-id="52978-129">Presenters can conduct polls in the Lync meeting to solicit feedback from the attendees.</span></span>

<span data-ttu-id="52978-130">Le partage de bureau permet aux présentateurs de diffuser des éléments visuels, des applications, des pages Web, des documents, des logiciels ou une partie de leurs bureaux aux participants distants, directement à partir de Lync.</span><span class="sxs-lookup"><span data-stu-id="52978-130">Desktop sharing enables presenters to broadcast any visuals, applications, webpages, documents, software, or part of their desktops to remote participants in real time, right from Lync.</span></span> <span data-ttu-id="52978-131">Les membres du public peuvent suivre les mouvements de souris et les saisies au clavier.</span><span class="sxs-lookup"><span data-stu-id="52978-131">Audience members can follow along with mouse movements and keyboard input.</span></span> <span data-ttu-id="52978-132">Les présentateurs peuvent choisir de partager l’intégralité de l’écran ou seulement une partie de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="52978-132">Presenters can choose to share the entire screen or only a portion.</span></span> <span data-ttu-id="52978-133">En partageant leur Bureau, les présentateurs peuvent proposer aux participants des démonstrations interactives sur des produits ou des logiciels, peu importe où ils se trouvent.</span><span class="sxs-lookup"><span data-stu-id="52978-133">By sharing their desktops, presenters are able to engage with their audiences in interactive product or software demos from any location.</span></span>

<span data-ttu-id="52978-p112">Le partage d’application permet aux présentateurs de partager le contrôle des logiciels sur leur Bureau sans perdre de vue les commentaires ou les questions textuelles des participants. Les présentateurs peuvent aussi déléguer le contrôle de l’application aux participants à la réunion.</span><span class="sxs-lookup"><span data-stu-id="52978-p112">Application sharing enables presenters to share control of software on their desktops without losing sight of participant feedback or text questions. Presenters can also delegate control of the application to meeting participants.</span></span>

</div>

<div>

## <a name="dial-in-conferencing"></a><span data-ttu-id="52978-136">Conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="52978-136">Dial-in Conferencing</span></span>

<span data-ttu-id="52978-137">Pour les utilisateurs qui n’utilisent pas d’ordinateur personnel, plusieurs méthodes sont disponibles pour rejoindre une conférence téléphonique Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52978-137">For users that are not using a personal computer, there are several methods available for joining a Lync Server conference call.</span></span> <span data-ttu-id="52978-138">Un utilisateur PSTN peut composer un numéro d’accès, accéder au pont de réunion, puis entrer l’ID de réunion.</span><span class="sxs-lookup"><span data-stu-id="52978-138">A PSTN user can dial an access number, access the meeting bridge, and then enter the meeting ID.</span></span> <span data-ttu-id="52978-139">Pour des réunions davantage sécurisées, le système peut aussi inviter l’utilisateur à entrer son code confidentiel afin de s’authentifier sur Active Directory.</span><span class="sxs-lookup"><span data-stu-id="52978-139">For more secure meetings, the user can also be required to enter his or her PIN to authenticate against Active Directory.</span></span> <span data-ttu-id="52978-140">Lync Server prend également en charge les appareils Lync Phone Edition, qui sont des appareils de téléphonie IP autonomes fournis par des partenaires Microsoft.</span><span class="sxs-lookup"><span data-stu-id="52978-140">Lync Server also supports Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

