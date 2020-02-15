---
title: 'Lync Server 2013 : nouveautés pour les clients'
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
ms.openlocfilehash: 210218ec3250e31356564731286735df48836ad6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="9581a-102">Nouveautés pour les clients dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9581a-102">What's new for clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9581a-103">_**Dernière modification de la rubrique :** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="9581a-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="9581a-104">Microsoft Lync 2013 dispose d’une interface utilisateur repensée et de nouvelles fonctionnalités importantes.</span><span class="sxs-lookup"><span data-stu-id="9581a-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="9581a-105">Pour les administrateurs, le client est désormais inclus dans le programme d’installation d’Office, ce qui offre une approche plus rationalisée pour le déploiement d’Office et la personnalisation des clients au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="9581a-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9581a-106">Pour obtenir une vue d’ensemble des mises à jour de l’interface utilisateur de Lync 2013, voir « What’s New in <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>Lync 2013 » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="9581a-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="9581a-107">Intégration au programme d’installation d’Office</span><span class="sxs-lookup"><span data-stu-id="9581a-107">Integration with Office Setup</span></span>

<span data-ttu-id="9581a-108">Le client Lync 2013 et le complément de réunion en ligne pour Lync 2013, qui prend en charge la gestion des réunions à partir du client de messagerie et de collaboration Outlook, sont désormais inclus dans le programme d’installation d’Office 2013.</span><span class="sxs-lookup"><span data-stu-id="9581a-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="9581a-109">Dans les versions précédentes de Lync et Office Communicator, vous pouviez utiliser les propriétés de Windows Installer pour personnaliser et contrôler l’installation d’Office.</span><span class="sxs-lookup"><span data-stu-id="9581a-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="9581a-110">Étant donné que Lync 2013 est intégré au programme d’installation d’Office, vous pouvez utiliser les méthodes suivantes pour personnaliser le programme d’installation de Lync 2013 :</span><span class="sxs-lookup"><span data-stu-id="9581a-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="9581a-111">Utiliser l’Outil de personnalisation Office (OPO)</span><span class="sxs-lookup"><span data-stu-id="9581a-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="9581a-112">Utiliser le fichier Config.xml pour effectuer les tâches d’installation</span><span class="sxs-lookup"><span data-stu-id="9581a-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="9581a-113">Utiliser les options de ligne de commande du programme d’installation</span><span class="sxs-lookup"><span data-stu-id="9581a-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9581a-114">Le programme d’installation de Lync 2013 ne désinstalle pas les versions précédentes de Lync ou d’Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="9581a-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="9581a-115">Le client Lync 2013 installe côte à côte avec d’autres clients Lync ou Office Communicator</span><span class="sxs-lookup"><span data-stu-id="9581a-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="9581a-116">Pour plus d’informations, reportez-vous à la rubrique [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="9581a-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="9581a-117">Déploiement de la stratégie de groupe</span><span class="sxs-lookup"><span data-stu-id="9581a-117">Group Policy Deployment</span></span>

