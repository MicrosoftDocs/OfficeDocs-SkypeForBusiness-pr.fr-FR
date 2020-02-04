---
title: 'Lync Server 2013 : Nouveautés pour les clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f938ccc4e4a040307a7cf86a8084353c480cfdca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="e7ddc-102">Nouveautés pour les clients dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7ddc-102">What's new for clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7ddc-103">_**Dernière modification de la rubrique :** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="e7ddc-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="e7ddc-104">Microsoft Lync 2013 dispose d’une interface utilisateur repensée et de nouvelles fonctionnalités importantes.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="e7ddc-105">Pour les administrateurs, le client est désormais inclus dans le programme d’installation d’Office, offrant ainsi une approche plus rationalisée pour le déploiement d’Office et la personnalisation des clients au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7ddc-106">Pour obtenir un affichage illustré des mises à jour de l’interface utilisateur de Lync 2013, voir « Nouveautés de Lync 2013 <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>».</span><span class="sxs-lookup"><span data-stu-id="e7ddc-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="e7ddc-107">Intégration à l’installation d’Office</span><span class="sxs-lookup"><span data-stu-id="e7ddc-107">Integration with Office Setup</span></span>

<span data-ttu-id="e7ddc-108">Le client Lync 2013 et le complément réunion en ligne pour Lync 2013, qui prend en charge la gestion de la réunion à partir du client de messagerie et de collaboration Outlook, sont désormais inclus dans le programme d’installation d’Office 2013.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="e7ddc-109">Dans les versions précédentes de Lync et Office Communicator, vous pouvez utiliser les propriétés Windows Installer pour personnaliser et contrôler l’installation d’Office.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="e7ddc-110">Dans la mesure où Lync 2013 est intégré au programme d’installation d’Office, vous pouvez utiliser les méthodes suivantes pour personnaliser le programme d’installation de Lync 2013 :</span><span class="sxs-lookup"><span data-stu-id="e7ddc-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="e7ddc-111">Utilisation de l’outil de personnalisation Office</span><span class="sxs-lookup"><span data-stu-id="e7ddc-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="e7ddc-112">Utiliser le fichier config. xml pour effectuer des tâches d’installation</span><span class="sxs-lookup"><span data-stu-id="e7ddc-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="e7ddc-113">Utiliser les options de la ligne de commande du programme d’installation</span><span class="sxs-lookup"><span data-stu-id="e7ddc-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7ddc-114">Le programme d’installation de Lync 2013 ne désinstalle pas les versions précédentes de Lync ou d’Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="e7ddc-115">Le client Lync 2013 s’installe côte à côte avec d’autres clients Lync ou Office Communicator</span><span class="sxs-lookup"><span data-stu-id="e7ddc-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="e7ddc-116">Pour plus d’informations, reportez-vous à [déploiement de clients Lync dans Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="e7ddc-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="e7ddc-117">Déploiement d’une stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="e7ddc-117">Group Policy Deployment</span></span>

<span data-ttu-id="e7ddc-118">Comme Lync 2013 est désormais inclus dans le programme d’installation d’Office, la méthode de déploiement des paramètres de stratégie de groupe Lync a changé.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="e7ddc-119">Dans les versions précédentes de Lync et d’Office Communicator, vous pouvez utiliser la fonction Communicator. adm pour définir les paramètres de stratégie de groupe, alors que dans Lync 2013, vous pouvez désormais utiliser les modèles d’administration ADMX et ADML fournis avec la stratégie de groupe Office Modèles d’administration.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="e7ddc-120">Pour plus d’informations, voir [paramètres de stratégie de groupe pour Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="e7ddc-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="e7ddc-121">Mises à jour de compléments de planification Outlook</span><span class="sxs-lookup"><span data-stu-id="e7ddc-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="e7ddc-122">Le complément réunion en ligne pour Lync 2013 inclut la personnalisation d’invitation à la réunion et les options de nouvelle réunion.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="e7ddc-123">Les administrateurs peuvent personnaliser les invitations aux réunions de l’organisation en ajoutant un logo personnalisé, une URL d’assistance, une URL d’exclusion de responsabilité ou un texte de pied de page personnalisé.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="e7ddc-124">Pour plus d’informations, reportez-vous à [la rubrique Personnalisation du complément de réunion en ligne dans Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="e7ddc-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="e7ddc-125">Les commandes de nouvelle option de désactivation des participants permettent aux organisateurs de la réunion de planifier des conférences qui ont désactivé le son et la vidéo des participants par défaut.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="e7ddc-126">Plug-in d’infrastructure de bureau virtuel</span><span class="sxs-lookup"><span data-stu-id="e7ddc-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="e7ddc-127">Le client Lync 2013 prend désormais en charge l’audio et la vidéo dans un environnement VDI (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="e7ddc-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="e7ddc-128">Un utilisateur peut connecter un périphérique audio ou vidéo (par exemple, un casque ou un appareil photo) à l’ordinateur local (par exemple, un client léger ou un ordinateur réaffecté).</span><span class="sxs-lookup"><span data-stu-id="e7ddc-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="e7ddc-129">L’utilisateur peut se connecter à la machine virtuelle, se connecter au client 2013 Lync qui s’exécute sur l’ordinateur virtuel et participer à une communication audio et vidéo en temps réel, comme si le client s’exécute localement.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="e7ddc-130">Les fonctionnalités suivantes sont prises en charge dans un environnement de bureau virtuel :</span><span class="sxs-lookup"><span data-stu-id="e7ddc-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="e7ddc-131">Intégration d’appareil pour l’audio et la vidéo, notamment les suivantes :</span><span class="sxs-lookup"><span data-stu-id="e7ddc-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="e7ddc-132">Contrôles d’appel à partir de l’appareil</span><span class="sxs-lookup"><span data-stu-id="e7ddc-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="e7ddc-133">Intégration de la présence sur l’appareil</span><span class="sxs-lookup"><span data-stu-id="e7ddc-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="e7ddc-134">Prise en charge de plusieurs HID (appareil d’interface utilisateur)</span><span class="sxs-lookup"><span data-stu-id="e7ddc-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="e7ddc-135">Emplacement et assistance technique pour les services d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="e7ddc-136">Prise en charge de toutes les modalités de Lync, notamment la messagerie instantanée, l’audio, la vidéo, le partage d’application, le partage de bureau, le partage PowerPoint, le tableau blanc et le transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="e7ddc-137">Prise en charge de l’audio et de la vidéo dans les appels de personne à personne et aux conférences téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="e7ddc-138">Pour plus d’informations sur le déploiement du plug-in VDI, voir [déploiement du plug-in LYNC VDI dans Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span><span class="sxs-lookup"><span data-stu-id="e7ddc-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="e7ddc-139">Améliorations de la vidéo</span><span class="sxs-lookup"><span data-stu-id="e7ddc-139">Video Enhancements</span></span>

<span data-ttu-id="e7ddc-140">Plusieurs nouvelles fonctions améliorent considérablement l’interface vidéo des participants à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="e7ddc-141">La vidéo est améliorée grâce à la détection des visages et au cadre intelligent, de sorte que la vidéo d’un participant se déplace pour qu’elle reste centrée dans le cadre.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="e7ddc-142">La vidéo haute définition est désormais prise en charge dans des appels à deux ou des conférences multiparties.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-142">High-definition video is now supported in two-party calls and multiparty conferences.</span></span> <span data-ttu-id="e7ddc-143">Les utilisateurs peuvent bénéficier de résolutions jusqu’à HD 1080P.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-143">Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="e7ddc-144">Les participants peuvent faire votre choix parmi les différentes dispositions de la réunion : le mode Galerie affiche les images et les vidéos de tous les participants. Vue présentateur affiche le contenu de la réunion et uniquement la vidéo ou l’image du présentateur actuel. Le mode présentation affiche uniquement le contenu de la réunion. Affichage Compact affiche uniquement les contrôles de la réunion.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="e7ddc-145">Grâce à la nouvelle fonctionnalité Galerie, les participants peuvent voir plusieurs flux vidéo en même temps.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-145">With the new Gallery feature, participants can see multiple video feeds at the same time.</span></span> <span data-ttu-id="e7ddc-146">Si la Conférence compte plus de cinq participants, les flux vidéo des seuls participants les plus actifs apparaissent dans la ligne supérieure, et les images des autres participants.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-146">If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="e7ddc-147">Les participants peuvent utiliser le verrouillage vidéo pour sélectionner un ou plusieurs des flux vidéo disponibles à afficher à tout moment.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="e7ddc-148">Les présentateurs peuvent utiliser la fonction actualités vidéo pour sélectionner le flux vidéo d’une personne de sorte que tous les participants à la réunion voient ce participant uniquement.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="e7ddc-149">Intégration d’une salle de conversation</span><span class="sxs-lookup"><span data-stu-id="e7ddc-149">Chat Room Integration</span></span>

<span data-ttu-id="e7ddc-150">Lync 2013 intègre désormais les fonctionnalités précédemment fournies par la discussion de groupe Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="e7ddc-151">Un client de discussion de groupe distinct n’est plus nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="e7ddc-152">À partir de Lync 2013, les utilisateurs peuvent rechercher des salles de conversation, ajouter des salles de conversation à leurs contacts, surveiller l’activité des salles de conversation et lire et publier des messages.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="e7ddc-153">Les utilisateurs peuvent créer des flux de sujets de sorte qu’ils soient avertis lorsqu’une personne figurant dans l’une de leurs salles de conversation ajoute un billet contenant des mots clés spécifiques.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="e7ddc-154">La nouvelle page d’options de **conversation permanente** permet aux utilisateurs de définir des alertes et des sons de notification qui s’appliquent quand des personnes publient des messages dans leurs salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="e7ddc-155">Mises à jour de Lync Web App</span><span class="sxs-lookup"><span data-stu-id="e7ddc-155">Lync Web App Updates</span></span>

<span data-ttu-id="e7ddc-156">Lync Web App est le client de conférences Web pour les réunions Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="e7ddc-157">Dans cette version, l’ajout de l’audio et de la vidéo de l’ordinateur à Lync Web App fournit une interface complète en réunion aux personnes qui n’ont pas de client Lync installé en local.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="e7ddc-158">Les participants à une réunion ont accès à toutes les fonctionnalités de collaboration et de partage, tandis que le présentateur de la réunion dispose du contrôle.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="e7ddc-159">Lorsqu’un utilisateur tente de participer à une réunion, mais qu’il n’a pas de client installé en local, Lync Web App s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="e7ddc-160">Si vous voulez autoriser d’autres options de participation à la réunion, vous pouvez configurer la page de participation à une réunion. Pour plus d’informations, reportez-vous à [la rubrique Configuration de la page de participation à une réunion dans Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) .</span><span class="sxs-lookup"><span data-stu-id="e7ddc-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e7ddc-161">En raison des améliorations apportées à Lync Web App, une version mise à jour du participant n’est pas disponible pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="e7ddc-162">Lync Web App est le client de votre choix pour les participants extérieurs à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="e7ddc-163">Aucune installation de client local n’est nécessaire, bien que les fonctionnalités audio, vidéo et de partage nécessitent qu’un plug-in soit installé lors de la première utilisation.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="e7ddc-164">2013 Lync pour les clients mobiles mises à jour</span><span class="sxs-lookup"><span data-stu-id="e7ddc-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="e7ddc-165">Outre les fonctionnalités de présence, de contacts et de messagerie instantanée améliorées, les clients mobiles Lync 2013 permettent désormais des appels audio et vidéo via Internet et les connexions de données cellulaires.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="e7ddc-166">En un seul appui du lien de la réunion dans un élément de calendrier, les utilisateurs mobiles peuvent rejoindre des réunions audio et vidéo Lync.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="e7ddc-167">Pour plus d’informations sur les clients mobiles Lync 2013, voir [planification pour les clients mobiles dans Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="e7ddc-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="e7ddc-168">Mises à jour de l’interface utilisateur de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e7ddc-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="e7ddc-169">Mises à jour de l’accessibilité</span><span class="sxs-lookup"><span data-stu-id="e7ddc-169">Accessibility Updates</span></span>

<span data-ttu-id="e7ddc-170">Lync 2013 inclut plusieurs nouvelles fonctionnalités d’accessibilité.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="e7ddc-171">Lync 2013 prend en charge la résolution PPP élevée, permettant aux utilisateurs de mettre à l’échelle du texte et des graphismes pour 125% et 150% de points par pouce.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="e7ddc-172">Lync fournit une prise en charge de contraste élevé afin que l’interface utilisateur reste entièrement fonctionnelle lorsqu’elle est utilisée avec des thèmes à contraste élevé dans Windows.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="e7ddc-173">Lync propose plus de 100 raccourcis clavier pour permettre aux utilisateurs d’accéder à des fonctions importantes sans souris.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="e7ddc-174">Par exemple, les utilisateurs peuvent appuyer sur ALT + C pour accepter un appel, ou sur Alt + I pour l’ignorer sans avoir besoin d’appuyer sur la touche Tab ou de définir le focus.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="e7ddc-175">Appuyer sur (Alt + Q) met fin à un appel, (Ctrl + N) démarre OneNote et (Alt + T) ouvre le menu outils.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="e7ddc-176">La prise en charge de lecteurs d’écran complets dans Lync 2013 permet de lire à haute voix toutes les notifications, demandes entrantes et messages instantanés lorsqu’un lecteur d’écran est activé.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="e7ddc-177">Présence lors du partage</span><span class="sxs-lookup"><span data-stu-id="e7ddc-177">Presence While Sharing</span></span>

<span data-ttu-id="e7ddc-178">Lorsque Lync détecte qu’un utilisateur partage, Lync attribue automatiquement à l’utilisateur un statut de présence de présentation.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="e7ddc-179">Ce statut bloque toutes les communications entrantes, sauf si l’expéditeur reçoit la relation de confidentialité groupe de travail.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="e7ddc-180">Si l’utilisateur utilise entièrement la fonctionnalité de partage sur un moniteur secondaire, Lync n’attribue pas de statut de présence présentant une présentation.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="e7ddc-181">Mises à jour de la fenêtre de conversation</span><span class="sxs-lookup"><span data-stu-id="e7ddc-181">Conversation Window Updates</span></span>

<span data-ttu-id="e7ddc-182">La fenêtre de conversation repensée vous permet d’accéder plus rapidement aux fonctions importantes.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="e7ddc-183">Grâce à la nouvelle fonctionnalité de conversations par onglets, les utilisateurs peuvent désormais conserver tous leurs messages instantanés et salles de conversation dans une seule fenêtre de conversation.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-183">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window.</span></span> <span data-ttu-id="e7ddc-184">Les onglets situés sur le côté gauche de la fenêtre de conversation permettent aux utilisateurs de naviguer facilement parmi toutes les conversations actives.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-184">The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="e7ddc-185">Les utilisateurs peuvent isoler une conversation individuelle dans une fenêtre séparée, puis redimensionner la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-185">Users can pop out an individual conversation into a separate window, and then resize the window.</span></span> <span data-ttu-id="e7ddc-186">Ils peuvent également intégrer la fenêtre dans la fenêtre de conversation principale.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-186">They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="e7ddc-187">Lync 2013 rouvert les conversations d’un utilisateur lorsque celui-ci se déconnecte et se reconnecte à Lync.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="e7ddc-188">Les utilisateurs peuvent rapidement ajouter des messages instantanés, des vidéos, le partage de programmes, le partage de bureau ou des outils de conférence Web (tableau blanc, notes de réunion, blocs-notes partagés et pièces jointes) à une conversation.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="e7ddc-189">Dans une réunion dans laquelle la vidéo ou le contenu est en cours de partage, les utilisateurs peuvent isoler la vidéo ou le contenu partagé de la réunion, puis redimensionner la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="e7ddc-190">Mises à jour de la fenêtre principale de Lync</span><span class="sxs-lookup"><span data-stu-id="e7ddc-190">Lync Main Window Updates</span></span>

<span data-ttu-id="e7ddc-191">Le nouveau look rationalisé conserve les fonctionnalités familières telles que le champ **activités du jour** , le sélecteur d’État et la **configuration de votre** sélecteur d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="e7ddc-192">Lorsque la messagerie instantanée est activée, les utilisateurs voient une nouvelle icône de **salles de conversation** dans la page principale de Lync.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="e7ddc-193">Les **salles de conversation** permettent aux utilisateurs d’accéder rapidement à leurs salles de conversation et filtres.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="e7ddc-194">Les utilisateurs peuvent cliquer sur l’icône d’affichage pour basculer vers l’affichage **contacts** , la vue **salles de conversation** , l’affichage **conversations** ou le mode **téléphone** .</span><span class="sxs-lookup"><span data-stu-id="e7ddc-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="e7ddc-195">Si les utilisateurs ont été migrés vers Exchange 2013, ils peuvent télécharger une image de haute résolution.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="e7ddc-196">Mises à jour de la carte de visite et du mode contacts</span><span class="sxs-lookup"><span data-stu-id="e7ddc-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="e7ddc-197">Lync 2013 offre aux utilisateurs différentes manières de afficher des contacts et des groupes dans leur affichage **contacts** .</span><span class="sxs-lookup"><span data-stu-id="e7ddc-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="e7ddc-198">Le nouveau magasin de contacts unifié, une fois que les contacts Lync des utilisateurs sont déplacés vers Exchange 2013, les utilisateurs peuvent accéder à leurs contacts et les gérer à partir de Lync 2013, Outlook ou Outlook Web App, et leurs favoris restent synchronisés.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="e7ddc-199">Par exemple, si un utilisateur ajoute un contact aux favoris dans Outlook, le contact apparaît dans le groupe favoris de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="e7ddc-200">Si vous avez ajouté et configuré le proxy XMPP et la passerelle XMPP, les utilisateurs peuvent ajouter des contacts de partenaires de XMPP pour la messagerie instantanée et la présence.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="e7ddc-201">Un nouveau **contact ajouter un contact qui n’est pas présent dans ma société** offre aux utilisateurs un moyen facile d’ajouter des personnes externes à l’organisation.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="e7ddc-202">Un nouveau groupe de **favoris** permet aux utilisateurs de créer une liste de personnes qui communiquent le plus souvent aux utilisateurs un accès plus rapide.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="e7ddc-203">Les utilisateurs peuvent utiliser la nouvelle page d’options de la **liste de contacts** pour choisir la manière dont les utilisateurs veulent trier et afficher les contacts.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-203">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts.</span></span> <span data-ttu-id="e7ddc-204">Les utilisateurs peuvent sélectionner un affichage à deux lignes développé qui affiche les images des contacts ou un affichage d’une seule ligne condensé.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-204">Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view.</span></span> <span data-ttu-id="e7ddc-205">Les utilisateurs peuvent également trier les contacts par ordre alphabétique ou par disponibilité.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-205">Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="e7ddc-206">Mises à jour de conférence</span><span class="sxs-lookup"><span data-stu-id="e7ddc-206">Conferencing Updates</span></span>

<span data-ttu-id="e7ddc-207">Lync 2013 offre plusieurs améliorations apportées aux fonctionnalités de conférence.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="e7ddc-208">En fonction du type de réunion, les utilisateurs peuvent désormais désactiver le son du public et autoriser ou bloquer le partage vidéo lors de la planification de la réunion.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-208">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting.</span></span> <span data-ttu-id="e7ddc-209">Ces options sont disponibles sur la page Options de la **réunion** et sont recommandées pour les réunions de grande taille avec plus de 20 participants.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-209">These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="e7ddc-210">L’utilisation des contrôles audio simples dans la salle de réunion permet à l’utilisateur de contrôler les options audio, comme le silence, le réactivation du son, le changement de périphérique, etc.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="e7ddc-211">Lorsque vous partagez des programmes, les utilisateurs peuvent sélectionner plusieurs programmes à partager s’ils ont besoin d’utiliser plusieurs programmes.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="e7ddc-212">Les utilisateurs peuvent désormais télécharger des présentations qui contiennent des clips vidéo en téléchargeant le fichier PowerPoint et en pointant la souris sur la diapositive pour afficher des commandes vidéo (lecture, pause, contrôles audio, etc.).</span><span class="sxs-lookup"><span data-stu-id="e7ddc-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="e7ddc-213">Pendant la réunion, les utilisateurs peuvent fusionner une autre conversation ouverte dans la réunion en utilisant l’option **fusionner cet appel** dans le menu **autres options** (**...**).</span><span class="sxs-lookup"><span data-stu-id="e7ddc-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="e7ddc-214">Pour afficher les noms des participants, les utilisateurs peuvent survoler le pointeur de la souris au-dessus du bouton **voir les participants** ou cliquer sur Afficher la **liste des participants** pour ancrer le panneau dans la réunion.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="e7ddc-215">En fonction du type de réunion, les utilisateurs peuvent sélectionner à partir de plusieurs affichages de contenus et de participants différents.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="e7ddc-216">Les enregistrements de réunion sont automatiquement enregistrés dans un format lisible par le lecteur Windows Media (MP4).</span><span class="sxs-lookup"><span data-stu-id="e7ddc-216">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4).</span></span> <span data-ttu-id="e7ddc-217">Les utilisateurs peuvent partager facilement le fichier avec tout le monde, ou utiliser la fonctionnalité de **publication** dans le gestionnaire d’enregistrements pour publier l’enregistrement à un emplacement partagé.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-217">Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="e7ddc-218">OneNote vous permet de créer de nouvelles façons de collaborer au cours d’une réunion.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-218">OneNote enables new ways to collaborate in a meeting.</span></span> <span data-ttu-id="e7ddc-219">Au cours d’une réunion, les utilisateurs peuvent prendre des notes à l’aide de OneNote pour une utilisation personnelle après la réunion, ou utiliser des blocs-notes partagés et collaborer avec les participants à la réunion en temps réel.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-219">During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time.</span></span> <span data-ttu-id="e7ddc-220">Tous les membres d’une équipe peuvent accéder aux notes partagées pour collaborer, rassembler des idées ou utiliser les pages de bloc-notes comme tableau blanc virtuel.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-220">All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard.</span></span> <span data-ttu-id="e7ddc-221">Les personnes et le contenu partagés dans la réunion sont automatiquement ajoutés aux notes.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-221">People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="e7ddc-222">Les utilisateurs peuvent passer d’un type de contenu à un autre en utilisant **partager du contenu et mener des activités de réunion** en bas de la salle de réunion.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-222">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room.</span></span> <span data-ttu-id="e7ddc-223">Les utilisateurs peuvent également utiliser le menu **gérer le contenu à présenter** pour choisir le contenu qu’ils souhaitent partager.</span><span class="sxs-lookup"><span data-stu-id="e7ddc-223">Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e7ddc-224">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7ddc-224">See Also</span></span>


[<span data-ttu-id="e7ddc-225">Planification pour les clients dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7ddc-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

