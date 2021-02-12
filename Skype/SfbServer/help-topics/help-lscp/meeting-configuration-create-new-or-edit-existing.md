---
title: 'Configuration de réunion : création d’une réunion ou modification d’une configuration existante'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: Les paramètres de configuration de réunion définissent la participation des utilisateurs pour les conférences planifiées par des utilisateurs. Ces paramètres s’appliquent uniquement aux réunions planifiées. Elles ne s’appliquent pas aux réunions ad hoc créées en cliquant sur l’option Conférence maintenant dans le client.
ms.openlocfilehash: dc37e3d76a81a09fe2cbd2407f4d3a2dff3d703e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803934"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="caffe-105">Configuration de la réunion : création d’une nouvelle ou modification d’une configuration existante</span><span class="sxs-lookup"><span data-stu-id="caffe-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="caffe-106">Les paramètres de configuration de réunion définissent la participation des utilisateurs pour les conférences planifiées par des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="caffe-106">Meeting configuration settings define the user join experience for conferences scheduled by users.</span></span> <span data-ttu-id="caffe-107">Ces paramètres s’appliquent uniquement aux réunions planifiées.</span><span class="sxs-lookup"><span data-stu-id="caffe-107">These settings only apply to scheduled meetings.</span></span> <span data-ttu-id="caffe-108">Elles ne s’appliquent pas aux réunions ad hoc créées en cliquant sur l’option Conférence **maintenant** dans le client.</span><span class="sxs-lookup"><span data-stu-id="caffe-108">They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="caffe-109">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="caffe-109">UI Reference</span></span>

<span data-ttu-id="caffe-110">La liste suivante décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="caffe-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="caffe-111">**Étendue** Identifie l’étendue de la configuration de réunion que vous créez ou modifiez : globale, de site ou de pool.</span><span class="sxs-lookup"><span data-stu-id="caffe-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="caffe-112">**Nom** Les configurations de réunion sont nommées par défaut et le nom ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="caffe-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="caffe-113">**Les appelants PSTN contournent la salle d’entrée** Cochez cette case pour admettre automatiquement les utilisateurs qui appellent la conférence sur une ligne téléphonique du réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="caffe-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="caffe-114">Cochez cette case pour router les appelants PSTN vers la salle d’attente de conférence, où ils sont en attente jusqu’à ce qu’un présentateur de conférence leur donne accès à la conférence.</span><span class="sxs-lookup"><span data-stu-id="caffe-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="caffe-115">**Désigné comme présentateur** Sélectionnez la catégorie des utilisateurs (en plus de l’organisateur de la réunion) qui sont automatiquement désignés comme présentateurs lorsqu’ils rejoignent une conférence.</span><span class="sxs-lookup"><span data-stu-id="caffe-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="caffe-116">Quel que soit ce paramètre, les présentateurs peuvent être explicitement désignés comme présentateurs lorsque la conférence est programmée, ou ils peuvent être promus explicitement en tant que présentateurs au cours de la conférence.</span><span class="sxs-lookup"><span data-stu-id="caffe-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="caffe-117">Les options disponibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="caffe-117">The options are:</span></span>

  - <span data-ttu-id="caffe-118">**Aucun** Sélectionnez cette option si personne d’autre que l’organisateur n’est désigné automatiquement comme présentateur.</span><span class="sxs-lookup"><span data-stu-id="caffe-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="caffe-119">**Société** Sélectionnez cette option pour désigner automatiquement uniquement les membres de votre organisation comme présentateurs.</span><span class="sxs-lookup"><span data-stu-id="caffe-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="caffe-120">**Tout le monde** Sélectionnez cette option pour désigner automatiquement quiconque comme présentateur.</span><span class="sxs-lookup"><span data-stu-id="caffe-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="caffe-121">**Type de conférence affecté par défaut** Ce paramètre contrôle si le addin de conférence Outlook planifiera toujours des conférences à l’aide de la conférence attribuée par l’organisateur, ce qui signifie que les conférences programmées ont toujours la même URL de rejoindre et les mêmes informations audio.</span><span class="sxs-lookup"><span data-stu-id="caffe-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="caffe-122">Cochez cette case pour que les conférences programmées utilisent toujours la même URL de jointeur.</span><span class="sxs-lookup"><span data-stu-id="caffe-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="caffe-123">Cochez cette case pour utiliser une URL de jointeur différente pour chaque conférence.</span><span class="sxs-lookup"><span data-stu-id="caffe-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="caffe-124">**Admettre les utilisateurs anonymes par défaut** Cochez cette case si les utilisateurs anonymes (c’est-à-dire non authentifiés) sont autorisés à participer à des conférences par défaut.</span><span class="sxs-lookup"><span data-stu-id="caffe-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="caffe-125">Cochez cette case si les utilisateurs anonymes ne sont pas autorisés à participer aux conférences par défaut.</span><span class="sxs-lookup"><span data-stu-id="caffe-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="caffe-126">**URL du logo** Tapez l’URL qui possède l’image à utiliser pour les invitations aux conférences personnalisées.</span><span class="sxs-lookup"><span data-stu-id="caffe-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="caffe-127">**URL de l’aide** Tapez l’URL d’un site web où les utilisateurs peuvent obtenir de l’aide pour participer à la conférence.</span><span class="sxs-lookup"><span data-stu-id="caffe-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="caffe-128">**URL de texte légal** Tapez l’URL d’un site web qui dispose des informations légales et des clauses d’exclusion de responsabilité pour la conférence.</span><span class="sxs-lookup"><span data-stu-id="caffe-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="caffe-129">**Texte de pied de groupe personnalisé** Tapez le texte à utiliser sur les invitations aux conférences personnalisées.</span><span class="sxs-lookup"><span data-stu-id="caffe-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="caffe-130">Pour plus d’informations sur l’utilisation des configurations de réunion, voir [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="caffe-130">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span> <span data-ttu-id="caffe-131">Pour plus de détails sur la définition de configurations de réunion pour de grandes réunions, voir [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="caffe-131">For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