<span data-ttu-id="9581a-118">Étant donné que Lync 2013 est désormais inclus dans le programme d’installation d’Office, la méthode de déploiement des paramètres de stratégie de groupe Lync a changé.</span><span class="sxs-lookup"><span data-stu-id="9581a-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="9581a-119">Dans les versions précédentes de Lync et Office Communicator, vous pouviez utiliser Communicator. adm pour définir les paramètres de la stratégie de groupe, tandis que dans Lync 2013 vous pouvez désormais utiliser les modèles d’administration Lync ADMX et ADML fournis avec la stratégie de groupe Office. Modèles d’administration.</span><span class="sxs-lookup"><span data-stu-id="9581a-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="9581a-120">Pour plus d’informations, consultez la rubrique [paramètres de stratégie de groupe pour Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="9581a-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="9581a-121">Mises à jour apportées au complément Planification dans Outlook</span><span class="sxs-lookup"><span data-stu-id="9581a-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="9581a-122">Le complément de réunion en ligne pour Lync 2013 inclut une personnalisation des invitations aux réunions et de nouvelles options de réunion.</span><span class="sxs-lookup"><span data-stu-id="9581a-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="9581a-123">Les administrateurs ont la possibilité de personnaliser les invitations à des réunions de leur organisation en ajoutant un logo personnalisé, une URL de support technique, une URL d’exclusion de responsabilité ou encore du texte personnalisé dans le pied de page.</span><span class="sxs-lookup"><span data-stu-id="9581a-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="9581a-124">Pour plus d’informations, reportez-vous à [la rubrique Customizing the online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="9581a-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="9581a-125">De nouveaux contrôles de désactivation du son des participants permettent aux organisateurs de réunion de planifier des conférences dans lesquelles l’audio et la vidéo des participants sont désactivés par défaut.</span><span class="sxs-lookup"><span data-stu-id="9581a-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="9581a-126">Plug-in VDI (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="9581a-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="9581a-127">Le client Lync 2013 prend désormais en charge les fonctionnalités audio et vidéo dans un environnement VDI (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="9581a-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="9581a-128">Un utilisateur peut connecter un périphérique audio ou vidéo (par exemple, un casque ou une caméra) à l’ordinateur local (par exemple, un client léger ou un ordinateur réaffecté).</span><span class="sxs-lookup"><span data-stu-id="9581a-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="9581a-129">L’utilisateur peut se connecter à la machine virtuelle, se connecter au client Lync 2013 qui est en cours d’exécution sur l’ordinateur virtuel et participer à la communication audio et vidéo en temps réel comme si le client était en cours d’exécution localement.</span><span class="sxs-lookup"><span data-stu-id="9581a-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="9581a-130">Les fonctionnalités suivantes sont prises en charge dans un environnement de bureau virtuel :</span><span class="sxs-lookup"><span data-stu-id="9581a-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="9581a-131">Intégration de périphériques pour l’audio et la vidéo, notamment :</span><span class="sxs-lookup"><span data-stu-id="9581a-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="9581a-132">Contrôle des appels à partir du périphérique</span><span class="sxs-lookup"><span data-stu-id="9581a-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="9581a-133">Intégration de la présence sur le périphérique</span><span class="sxs-lookup"><span data-stu-id="9581a-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="9581a-134">Prise en charge de plusieurs périphériques d’interface utilisateur (HID)</span><span class="sxs-lookup"><span data-stu-id="9581a-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="9581a-135">Prise en charge des services de localisation et d’urgence</span><span class="sxs-lookup"><span data-stu-id="9581a-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="9581a-136">Prise en charge de toutes les modalités de Lync, y compris la messagerie instantanée, l’audio, la vidéo, le partage d’applications, le partage de bureau, le partage PowerPoint, le tableau blanc et le transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="9581a-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="9581a-137">Prise en charge de l’audio et de la vidéo dans les appels de personne à personne et les téléconférences</span><span class="sxs-lookup"><span data-stu-id="9581a-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="9581a-138">Pour plus d’informations sur le déploiement du plug-in VDI, reportez-vous à [la rubrique Deploying the LYNC VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span><span class="sxs-lookup"><span data-stu-id="9581a-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="9581a-139">Améliorations apportées à la vidéo</span><span class="sxs-lookup"><span data-stu-id="9581a-139">Video Enhancements</span></span>

<span data-ttu-id="9581a-140">L’ajout de plusieurs nouvelles fonctionnalités a permis d’améliorer sensiblement l’expérience vidéo des participants à des conférences.</span><span class="sxs-lookup"><span data-stu-id="9581a-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="9581a-141">Grâce aux améliorations apportées telles que la détection du visage et le cadrage actif, la vidéo peut se déplacer pour maintenir le participant au centre du cadre.</span><span class="sxs-lookup"><span data-stu-id="9581a-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="9581a-p107">La vidéo haute définition est désormais prise en charge dans les appels à deux et les conférences à plusieurs. Les utilisateurs peuvent bénéficier de résolutions HD pouvant aller jusqu’à 1080 p.</span><span class="sxs-lookup"><span data-stu-id="9581a-p107">High-definition video is now supported in two-party calls and multiparty conferences. Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="9581a-144">Les participants ont le choix entre différentes dispositions de réunion : la vue Galerie montre l’ensemble des photos ou des vidéos des participants ; la vue Présentateur montre le contenu de la réunion et uniquement la vidéo ou l’image du présentateur actuel ; la vue Présentation montre uniquement le contenu de la réunion ; et la vue Compact montre uniquement les contrôles de la réunion.</span><span class="sxs-lookup"><span data-stu-id="9581a-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="9581a-p108">Grâce à la nouvelle fonctionnalité Galerie, les participants peuvent voir plusieurs flux vidéo en même temps. Si la conférence compte plus de cinq participants, seuls les flux vidéo des participants les plus actifs apparaissent dans la ligne du haut, tandis que des images s’affichent pour les autres participants.</span><span class="sxs-lookup"><span data-stu-id="9581a-p108">With the new Gallery feature, participants can see multiple video feeds at the same time. If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="9581a-147">Les participants peuvent utiliser l’épinglage vidéo pour sélectionner un ou plusieurs des flux vidéo disponibles et les afficher en permanence.</span><span class="sxs-lookup"><span data-stu-id="9581a-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="9581a-148">Les présentateurs peuvent utiliser la fonctionnalité de vidéo à la une pour sélectionner le flux vidéo d’une personne. De cette manière, tous les participants à la réunion voient uniquement ce participant.</span><span class="sxs-lookup"><span data-stu-id="9581a-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="9581a-149">Intégration de la salle de conversation</span><span class="sxs-lookup"><span data-stu-id="9581a-149">Chat Room Integration</span></span>

<span data-ttu-id="9581a-150">Lync 2013 intègre désormais les fonctionnalités fournies précédemment par Lync 2010 Group chat.</span><span class="sxs-lookup"><span data-stu-id="9581a-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="9581a-151">Il n’est plus nécessaire de disposer d’un client de conversation de groupe séparé.</span><span class="sxs-lookup"><span data-stu-id="9581a-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="9581a-152">À partir de Lync 2013, les utilisateurs peuvent rechercher des salles de conversation, ajouter des salles de conversation à leurs contacts, surveiller l’activité des salles de conversation, ainsi que lire et publier des messages.</span><span class="sxs-lookup"><span data-stu-id="9581a-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="9581a-153">Les utilisateurs peuvent créer des flux de sujets de manière à être informés si quelqu’un dans l’une de leurs salles de conversation ajoute un billet contenant des mots clés spécifiques.</span><span class="sxs-lookup"><span data-stu-id="9581a-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="9581a-154">Grâce à la nouvelle page d’options **Conversation permanente**, les utilisateurs peuvent définir des alertes de notification et des sons à émettre lorsque des personnes publient des messages dans leurs salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="9581a-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="9581a-155">Mises à jour de Lync Web App</span><span class="sxs-lookup"><span data-stu-id="9581a-155">Lync Web App Updates</span></span>

<span data-ttu-id="9581a-156">Lync Web App est le client de conférence Web pour les réunions Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9581a-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="9581a-157">Dans cette version, l’ajout de l’audio et de la vidéo à Lync Web App offre une expérience complète en réunion pour toute personne qui n’a pas de client Lync installé localement.</span><span class="sxs-lookup"><span data-stu-id="9581a-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="9581a-158">Les participants à la réunion ont accès à toutes les fonctionnalités de collaboration et de partage et aux contrôles de réunion du présentateur.</span><span class="sxs-lookup"><span data-stu-id="9581a-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="9581a-159">Lorsqu’un utilisateur tente de rejoindre une réunion mais qu’il ne dispose pas d’un client installé en local, Lync Web App s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="9581a-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="9581a-160">Si vous souhaitez autoriser des options supplémentaires pour rejoindre la réunion, vous pouvez configurer la page de participation aux réunions ; consultez la rubrique [configuration de la page de participation aux réunions dans Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="9581a-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="9581a-161">En raison des améliorations apportées à Lync Web App, une version mise à jour de Attendee n’est pas disponible pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9581a-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="9581a-162">Lync Web App est le client de choix pour les participants extérieurs à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="9581a-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="9581a-163">Aucun client local ne doit être installé, bien que les fonctionnalités audio, vidéo et de partage nécessitent l’installation d’un plug-in lors de la première utilisation.</span><span class="sxs-lookup"><span data-stu-id="9581a-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="9581a-164">Lync 2013 pour les mises à jour de clients mobiles</span><span class="sxs-lookup"><span data-stu-id="9581a-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="9581a-165">En plus des fonctionnalités avancées de présence, de contacts et de messagerie instantanée, les clients mobiles Lync 2013 fournissent désormais des appels vocaux et vidéo sur Internet et des connexions de données cellulaires.</span><span class="sxs-lookup"><span data-stu-id="9581a-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="9581a-166">En un seul clic sur le lien de réunion dans un élément de calendrier, les utilisateurs mobiles peuvent rejoindre des réunions vocales et vidéo Lync.</span><span class="sxs-lookup"><span data-stu-id="9581a-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="9581a-167">Pour plus d’informations sur les clients mobiles Lync 2013, voir [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="9581a-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="9581a-168">Mises à jour de l’interface utilisateur de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9581a-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="9581a-169">Mises à jour apportées à l’accessibilité</span><span class="sxs-lookup"><span data-stu-id="9581a-169">Accessibility Updates</span></span>

<span data-ttu-id="9581a-170">Lync 2013 intègre plusieurs nouvelles fonctionnalités d’accessibilité.</span><span class="sxs-lookup"><span data-stu-id="9581a-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="9581a-171">Lync 2013 prend en charge la résolution haute résolution, ce qui permet aux utilisateurs de mettre à l’échelle du texte et des graphiques pour 125% et 150% de points par pouce.</span><span class="sxs-lookup"><span data-stu-id="9581a-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="9581a-172">Lync offre une prise en charge à contraste élevé afin que l’interface utilisateur reste entièrement fonctionnelle lorsqu’elle est utilisée avec des thèmes à contraste élevé dans Windows.</span><span class="sxs-lookup"><span data-stu-id="9581a-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="9581a-173">Lync propose plus de 100 raccourcis clavier pour permettre aux utilisateurs d’accéder à des fonctions importantes sans souris.</span><span class="sxs-lookup"><span data-stu-id="9581a-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="9581a-174">Par exemple, les utilisateurs peuvent appuyer sur Alt+C pour accepter un appel ou sur Alt+I pour l’ignorer, le tout sans changer d’onglet ou définir le focus.</span><span class="sxs-lookup"><span data-stu-id="9581a-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="9581a-175">De plus, Alt+Q met fin à un appel, Ctrl+N démarre OneNote et Alt+T ouvre le menu Outils.</span><span class="sxs-lookup"><span data-stu-id="9581a-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="9581a-176">Une prise en charge étendue des lecteurs d’écran dans Lync 2013 garantit que toutes les notifications, les demandes entrantes et les messages instantanés sont lus à haute voix lorsqu’un lecteur d’écran est activé.</span><span class="sxs-lookup"><span data-stu-id="9581a-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="9581a-177">Présence pendant le partage</span><span class="sxs-lookup"><span data-stu-id="9581a-177">Presence While Sharing</span></span>

<span data-ttu-id="9581a-178">Lorsque Lync détecte qu’un utilisateur partage, Lync lui attribue automatiquement un statut de présence.</span><span class="sxs-lookup"><span data-stu-id="9581a-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="9581a-179">Cette situation bloque toutes les communications entrantes, sauf si l’expéditeur est affecté au niveau de confidentialité Groupe de travail.</span><span class="sxs-lookup"><span data-stu-id="9581a-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="9581a-180">Si l’utilisateur utilise la fonctionnalité de partage entièrement sur un moniteur secondaire, Lync n’affecte pas un statut de présence de présentation.</span><span class="sxs-lookup"><span data-stu-id="9581a-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="9581a-181">Mises à jour apportées à la fenêtre Conversation</span><span class="sxs-lookup"><span data-stu-id="9581a-181">Conversation Window Updates</span></span>

<span data-ttu-id="9581a-182">Entièrement repensée, la fenêtre Conversation offre un accès rapide aux fonctions importantes.</span><span class="sxs-lookup"><span data-stu-id="9581a-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="9581a-p116">Grâce à la nouvelle fonctionnalité de conversations par onglets, les utilisateurs peuvent à présent avoir l’ensemble de leurs messages instantanés et de leurs salles de conversation dans une seule fenêtre Conversation. Les onglets situés à gauche de la fenêtre Conversation permettent aux utilisateurs de naviguer facilement parmi toutes les conversations actives.</span><span class="sxs-lookup"><span data-stu-id="9581a-p116">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window. The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="9581a-p117">Les utilisateurs peuvent détacher une conversation individuelle dans une fenêtre séparée et redimensionner la fenêtre. Ils peuvent aussi faire revenir la fenêtre dans la fenêtre Conversation principale.</span><span class="sxs-lookup"><span data-stu-id="9581a-p117">Users can pop out an individual conversation into a separate window, and then resize the window. They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="9581a-187">Lync 2013 ouvre à nouveau les conversations d’un utilisateur lorsque celui-ci se déconnecte, puis se reconnecte à Lync.</span><span class="sxs-lookup"><span data-stu-id="9581a-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="9581a-188">Les utilisateurs peuvent rapidement ajouter la messagerie instantanée, la vidéo, le partage de programme, le partage de Bureau ou des outils de conférence web (tableau blanc, notes de réunion, blocs-notes partagés et pièces jointes) à n’importe quelle conversation.</span><span class="sxs-lookup"><span data-stu-id="9581a-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="9581a-189">Lors d’une réunion dans laquelle la vidéo ou du contenu est partagé, les utilisateurs peuvent détacher la vidéo ou le contenu partagé de la réunion, puis redimensionner la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="9581a-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="9581a-190">Mises à jour de la fenêtre principale Lync</span><span class="sxs-lookup"><span data-stu-id="9581a-190">Lync Main Window Updates</span></span>

<span data-ttu-id="9581a-191">La nouvelle apparence rationalisée conserve des fonctionnalités familières telles que le champ de note **Activités du jour**, le sélecteur de statut et le sélecteur **Définir votre emplacement**.</span><span class="sxs-lookup"><span data-stu-id="9581a-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="9581a-192">Lorsque les salles de conversation sont activées, les utilisateurs voient une nouvelle icône de salle de **conversation** sur la page principale de Lync.</span><span class="sxs-lookup"><span data-stu-id="9581a-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="9581a-193">Avec l’icône **Salles de conversation**, les utilisateurs peuvent accéder rapidement à leurs salles de conversation et à leurs filtres.</span><span class="sxs-lookup"><span data-stu-id="9581a-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="9581a-194">Les utilisateurs peuvent cliquer sur les icônes de vue pour passer à la vue **Contacts**, **Salles de conversation**, **Conversations** ou **Téléphone**.</span><span class="sxs-lookup"><span data-stu-id="9581a-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="9581a-195">Si les utilisateurs ont été migrés vers Exchange 2013, ils peuvent télécharger une image haute résolution.</span><span class="sxs-lookup"><span data-stu-id="9581a-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="9581a-196">Mises à jour apportées à la vue Contacts et aux cartes de visite</span><span class="sxs-lookup"><span data-stu-id="9581a-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="9581a-197">Lync 2013 offre aux utilisateurs différentes façons d’afficher les contacts et les groupes dans leur affichage **contacts** .</span><span class="sxs-lookup"><span data-stu-id="9581a-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="9581a-198">Avec le nouveau magasin de contacts unifié, après la migration des contacts Lync des utilisateurs vers Exchange 2013, les utilisateurs peuvent accéder à leurs contacts et les gérer à partir de Lync 2013, Outlook ou Outlook Web App, et leurs favoris restent synchronisés.</span><span class="sxs-lookup"><span data-stu-id="9581a-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="9581a-199">Par exemple, si un utilisateur ajoute un contact aux favoris dans Outlook, le contact apparaît dans le groupe favoris de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9581a-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="9581a-200">Si vous avez ajouté et configuré le proxy XMPP et la passerelle XMPP, les utilisateurs peuvent ajouter des contacts de partenaires basés sur XMPP pour la messagerie instantanée et la présence.</span><span class="sxs-lookup"><span data-stu-id="9581a-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="9581a-201">La nouvelle fonctionnalité **Ajouter un contact qui ne fait pas partie de ma société** offre aux utilisateurs un moyen facile d’ajouter des personnes externes à l’organisation.</span><span class="sxs-lookup"><span data-stu-id="9581a-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="9581a-202">Le nouveau groupe **Favoris** permet aux utilisateurs de créer une liste de personnes qu’ils contactent le plus souvent pour un accès plus rapide.</span><span class="sxs-lookup"><span data-stu-id="9581a-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="9581a-p120">Les utilisateurs peuvent utiliser la nouvelle page d’options **Liste de contacts** pour choisir la façon dont les utilisateurs souhaitent trier et afficher les contacts. Les utilisateurs peuvent sélectionner une vue développée sur deux lignes qui montre les images des contacts ou une vue condensée sur une ligne. Les utilisateurs peuvent également trier les contacts par ordre alphabétique ou par disponibilité.</span><span class="sxs-lookup"><span data-stu-id="9581a-p120">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts. Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view. Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="9581a-206">Mises à jour apportées aux conférences</span><span class="sxs-lookup"><span data-stu-id="9581a-206">Conferencing Updates</span></span>

<span data-ttu-id="9581a-207">Lync 2013 offre plusieurs améliorations apportées aux fonctionnalités de conférence.</span><span class="sxs-lookup"><span data-stu-id="9581a-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="9581a-p121">Selon le type de réunion, les utilisateurs peuvent à présent désactiver le micro de l’audience et autoriser ou bloquer le partage vidéo lors de la planification de la réunion. Ces options sont disponibles dans la page **Options de la réunion** et sont recommandées pour les grandes réunions de plus de 20 participants.</span><span class="sxs-lookup"><span data-stu-id="9581a-p121">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting. These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="9581a-210">Des contrôles audio faciles à utiliser dans la salle de réunion permettent à l’utilisateur de contrôler les options audio, telles que l’activation du micro, la désactivation du micro, le changement de périphérique, etc.</span><span class="sxs-lookup"><span data-stu-id="9581a-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="9581a-211">Lors du partage de programmes, les utilisateurs peuvent sélectionner plusieurs programmes à partager s’ils ont besoin de travailler avec plus d’un programme.</span><span class="sxs-lookup"><span data-stu-id="9581a-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="9581a-212">Les utilisateurs peuvent à présent télécharger des présentations qui contiennent des clips vidéo en téléchargeant le fichier PowerPoint et en pointant la souris sur la diapositive pour afficher les contrôles vidéo (tels que Lire et Pause) et audio.</span><span class="sxs-lookup"><span data-stu-id="9581a-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="9581a-213">Au cours d’une réunion, les utilisateurs peuvent fusionner une autre conversation ouverte dans la réunion en sélectionnant **Fusionner cet appel dans** dans le menu **Autres options** (**...**).</span><span class="sxs-lookup"><span data-stu-id="9581a-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="9581a-214">Pour afficher le nom des participants, les utilisateurs peuvent pointer la souris sur le bouton **Afficher les participants** ou cliquer sur **Afficher la liste des participants** pour ancrer le volet à la réunion.</span><span class="sxs-lookup"><span data-stu-id="9581a-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="9581a-215">Selon le type de réunion, les utilisateurs ont le choix entre différentes vues du contenu et des participants.</span><span class="sxs-lookup"><span data-stu-id="9581a-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="9581a-p122">Les enregistrements de réunion sont automatiquement enregistrés dans un format compatible avec le Lecteur Windows Media (MP4). Les utilisateurs peuvent facilement partager le fichier avec d’autres personnes ou utiliser la fonctionnalité **Publier** dans le Gestionnaire d’enregistrements pour publier l’enregistrement dans un emplacement partagé.</span><span class="sxs-lookup"><span data-stu-id="9581a-p122">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4). Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="9581a-p123">OneNote offre de nouvelles façons de collaborer dans une réunion. Au cours d’une réunion, les utilisateurs peuvent prendre des notes avec OneNote pour un usage personnel après la réunion, ou utiliser des blocs-notes partagés et les modifier en collaboration avec les participants en temps réel. Tous les membres de l’équipe peuvent accéder aux notes partagées pour contribuer aux informations, échanger des idées ou utiliser les pages du bloc-notes comme tableau blanc virtuel. Les personnes et le contenu partagés dans la réunion sont automatiquement ajoutés aux notes.</span><span class="sxs-lookup"><span data-stu-id="9581a-p123">OneNote enables new ways to collaborate in a meeting. During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time. All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard. People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="9581a-p124">Les utilisateurs peuvent basculer entre les types de contenu à l’aide de l’option **Partager du contenu et mener des activités de réunion** en bas de la salle de réunion. Les utilisateurs peuvent également utiliser le menu **Gérer le contenu à présenter** pour choisir le contenu à partager.</span><span class="sxs-lookup"><span data-stu-id="9581a-p124">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room. Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9581a-224">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9581a-224">See Also</span></span>


[<span data-ttu-id="9581a-225">Planification des clients dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9581a-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

