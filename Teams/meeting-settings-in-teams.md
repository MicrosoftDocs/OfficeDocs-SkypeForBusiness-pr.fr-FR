---
title: Gérer les paramètres de réunion dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.overview
MS.collection: Teams_ITAdmin_Help
description: Découvrez comment gérer les paramètres pour les réunions d’équipes qui planifient des utilisateurs dans votre organisation.
ms.openlocfilehash: e4eba5f585f7621add95101d06194bebead507e2
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754416"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="cff2c-103">Gérer les paramètres de réunion dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cff2c-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="cff2c-104">En tant qu’administrateur, vous utilisez les paramètres de réunion équipes pour contrôler si les utilisateurs anonymes peuvent participer à des réunions d’équipes, personnaliser les invitations aux réunions et si vous souhaitez activer la qualité de Service (QoS), définir les ports pour le trafic en temps réel.</span><span class="sxs-lookup"><span data-stu-id="cff2c-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set ports for real-time traffic.</span></span> <span data-ttu-id="cff2c-105">Ces paramètres s’appliquent à toutes les réunions d’équipes cette planification, les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cff2c-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="cff2c-106">Vous gérer ces paramètres à partir de **réunions** > **paramètres de réunion** dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cff2c-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span> 

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="cff2c-107">Autoriser les utilisateurs anonymes à participer à des réunions</span><span class="sxs-lookup"><span data-stu-id="cff2c-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="cff2c-108">Avec la participation anonyme, tout le monde peut joindre la réunion en tant qu’utilisateur anonyme en cliquant sur le lien dans l’invitation à la réunion.</span><span class="sxs-lookup"><span data-stu-id="cff2c-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span> 

