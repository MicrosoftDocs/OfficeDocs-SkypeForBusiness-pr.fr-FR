---
title: Configuration de la réunion création d’un nouveau ou modification existante
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: Les paramètres de configuration de réunion définissent la participation des utilisateurs pour les conférences planifiées par des utilisateurs. Ces paramètres ne concernent que les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option Conférence maintenant du client.
ms.openlocfilehash: ce94eff347d4cbae35d78ced44873e8164abe0d5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691399"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="ab02d-105">Configuration de la réunion : création d’une réunion ou modification d’une réunion existante</span><span class="sxs-lookup"><span data-stu-id="ab02d-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="ab02d-p102">Les paramètres de configuration de réunion définissent la participation des utilisateurs pour les conférences planifiées par des utilisateurs. Ces paramètres ne concernent que les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option **Conférence maintenant** du client.</span><span class="sxs-lookup"><span data-stu-id="ab02d-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="ab02d-109">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="ab02d-109">UI Reference</span></span>

<span data-ttu-id="ab02d-110">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="ab02d-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="ab02d-111">**Scope** Identifie l’étendue de la configuration de réunion que vous créez ou modifiez : global, site ou pool.</span><span class="sxs-lookup"><span data-stu-id="ab02d-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="ab02d-112">**Nom** Les configurations de réunion sont nommées par défaut et le nom ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="ab02d-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="ab02d-113">**Appel RTC-salle d’attente** Activez cette case à cocher pour admettre automatiquement les utilisateurs qui se connectent à la Conférence par le biais d’une ligne téléphonique PSTN (réseau téléphonique commuté).</span><span class="sxs-lookup"><span data-stu-id="ab02d-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="ab02d-114">Désactivez cette case à cocher pour acheminer les appelants PSTN vers la salle d’attente, où ils sont en attente jusqu’à ce qu’un présentateur de conférence leur accorde l’accès à la Conférence.</span><span class="sxs-lookup"><span data-stu-id="ab02d-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="ab02d-115">**Désigner comme présentateur** Sélectionnez la catégorie d’utilisateurs (en plus de l’organisateur de la réunion) qui sont automatiquement désignés comme présentateurs lorsqu’ils rejoignent une conférence.</span><span class="sxs-lookup"><span data-stu-id="ab02d-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="ab02d-116">Quels que soient les paramètres de ce paramètre, les présentateurs peuvent être désignés explicitement comme présentateurs lorsque la Conférence est planifiée, ou être promues explicitement au présentateur lors de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="ab02d-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="ab02d-117">Les options disponibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="ab02d-117">The options are:</span></span>

  - <span data-ttu-id="ab02d-118">**Aucun** Sélectionnez cette option si personne autre que l’organisateur n’est désigné automatiquement comme présentateur.</span><span class="sxs-lookup"><span data-stu-id="ab02d-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="ab02d-119">**Société** Sélectionnez cette option pour désigner automatiquement seuls les membres de votre organisation comme présentateurs.</span><span class="sxs-lookup"><span data-stu-id="ab02d-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="ab02d-120">**Tout le monde** Sélectionnez cette option pour désigner automatiquement tout le monde devant être présentateur.</span><span class="sxs-lookup"><span data-stu-id="ab02d-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="ab02d-121">**Type de conférence affecté par défaut** Ce paramètre détermine si le complément de conférence Outlook planifie toujours des conférences à l’aide de la Conférence affectée à l’organisateur, ce qui signifie que les conférences planifiées ont toujours les mêmes URL et informations audio.</span><span class="sxs-lookup"><span data-stu-id="ab02d-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="ab02d-122">Activez cette case à cocher pour que les conférences planifiées utilisent toujours la même URL de jointure.</span><span class="sxs-lookup"><span data-stu-id="ab02d-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="ab02d-123">Désactivez cette case à cocher pour utiliser une autre URL de jointure pour chaque conférence.</span><span class="sxs-lookup"><span data-stu-id="ab02d-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="ab02d-124">**Admettre les utilisateurs anonymes par défaut** Activez cette case à cocher si les utilisateurs anonymes (non authentifiés) peuvent participer par défaut aux conférences.</span><span class="sxs-lookup"><span data-stu-id="ab02d-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="ab02d-125">Désactivez cette case à cocher si les utilisateurs anonymes ne peuvent pas participer par défaut aux conférences.</span><span class="sxs-lookup"><span data-stu-id="ab02d-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="ab02d-126">**URL du logo** Tapez l’URL contenant l’image à utiliser pour les invitations aux conférences personnalisées.</span><span class="sxs-lookup"><span data-stu-id="ab02d-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="ab02d-127">**URL de l’aide** Tapez l’URL d’un site Web dans lequel les utilisateurs peuvent obtenir de l’aide pour joindre la Conférence.</span><span class="sxs-lookup"><span data-stu-id="ab02d-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="ab02d-128">**URL de texte légal** Tapez l’URL d’un site Web contenant les informations juridiques et les exclusions de responsabilité pour la Conférence.</span><span class="sxs-lookup"><span data-stu-id="ab02d-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="ab02d-129">**Texte de pied de page personnalisé** Entrez le texte à utiliser pour les invitations aux conférences personnalisées.</span><span class="sxs-lookup"><span data-stu-id="ab02d-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="ab02d-p107">Pour plus d’informations sur l’utilisation des configurations de réunion, reportez-vous à la rubrique [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) de la documentation des opérations. Pour plus d’informations sur la définition de configurations de réunion pour des réunions importantes, reportez-vous à la rubrique [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) de la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="ab02d-p107">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation. For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


