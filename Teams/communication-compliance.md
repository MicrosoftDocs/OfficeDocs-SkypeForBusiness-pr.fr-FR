---
title: Conformité des communications avec les Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Learning la conformité des communications, qui fait partie du jeu de solutions de risque Insider, du point de vue Microsoft Teams (cela fait partie de la fonctionnalité de conformité des communications M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5957e8900a9b3d9915a88e3ad8bf5e18c7a08b3
ms.sourcegitcommit: d77104d5606ff93a792e8712d6c7780ae247b536
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2021
ms.locfileid: "53126900"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="5a17d-103">Conformité des communications avec les Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5a17d-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="5a17d-104">La conformité des communications est une solution à risque au niveau du Microsoft 365 qui permet de minimiser les risques de communication en vous aidant à détecter, capturer et agir sur les messages inappropriés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5a17d-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="5a17d-105">Par Microsoft Teams, la conformité des communications permet d’identifier les [types](/microsoft-365/compliance/communication-compliance-feature-reference) de contenus inappropriés suivants dans les canaux Teams, les canaux de Teams privés ou dans les conversations en tête-à-tête et de groupe :</span><span class="sxs-lookup"><span data-stu-id="5a17d-105">For Microsoft Teams, communication compliance helps identify the [following types](/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels, Private Teams channels, or in 1:1 and group chats:</span></span>

- <span data-ttu-id="5a17d-106">Langage choquant, choquant et choquant</span><span class="sxs-lookup"><span data-stu-id="5a17d-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="5a17d-107">Images pour adultes, racy et gory</span><span class="sxs-lookup"><span data-stu-id="5a17d-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="5a17d-108">Partage d’informations sensibles</span><span class="sxs-lookup"><span data-stu-id="5a17d-108">Sharing of sensitive information</span></span>

<span data-ttu-id="5a17d-109">Pour plus d’informations sur la conformité des communications et la configuration des stratégies pour votre organisation, consultez la conformité des communications [dans Microsoft 365.](/microsoft-365/compliance/communication-compliance)</span><span class="sxs-lookup"><span data-stu-id="5a17d-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="5a17d-110">Comment utiliser la conformité des communications dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5a17d-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="5a17d-111">La conformité et les Microsoft Teams communication sont étroitement intégrés et peuvent contribuer à minimiser les risques de communication dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5a17d-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="5a17d-112">Après avoir configuré vos premières stratégies de conformité aux communications, vous pouvez gérer activement les messages Microsoft Teams et le contenu signalés automatiquement par des alertes.</span><span class="sxs-lookup"><span data-stu-id="5a17d-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="5a17d-113">Prise en main</span><span class="sxs-lookup"><span data-stu-id="5a17d-113">Getting started</span></span>

<span data-ttu-id="5a17d-114">La mise en place de la conformité [](/microsoft-365/compliance/communication-compliance-plan) des communications dans Microsoft Teams commence par la planification et la création de stratégies prédéfinées ou personnalisées permettant d’identifier les activités inappropriées des utilisateurs dans les canaux Teams ou dans les groupes et les deux: 1.</span><span class="sxs-lookup"><span data-stu-id="5a17d-114">Getting started with communication compliance in Microsoft Teams begins with [planning](/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="5a17d-115">N’oubliez pas que [](/microsoft-365/compliance/communication-compliance-configure) vous devez configurer certaines autorisations et conditions préalables de base dans le cadre du processus de configuration.</span><span class="sxs-lookup"><span data-stu-id="5a17d-115">Keep in mind that you'll need to [configure](/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="5a17d-116">Teams administrateurs peuvent configurer des stratégies de conformité des communications aux niveaux suivants :</span><span class="sxs-lookup"><span data-stu-id="5a17d-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="5a17d-117">**Niveau utilisateur**: les stratégies de ce niveau s’appliquent à Teams utilisateur individuel ou peuvent être appliquées à tous Teams utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5a17d-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="5a17d-118">Ces stratégies couvrent les messages que ces utilisateurs peuvent envoyer dans des conversations à deux ou de groupe.</span><span class="sxs-lookup"><span data-stu-id="5a17d-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="5a17d-119">Les communications de conversation pour les utilisateurs sont automatiquement contrôlées dans toutes les Microsoft Teams où les utilisateurs en sont membres.</span><span class="sxs-lookup"><span data-stu-id="5a17d-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="5a17d-120">**Teams niveaux :** les stratégies de ce niveau s’appliquent à un canal Microsoft Team, y compris à un canal privé.</span><span class="sxs-lookup"><span data-stu-id="5a17d-120">**Teams level**: Policies at this level apply to a Microsoft Team channel, including a Private channel.</span></span> <span data-ttu-id="5a17d-121">Ces stratégies couvrent les messages envoyés dans Teams canal uniquement.</span><span class="sxs-lookup"><span data-stu-id="5a17d-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="5a17d-122">Agir sur les messages inappropriés dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5a17d-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="5a17d-123">Après avoir configuré vos stratégies et reçu des alertes de conformité aux communications pour les messages Microsoft Teams, les réviseurs de la conformité de votre organisation doivent agir sur ces messages.</span><span class="sxs-lookup"><span data-stu-id="5a17d-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="5a17d-124">Les réviseurs peuvent vous aider à protéger votre organisation en filant les alertes de conformité aux communications et en supprimant les messages marqués d’un Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5a17d-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![Supprimer un message dans Teams](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="5a17d-126">Les messages et le contenu supprimés sont remplacés par des notifications pour les utilisateurs qui leur expliquent que le message ou le contenu a été supprimé et quelle stratégie est applicable à la suppression.</span><span class="sxs-lookup"><span data-stu-id="5a17d-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="5a17d-127">L’expéditeur du message ou du contenu supprimé est également informé de l’état de suppression et fournit le contenu du message d’origine pour le contexte relatif à sa suppression.</span><span class="sxs-lookup"><span data-stu-id="5a17d-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="5a17d-128">L’expéditeur peut également afficher la condition de stratégie spécifique qui s’applique à la suppression du message.</span><span class="sxs-lookup"><span data-stu-id="5a17d-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="5a17d-129">Exemple de conseil de stratégie vu par l’expéditeur :</span><span class="sxs-lookup"><span data-stu-id="5a17d-129">Example of policy tip seen by sender:</span></span>

![Conseil de stratégie pour l’expéditeur](./media/communication-compliance-warning-1.png)

<span data-ttu-id="5a17d-131">Exemple de notification de condition de stratégie vu par l’expéditeur :</span><span class="sxs-lookup"><span data-stu-id="5a17d-131">Example of policy condition notification seen by the sender:</span></span>

![Informations sur les conditions de stratégie de l’expéditeur](./media/communication-compliance-warning-2.png)

<span data-ttu-id="5a17d-133">Exemple de conseil de stratégie vu par le destinataire :</span><span class="sxs-lookup"><span data-stu-id="5a17d-133">Example of policy tip seen by recipient:</span></span>

![Conseil de stratégie pour le destinataire](./media/communication-compliance-warning-3.png)