<span data-ttu-id="cff2c-109">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**</span><span class="sxs-lookup"><span data-stu-id="cff2c-109">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
1. <span data-ttu-id="cff2c-110">Dans la navigation de gauche, accédez à des **réunions** > **paramètres de réunion**.</span><span class="sxs-lookup"><span data-stu-id="cff2c-110">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span> 
2. <span data-ttu-id="cff2c-111">Sous **Participants**, activez **les utilisateurs anonymes peuvent participer à une réunion**.</span><span class="sxs-lookup"><span data-stu-id="cff2c-111">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span> 

    <span data-ttu-id="cff2c-112">![réunion-paramètres-participants.png] (media/meeting-settings-participants.png "Capture d’écran des paramètres des participants pour les réunions d’équipes dans le centre d’administration Microsoft équipes")</span><span class="sxs-lookup"><span data-stu-id="cff2c-112">![meeting-settings-participants.png](media/meeting-settings-participants.png "Screen shot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

<span data-ttu-id="cff2c-113">Si vous ne voulez pas que les utilisateurs anonymes à participer à des réunions planifiées par les utilisateurs de votre organisation, désactivez ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="cff2c-113">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span> 

## <a name="customize-meeting-invitations"></a><span data-ttu-id="cff2c-114">Personnaliser les invitations aux réunions</span><span class="sxs-lookup"><span data-stu-id="cff2c-114">Customize meeting invitations</span></span>

<span data-ttu-id="cff2c-115">Vous pouvez personnaliser les invitations à des équipes pour répondre aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="cff2c-115">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="cff2c-116">Vous pouvez ajouter le logo de votre organisation et inclure des informations utiles, telles que des liens vers votre site Web de support et exclusion de responsabilité et un pied de page en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="cff2c-116">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span> 

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="cff2c-117">Conseils pour la création d’un logo pour les invitations aux réunions</span><span class="sxs-lookup"><span data-stu-id="cff2c-117">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="cff2c-118">Créer une image qui n’est pas plus de 188 pixels de large par 30 pixels de haut (il s’agit très petite).</span><span class="sxs-lookup"><span data-stu-id="cff2c-118">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span> 
2. <span data-ttu-id="cff2c-119">Enregistrez l’image au format JPG.</span><span class="sxs-lookup"><span data-stu-id="cff2c-119">Save the image in JPG format.</span></span> 
3. <span data-ttu-id="cff2c-120">Stocker l’image dans un emplacement central tout le monde dans votre organisation permettre accéder, par exemple un partage réseau.</span><span class="sxs-lookup"><span data-stu-id="cff2c-120">Store the image in a central location that everyone in your organization can access, such as a network share.</span></span> 

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="cff2c-121">Personnaliser vos invitations aux réunions</span><span class="sxs-lookup"><span data-stu-id="cff2c-121">Customize your meeting invitations</span></span>

<span data-ttu-id="cff2c-122">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**</span><span class="sxs-lookup"><span data-stu-id="cff2c-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="cff2c-123">Dans la navigation de gauche, accédez à des **réunions** > **paramètres de réunion**.</span><span class="sxs-lookup"><span data-stu-id="cff2c-123">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="cff2c-124">Sous **invitation par courrier électronique**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="cff2c-124">Under **Email invitation**, do the following:</span></span> 

    <span data-ttu-id="cff2c-125">![réunion-paramètres-invitation.png] (media/meeting-settings-invitation.png "Capture d’écran de la réunion paramètres de l’invitation que vous pouvez personnaliser pour les réunions des équipes")</span><span class="sxs-lookup"><span data-stu-id="cff2c-125">![meeting-settings-invitation.png](media/meeting-settings-invitation.png "Screen shot of the meeting invitation settings that you can customize for Teams meetings")</span></span> 

    - <span data-ttu-id="cff2c-126">**URL du logo** Entrez l’URL où est stockée votre logo.</span><span class="sxs-lookup"><span data-stu-id="cff2c-126">**Logo URL** Enter the URL where your logo is stored.</span></span> 
    - <span data-ttu-id="cff2c-127">**URL juridique** Si votre organisation dispose d’un site Web juridique que vous souhaitez communiquer à atteindre pour n’importe quel des implications juridiques, entrez l’URL ici.</span><span class="sxs-lookup"><span data-stu-id="cff2c-127">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span> 
    - <span data-ttu-id="cff2c-128">**URL de l’aide** Si votre organisation dispose d’un site Web que vous souhaitez atteindre en cas de problèmes de personnes, entrez l’URL ici.</span><span class="sxs-lookup"><span data-stu-id="cff2c-128">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="cff2c-129">**Pied de page** Entrez le texte que vous souhaitez inclure dans le pied de page.</span><span class="sxs-lookup"><span data-stu-id="cff2c-129">**Footer** Enter text that you want to include as a footer.</span></span> 
3. <span data-ttu-id="cff2c-130">Attendez une heure pour propager les modifications.</span><span class="sxs-lookup"><span data-stu-id="cff2c-130">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="cff2c-131">Planifier une réunion équipes pour afficher un aperçu de l’invitation à la réunion.</span><span class="sxs-lookup"><span data-stu-id="cff2c-131">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="cff2c-132">Définir la manière dont vous souhaitez gérer le trafic multimédia en temps réel pour les réunions d’équipes</span><span class="sxs-lookup"><span data-stu-id="cff2c-132">Set how you want to handle real-time media traffic for Teams meetings</span></span>
<span data-ttu-id="cff2c-133">Si vous utilisez la qualité de Service (QoS) pour définir la priorité du trafic réseau, vous pouvez activer les indicateurs de qualité de service et vous pouvez définir des plages de ports pour chaque type de trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="cff2c-133">If you're using Quality of Service (QoS) to prioritize network traffic, you can enable QoS markers and you can set port ranges for each type of media traffic.</span></span> 

 <span data-ttu-id="cff2c-134">![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**</span><span class="sxs-lookup"><span data-stu-id="cff2c-134">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="cff2c-135">Dans la navigation de gauche, accédez à des **réunions** > **paramètres de réunion**.</span><span class="sxs-lookup"><span data-stu-id="cff2c-135">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span> 
2. <span data-ttu-id="cff2c-136">Sous **réseau**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="cff2c-136">Under **Network**, do the following:</span></span>

    <span data-ttu-id="cff2c-137">![réunion-paramètres-network.png] (media/meeting-settings-network.png "Capture d’écran des paramètres du réseau pour les réunions d’équipes dans le centre d’administration Microsoft équipes")</span><span class="sxs-lookup"><span data-stu-id="cff2c-137">![meeting-settings-network.png](media/meeting-settings-network.png "Screen shot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="cff2c-138">Pour activer les indicateurs de qualité de service, activer **marqueurs insérer qualité de Service (QoS) pour le trafic multimédia en temps réel**.</span><span class="sxs-lookup"><span data-stu-id="cff2c-138">To enable QoS markers, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span>
    - <span data-ttu-id="cff2c-139">Pour spécifier les plages de ports, en regard de **Sélectionner une plage de ports pour chaque type de trafic multimédia en temps réel**, sélectionnez **spécifier les plages de ports**, puis entrez les ports de départ et de fin pour l’audio, vidéo et partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="cff2c-139">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> 
    
        <span data-ttu-id="cff2c-140">Si vous choisissez **d’utiliser automatiquement les ports disponibles**, les ports disponibles entre 1024 et 65535 sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="cff2c-140">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> 

 ### <a name="related-topics"></a><span data-ttu-id="cff2c-141">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="cff2c-141">Related topics</span></span>
- [<span data-ttu-id="cff2c-142">Qualité de Service (QoS) dans les équipes</span><span class="sxs-lookup"><span data-stu-id="cff2c-142">Quality of Service (QoS) in Teams</span></span>](qos-in-teams.md)

