---
title: Configuration de la présence dans Skype Entreprise Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: ce59ac0b-8115-4c6b-8174-e3aef982d3cb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- O365P_OnlinePresenceDesc
description: 'Découvrez comment configurer des Skype Entreprise vous pouvez voir la disponibilité de vos collègues. '
ms.openlocfilehash: 5eec57f295dbb45649fea6590147798881297a1b
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239964"
---
# <a name="configure-presence-in-skype-for-business-online"></a><span data-ttu-id="4d13a-103">Configuration de la présence dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4d13a-103">Configure presence in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="4d13a-104">Le Microsoft Teams d’administration a remplacé Skype Entreprise centre d’administration principal (portail hérité).</span><span class="sxs-lookup"><span data-stu-id="4d13a-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="4d13a-105">Tous les paramètres de gestion des Skype Entreprise sont désormais dans le Centre Teams’administration.</span><span class="sxs-lookup"><span data-stu-id="4d13a-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="4d13a-106">Le rôle d’administrateur [Azure AD](/azure/active-directory/roles/permissions-reference) de l’administrateur global ou de l’administrateur de Skype Entreprise vous doit être attribué pour gérer les fonctionnalités de gestion des Skype Entreprise dans le Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="4d13a-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="4d13a-107">Pour plus d’informations, consultez [Gérer les paramètres de Skype Entreprise dans le centre d’administration Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="4d13a-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="4d13a-108">Par défaut, les personnes qui peuvent communiquer avec l’une des personnes de votre organisation à l’aide de Skype Entreprise peuvent également voir si cette personne est en ligne.</span><span class="sxs-lookup"><span data-stu-id="4d13a-108">By default, anyone who can communicate with one of the people in your organization using Skype for Business can also see whether that person is online.</span></span> <span data-ttu-id="4d13a-109">Skype Entreprise indique si une personne est disponible en ligne, en réunion, hors connexion ou si elle présente un autre indicateur.</span><span class="sxs-lookup"><span data-stu-id="4d13a-109">Skype for Business shows whether a person is available online, in a meeting, offline, or another indicator.</span></span>

![Exemple de statut de ligne d’une personne dans Skype Entreprise.](../images/f0849132-1ddb-480f-bca6-cfe9eaa0486d.png)

<span data-ttu-id="4d13a-111">En tant **[qu’administrateur](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** pour tous les utilisateurs de votre entreprise, vous pouvez choisir qui voit leur présence en ligne dans Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="4d13a-111">As the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for everyone in your business, you can choose who sees their online presence in Skype for Business.</span></span>

<span data-ttu-id="4d13a-112">![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**</span><span class="sxs-lookup"><span data-stu-id="4d13a-112">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="4d13a-113">Allez dans le Centre d’administration > **centres d’administration**  >  **Skype Entreprise.**</span><span class="sxs-lookup"><span data-stu-id="4d13a-113">Go to the admin center > **Admin centers** > **Skype for Business**.</span></span>

2. <span data-ttu-id="4d13a-114">Dans la Skype Entreprise **d’administration,** sélectionnez **organisation.**</span><span class="sxs-lookup"><span data-stu-id="4d13a-114">In the **Skype for Business admin center**, choose **organization**.</span></span>

3. <span data-ttu-id="4d13a-115">Sous **le mode de confidentialité de** la présence, sélectionnez l’un des paramètres suivants, puis sélectionnez **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="4d13a-115">Under **presence privacy mode**, select one of the following settings, and then choose **Save**.</span></span>

|<span data-ttu-id="4d13a-116">**Paramètres**</span><span class="sxs-lookup"><span data-stu-id="4d13a-116">**Setting**</span></span>|<span data-ttu-id="4d13a-117">**Qui peut afficher la présence d’un utilisateur**</span><span class="sxs-lookup"><span data-stu-id="4d13a-117">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4d13a-118">**Afficher automatiquement des informations de présence**</span><span class="sxs-lookup"><span data-stu-id="4d13a-118">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="4d13a-119">Tout Skype Entreprise utilisateur dans votre entreprise qui n’a pas  été  ajouté à la liste externe ou bloquée d’une personne pourra voir sa présence en ligne.</span><span class="sxs-lookup"><span data-stu-id="4d13a-119">Any Skype for Business user in your business who has not been added to a person's **External** or **Blocked** list will be able to see that person's online presence.</span></span> <br/> |
|<span data-ttu-id="4d13a-120">**Afficher les informations de présence uniquement aux contacts d’un utilisateur**</span><span class="sxs-lookup"><span data-stu-id="4d13a-120">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="4d13a-121">Toute personne dans la liste des contacts d’une personne qu’elle n’a pas ajoutée à **sa** liste externe **ou bloquée.**</span><span class="sxs-lookup"><span data-stu-id="4d13a-121">Anyone in a person's Contacts list who they have not added to their **External** or **Blocked** list.</span></span> <br/> <span data-ttu-id="4d13a-122">Les individus peuvent remplacer vos paramètres par défaut dans leur application Skype Entreprise **:** Paramètres  >  **Options**  >  **outils.**</span><span class="sxs-lookup"><span data-stu-id="4d13a-122">Individuals can override your default settings in their Skype for Business app: **Settings** > **Tools** > **Options**.</span></span> <br/> |

<span data-ttu-id="4d13a-123">Pour plus d’informations sur les changements que vos utilisateurs peuvent Skype Entreprise, consultez les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="4d13a-123">For information about what your users can change in Skype for Business, see these articles:</span></span>

- [<span data-ttu-id="4d13a-124">Contrôler l’accès à vos informations de présence dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="4d13a-124">Control access to your presence information in Skype for Business</span></span>](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)

- [<span data-ttu-id="4d13a-125">Définir les options d’état dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="4d13a-125">Set Status options in Skype for Business</span></span>](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)

## <a name="related-topics"></a><span data-ttu-id="4d13a-126">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="4d13a-126">Related topics</span></span>

[<span data-ttu-id="4d13a-127">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4d13a-127">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="4d13a-128">Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype</span><span class="sxs-lookup"><span data-stu-id="4d13a-128">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
