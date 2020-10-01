---
title: Conformité de la communication avec Microsoft teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: En savoir plus sur la conformité des communications, qui fait partie de la solution de risque Insider de Microsoft Teams (incluse dans la fonctionnalité de conformité des communications M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb9400778b8e000a438343e74bc6b030087ff297
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328253"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="d5dc2-103">Conformité de la communication avec Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="d5dc2-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="d5dc2-104">Le respect de la communication est une solution de risque Insider dans Microsoft 365 qui permet de réduire les risques de communication en vous aidant à détecter, capturer et agir sur des messages inappropriés au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="d5dc2-105">Dans Microsoft Teams, la conformité de la communication permet d’identifier les types de contenus inappropriés [suivants](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) dans les canaux d’équipe ou dans 1:1 et les discussions de groupe :</span><span class="sxs-lookup"><span data-stu-id="d5dc2-105">For Microsoft Teams, communication compliance helps identify the [following types](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="d5dc2-106">Langage injurieux, profanes et harceler</span><span class="sxs-lookup"><span data-stu-id="d5dc2-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="d5dc2-107">Images adultes, racy et Gory</span><span class="sxs-lookup"><span data-stu-id="d5dc2-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="d5dc2-108">Partage d’informations sensibles</span><span class="sxs-lookup"><span data-stu-id="d5dc2-108">Sharing of sensitive information</span></span>

<span data-ttu-id="d5dc2-109">Pour plus d’informations sur la conformité de la communication et la configuration des stratégies pour votre organisation, voir [conformité de la communication dans Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span><span class="sxs-lookup"><span data-stu-id="d5dc2-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="d5dc2-110">Utilisation de la conformité de la communication dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="d5dc2-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="d5dc2-111">Le respect des communications et Microsoft teams sont étroitement intégrés et permettent de limiter les risques de communication au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="d5dc2-112">Après avoir configuré votre première stratégie de conformité des communications, vous pouvez gérer activement les messages et le contenu de Microsoft teams inappropriés, qui est automatiquement signalé dans alertes.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="d5dc2-113">Prise en main</span><span class="sxs-lookup"><span data-stu-id="d5dc2-113">Getting started</span></span>

<span data-ttu-id="d5dc2-114">La mise en route de la conformité de la communication dans Microsoft teams commence par la [planification](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) et la création de stratégies prédéfinies ou personnalisées permettant d’identifier les activités utilisateur inappropriées dans les canaux d’équipe ou dans 1:1 et groupes.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-114">Getting started with communication compliance in Microsoft Teams begins with [planning](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="d5dc2-115">Gardez à l’esprit que vous devrez [configurer](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) des autorisations et des conditions préalables de base dans le cadre du processus de configuration.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-115">Keep in mind that you'll need to [configure](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="d5dc2-116">Les administrateurs d’équipes peuvent configurer les stratégies de conformité des communications aux niveaux suivants :</span><span class="sxs-lookup"><span data-stu-id="d5dc2-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="d5dc2-117">**Niveau utilisateur**: les stratégies à ce niveau s’appliquent à un utilisateur de teams individuel ou peuvent être appliquées à tous les utilisateurs d’équipes au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="d5dc2-118">Ces stratégies couvrent les messages que les utilisateurs peuvent envoyer dans 1:1 ou les discussions de groupe.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="d5dc2-119">Les communications de conversation pour les utilisateurs sont automatiquement surveillées sur toutes les équipes Microsoft teams dont les utilisateurs sont membres.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="d5dc2-120">**Niveau équipes**: les stratégies à ce niveau s’appliquent à un canal d’équipe Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-120">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="d5dc2-121">Ces stratégies couvrent uniquement les messages envoyés uniquement dans le canal Teams.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="d5dc2-122">Agir sur des messages indésirables dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="d5dc2-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="d5dc2-123">Une fois que vous avez configuré vos stratégies et que vous avez reçu des alertes de conformité de communication pour les messages de Microsoft Teams, il est temps que les réviseurs de conformité de votre organisation effectuent des actions sur ces messages.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="d5dc2-124">Les réviseurs peuvent contribuer à la protection de votre organisation en passant en revue les alertes de conformité des communications et en supprimant les messages avec indicateur dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![Supprimer un message dans teams](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="d5dc2-126">Les messages et le contenu supprimés ont été remplacés par les notifications de visionneuses qui décrivent que le message ou le contenu a été supprimé et la stratégie applicable à la suppression.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="d5dc2-127">L’expéditeur du message ou du contenu supprimé est également averti de l’état de suppression et est fourni avec le contenu du message d’origine pour le contexte relatif à sa suppression.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="d5dc2-128">L’expéditeur peut également afficher la condition de stratégie spécifique qui s’applique à la suppression du message.</span><span class="sxs-lookup"><span data-stu-id="d5dc2-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="d5dc2-129">Exemple de Conseil de stratégie présenté par l’expéditeur :</span><span class="sxs-lookup"><span data-stu-id="d5dc2-129">Example of policy tip seen by sender:</span></span>

![Conseil de stratégie pour l’expéditeur](./media/communication-compliance-warning-1.png)

<span data-ttu-id="d5dc2-131">Exemple de notification de condition de stratégie affichée par l’expéditeur :</span><span class="sxs-lookup"><span data-stu-id="d5dc2-131">Example of policy condition notification seen by the sender:</span></span>

![Informations de conditions de stratégie pour l’expéditeur](./media/communication-compliance-warning-2.png)

<span data-ttu-id="d5dc2-133">Exemple de Conseil de stratégie présenté par le destinataire :</span><span class="sxs-lookup"><span data-stu-id="d5dc2-133">Example of policy tip seen by recipient:</span></span>

![Conseil de stratégie pour le destinataire](./media/communication-compliance-warning-3.png)
