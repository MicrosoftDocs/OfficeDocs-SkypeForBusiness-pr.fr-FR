---
title: Une interface utilisateur native pour les discussions pour les utilisateurs externes de Microsoft teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Apprenez-en davantage sur l’interface de chat d’équipe native pour les utilisateurs de Microsoft Teams (fédéré) disponibles entre les utilisateurs externes lorsque les deux utilisateurs sont en mode de mise à niveau TeamsOnly.
ms.openlocfilehash: a7a66693bbff98aa707c369a9da08d0ccfe48f69
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2019
ms.locfileid: "37754340"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="ea46a-103">Une interface utilisateur native pour les discussions pour les utilisateurs externes de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="ea46a-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>
======================================

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="ea46a-104">Lorsqu’un utilisateur de Microsoft teams discute avec un utilisateur externe (fédéré), l’interface de conversation est limitée au texte.</span><span class="sxs-lookup"><span data-stu-id="ea46a-104">When a Microsoft Teams users is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="ea46a-105">Toutefois, si votre client teams et celui de l’utilisateur externe se trouvent dans le mode de mise à niveau de TeamsOnly, vous pouvez avoir une « expérience de conversation en équipe native » qui inclut une mise en forme enrichie, @mentions et d’autres fonctionnalités de conversation.</span><span class="sxs-lookup"><span data-stu-id="ea46a-105">However, if both your Teams tenant and that of the external user is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="ea46a-106">En d’autres termes, vous pouvez utiliser la même expérience de conversation d’équipe 1:1 avec les utilisateurs externes éligibles, comme vous le faites avec les utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ea46a-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible external users as you'd have with users in your organization.</span></span> <span data-ttu-id="ea46a-107">Les discussions d’équipe natives avec des utilisateurs externes sont toujours limitées aux discussions 1:1 uniquement (les utilisateurs externes ne peuvent pas faire des discussions de groupe).</span><span class="sxs-lookup"><span data-stu-id="ea46a-107">Native Teams chats with external users are still limited to 1:1 chats only (external users can't do group chats).</span></span>

<span data-ttu-id="ea46a-108">L’interface de conversation native pour les utilisateurs externes est activée pour tous les clients Teams, mais tous les utilisateurs ne sont pas éligibles.</span><span class="sxs-lookup"><span data-stu-id="ea46a-108">The native chat experience for external users is turned on for all Teams tenants, but not all users are eligible.</span></span> <span data-ttu-id="ea46a-109">Pour vous offrir une conversation native, l’expéditeur et le destinataire doivent être sur un client d’équipe exécutant le mode de mise à niveau TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ea46a-109">To be offered a native chat experience, both the sender and receiver need to be on a Teams tenant that's running the TeamsOnly upgrade mode.</span></span> <span data-ttu-id="ea46a-110">Pour en savoir plus sur les stratégies de mise à niveau, voir [définir vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ea46a-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="ea46a-111">Pour afficher une liste de fonctionnalités pour les utilisateurs d’accès externe dans Teams, voir [comparer des accès externes et invités](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="ea46a-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="ea46a-112">Comment savoir si je suis en mode conversation ?</span><span class="sxs-lookup"><span data-stu-id="ea46a-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="ea46a-113">Si vous ne pouvez échanger uniquement du texte dans votre conversation avec un utilisateur externe, vous êtes dans une conversation à accès externe standard (fédéré).</span><span class="sxs-lookup"><span data-stu-id="ea46a-113">If you can only exchange text in your chat with an external user, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="ea46a-114">Si vous disposez de toutes les autres fonctionnalités de conversation, y compris la mise en forme, les @mentions, les emoji, etc., vous êtes dans une conversation en équipe native avec votre utilisateur externe.</span><span class="sxs-lookup"><span data-stu-id="ea46a-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat with your external user.</span></span> 

<span data-ttu-id="ea46a-115">Teams vérifie régulièrement le mode de mise à niveau pour les utilisateurs externes et, lorsqu’il trouve un utilisateur externe exécutant teams dans le mode de mise à niveau d’TeamsOnly, il vous invite à passer à une discussion d’équipe native et à verrouiller la discussion d’origine.</span><span class="sxs-lookup"><span data-stu-id="ea46a-115">Teams periodically checks the upgrade mode for external users and, when it finds an external user running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="ea46a-116">Lorsque vous basculez vers une conversation d’équipe native, Teams ne fusionne pas les deux conversations.</span><span class="sxs-lookup"><span data-stu-id="ea46a-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="ea46a-117">À la place, vous verrez les deux discussions dans votre fil de discussion.</span><span class="sxs-lookup"><span data-stu-id="ea46a-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="ea46a-118">Le nouveau chat natif-teams est actif, mais l’ancien message texte uniquement est verrouillé.</span><span class="sxs-lookup"><span data-stu-id="ea46a-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="ea46a-119">Que se passe-t-il si un utilisateur n’est pas en mode uniquement en équipe ?</span><span class="sxs-lookup"><span data-stu-id="ea46a-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="ea46a-120">Si vous avez une conversation d’équipe native avec un utilisateur externe et que vous êtes à l’extérieur du mode de mise à niveau d’TeamsOnly, teams verrouille la discussion d’équipe native et vous donne un lien pour une conversation de texte limitée.</span><span class="sxs-lookup"><span data-stu-id="ea46a-120">If you were having a native Teams chat with an external user and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="ea46a-121">Vous ne serez pas en mesure de continuer dans la conversation d’équipe native.</span><span class="sxs-lookup"><span data-stu-id="ea46a-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="ea46a-122">Vous pouvez toujours lire les discussions d’équipe natives, mais vous ne pouvez pas continuer la conversation.</span><span class="sxs-lookup"><span data-stu-id="ea46a-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="ea46a-123">Si teams recherche une ancienne conversation textuelle uniquement avec cet utilisateur externe, il le réutilisera.</span><span class="sxs-lookup"><span data-stu-id="ea46a-123">If Teams finds an old text-only chat with this external user, it'll revive that chat.</span></span> <span data-ttu-id="ea46a-124">Dans le cas contraire, teams crée une discussion de texte uniquement.</span><span class="sxs-lookup"><span data-stu-id="ea46a-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ea46a-125">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="ea46a-125">Related topics</span></span>

[<span data-ttu-id="ea46a-126">Gérer l’accès externe dans teams</span><span class="sxs-lookup"><span data-stu-id="ea46a-126">Manage external access in Teams</span></span>](manage-external-access.md)
