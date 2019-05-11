---
title: Configuration de réunion créer ou modifier une existant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: Les paramètres de configuration de réunion définissent la participation des utilisateurs pour les conférences planifiées par des utilisateurs. Ces paramètres ne concernent que les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option Conférence maintenant du client.
ms.openlocfilehash: 05613fb9c8df89bb9c7efc5fe7bfced78ca12574
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891585"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="dbf4f-105">Configuration de la réunion : création d’une réunion ou modification d’une réunion existante</span><span class="sxs-lookup"><span data-stu-id="dbf4f-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="dbf4f-p102">Les paramètres de configuration de réunion définissent la participation des utilisateurs pour les conférences planifiées par des utilisateurs. Ces paramètres ne concernent que les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option **Conférence maintenant** du client.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="dbf4f-109">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="dbf4f-109">UI Reference</span></span>

<span data-ttu-id="dbf4f-110">La liste ci-dessous décrit les champs de la page.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="dbf4f-111">**Étendue** Identifie l’étendue de la configuration de réunion que vous créez ou modifiez : globale, site ou pool.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="dbf4f-112">**Nom** Configurations de réunion sont nommées par défaut et le nom ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="dbf4f-113">**Les appelants PSTN de contournement salle d’attente** Activez cette case à cocher Accepter automatiquement les utilisateurs qui sont connectent à la conférence sur la ligne téléphonique public commuté (PSTN) réseau.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="dbf4f-114">Désactivez cette case à cocher pour les appelants PSTN d’itinéraire à la salle d’attente de conférence, où ils se trouvent sur attente jusqu'à ce que le présentateur de la conférence les autorise à accéder à la conférence.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="dbf4f-115">**Désigner en tant que présentateur** Sélectionnez la catégorie d’utilisateurs sont automatiquement désigné en tant que présentateurs lorsqu’ils rejoignent une conférence (en plus de l’organisateur de la réunion).</span><span class="sxs-lookup"><span data-stu-id="dbf4f-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="dbf4f-116">Quel que soit ce paramètre, les présentateurs peuvent être explicitement désignés en tant que présentateurs lors de la conférence est planifiée, ou ils peuvent être promus explicitement au présentateur au cours de la conférence.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="dbf4f-117">Les options sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="dbf4f-117">The options are:</span></span>

  - <span data-ttu-id="dbf4f-118">**Aucun** Sélectionnez cette option si personne d’autre que l’organisateur est automatiquement désigné en tant que présentateur.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="dbf4f-119">**Société** Sélectionnez cette option pour désigner automatiquement uniquement les membres de votre organisation en tant que présentateurs.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="dbf4f-120">**Tout le monde** Sélectionnez cette option pour désigner automatiquement tout le monde à être présentateur.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="dbf4f-121">**Type de conférence affecté par défaut** Ce paramètre contrôle si le complément de conférence Outlook planifie toujours les conférences à l’aide de l’organisateur affecté conférence, ce qui signifie que planifiées toujours des conférences ont le même participer à une URL et les informations audio.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="dbf4f-122">Activez cette case à cocher pour que les conférences planifiées à toujours utiliser la même URL jointure.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="dbf4f-123">Désactivez cette case à cocher pour utiliser une URL de jointure différente pour chaque conférence.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="dbf4f-124">**Autoriser les utilisateurs anonymes par défaut** Activez cette case à cocher si anonyme (c'est-à-dire, non authentifié) les utilisateurs sont autorisés à participer à des conférences par défaut.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="dbf4f-125">Désactivez cette case à cocher si les utilisateurs anonymes ne sont pas autorisés à participer à des conférences par défaut.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="dbf4f-126">**URL du logo** Tapez l’URL qui se trouve l’image à utiliser pour les invitations de conférence personnalisées.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="dbf4f-127">**URL de l’aide** Tapez l’URL d’un site Web où les utilisateurs peuvent obtenir une assistance pour participer à la conférence.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="dbf4f-128">**URL légales** Tapez l’URL d’un site Web qui possède les informations légales et les clauses d’exclusion pour la conférence.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="dbf4f-129">**Texte de pied de page personnalisé** Tapez le texte à utiliser sur les invitations de conférence personnalisées.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="dbf4f-p107">Pour plus d’informations sur l’utilisation des configurations de réunion, reportez-vous à la rubrique [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) de la documentation des opérations. Pour plus d’informations sur la définition de configurations de réunion pour des réunions importantes, reportez-vous à la rubrique [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) de la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="dbf4f-p107">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation. For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


