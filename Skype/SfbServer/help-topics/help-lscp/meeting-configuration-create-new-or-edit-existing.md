---
title: Configuration de la réunion, créer ou modifier une existante
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: Les paramètres de configuration de réunion définissent la participation des utilisateurs pour les conférences planifiées par des utilisateurs. Ces paramètres ne concernent que les réunions planifiées. Elles ne s’appliquent pas à des réunions ad hoc créées en cliquant sur l’option Conférence maintenant dans le client.
ms.openlocfilehash: af9a1cca6a34320a7e2bd2ba53b08040351f784e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="616e1-105">Configuration de la réunion : création d’une réunion ou modification d’une réunion existante</span><span class="sxs-lookup"><span data-stu-id="616e1-105">Meeting Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="616e1-p102">Les paramètres de configuration de réunion définissent la participation des utilisateurs pour les conférences planifiées par des utilisateurs. Ces paramètres ne concernent que les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option **Conférence maintenant** du client.</span><span class="sxs-lookup"><span data-stu-id="616e1-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="616e1-109">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="616e1-109">UI Reference</span></span>

<span data-ttu-id="616e1-110">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="616e1-110">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="616e1-111">**Champ d’application** Identifie la portée de la configuration de la réunion que vous créez ou modifiez : global, site, ou le pool.</span><span class="sxs-lookup"><span data-stu-id="616e1-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>
    
- <span data-ttu-id="616e1-112">**Nom** Configurations de réunion sont nommées par défaut, et le nom ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="616e1-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>
    
- <span data-ttu-id="616e1-113">**Les appelants RTPC contournent la salle d’attente** Activez cette case à cocher d’admettre automatiquement les utilisateurs qui sont connectent à la conférence via une ligne téléphonique du réseau téléphonique public commuté.</span><span class="sxs-lookup"><span data-stu-id="616e1-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="616e1-114">Désactivez cette case à cocher aux appelants de RTPC d’itinéraire à la salle de conférence, où qu’ils se trouvent sur Maintenez jusqu'à ce qu’un présentateur de la conférence leur accorde l’accès à la conférence.</span><span class="sxs-lookup"><span data-stu-id="616e1-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>
    
- <span data-ttu-id="616e1-115">**Désigner en tant que présentateur** Sélectionnez la catégorie d’utilisateurs sont automatiquement désigné en tant que présentateurs lorsqu’ils rejoignent une conférence (en plus de l’organisateur de la réunion).</span><span class="sxs-lookup"><span data-stu-id="616e1-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="616e1-116">Indépendamment de ce paramètre, les présentateurs peuvent être explicitement désignés en tant que présentateurs lors de la conférence est planifiée, ou ils peuvent être promus explicitement au présentateur au cours de la conférence.</span><span class="sxs-lookup"><span data-stu-id="616e1-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="616e1-117">Les options sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="616e1-117">The options are:</span></span>
    
  - <span data-ttu-id="616e1-118">**Aucun** Sélectionnez cette option si la personne que l’organisateur est automatiquement désigné en tant que présentateur.</span><span class="sxs-lookup"><span data-stu-id="616e1-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>
    
  - <span data-ttu-id="616e1-119">**Société** Sélectionnez cette option pour désigner automatiquement uniquement les membres de votre organisation en tant que présentateurs.</span><span class="sxs-lookup"><span data-stu-id="616e1-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>
    
  - <span data-ttu-id="616e1-120">**Tout le monde** Sélectionnez cette option pour désigner automatiquement tous les utilisateurs d’être un présentateur.</span><span class="sxs-lookup"><span data-stu-id="616e1-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>
    
- <span data-ttu-id="616e1-121">**Type de conférence attribué par défaut** Ce paramètre contrôle si le complément de conférence Outlook planifie toujours les conférences à l’aide de l’organisateur affecté de conférence, qui signifie que prévu des conférences toujours ont la même URL de jointure et les informations audio.</span><span class="sxs-lookup"><span data-stu-id="616e1-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="616e1-122">Activez cette case à cocher pour que les conférences planifiées à toujours utiliser la même URL de jointure.</span><span class="sxs-lookup"><span data-stu-id="616e1-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="616e1-123">Désactivez cette case à cocher pour utiliser une URL de jointure différente pour chaque conférence.</span><span class="sxs-lookup"><span data-stu-id="616e1-123">Clear this check box to use a different join URL for each conference.</span></span>
    
- <span data-ttu-id="616e1-124">**Admit les utilisateurs anonymes par défaut** Activez cette case à cocher si anonyme (c'est-à-dire, non authentifié) les utilisateurs sont autorisés à participer à des conférences par défaut.</span><span class="sxs-lookup"><span data-stu-id="616e1-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="616e1-125">Désactivez cette case à cocher si les utilisateurs anonymes ne sont pas autorisés à participer à des conférences par défaut.</span><span class="sxs-lookup"><span data-stu-id="616e1-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>
    
- <span data-ttu-id="616e1-126">**URL du logo** Tapez l’URL contenant l’image à utiliser pour les invitations Conférence personnalisé.</span><span class="sxs-lookup"><span data-stu-id="616e1-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>
    
- <span data-ttu-id="616e1-127">**URL d’aide** Tapez l’URL d’un site Web où les utilisateurs peuvent obtenir une assistance pour joindre la conférence.</span><span class="sxs-lookup"><span data-stu-id="616e1-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>
    
- <span data-ttu-id="616e1-128">**URL de texte juridique** Tapez l’URL d’un site Web qui a les informations légales et limitation de responsabilité pour la conférence.</span><span class="sxs-lookup"><span data-stu-id="616e1-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>
    
- <span data-ttu-id="616e1-129">**Texte de pied de page personnalisé** Tapez le texte à utiliser sur les invitations Conférence personnalisé.</span><span class="sxs-lookup"><span data-stu-id="616e1-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>
    
<span data-ttu-id="616e1-130">Pour plus d’informations sur l’utilisation des configurations de réunion, reportez-vous à la section [créer un ou modifier une Collection de réunion Configuration paramètres](http://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) dans la documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="616e1-130">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](http://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span> <span data-ttu-id="616e1-131">Pour plus d’informations sur la définition de configurations de réunion pour les réunions de grande taille, consultez [Configuration de Support pour les réunions de grande taille](http://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="616e1-131">For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](http://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>
  

