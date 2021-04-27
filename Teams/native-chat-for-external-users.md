---
title: Expérience de conversation native pour les utilisateurs externes (fédérés) dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Découvrez l'expérience de conversation Teams native pour les utilisateurs à accès externe (fédéré) dans Microsoft Teams, où les deux utilisateurs sont dans le mode de mise à niveau TeamsOnly.
ms.openlocfilehash: a06532ab4cd1d1c5ffe3f30d2a6036b2c34c716f
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030114"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="de32d-103">Expérience de conversation native pour les utilisateurs externes (fédérés) dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de32d-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="de32d-104">Lorsqu'un utilisateur de Microsoft Teams discute avec un utilisateur externe (fédéré), l'expérience de conversation est limitée au texte.</span><span class="sxs-lookup"><span data-stu-id="de32d-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="de32d-105">Toutefois, si l'utilisateur de Teams et la personne d'une autre organisation sont en mode de mise à niveau TeamsOnly, vous pouvez avoir une « expérience de conversation Teams native » qui inclut une mise en forme enrichie, des @mentions et d'autres fonctionnalités de conversation.</span><span class="sxs-lookup"><span data-stu-id="de32d-105">However, if both your Teams user and the person in another organization are in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="de32d-106">Les conversations Teams natives avec des personnes d'autres organisations sont limitées à des conversations en tête-à-tête uniquement.</span><span class="sxs-lookup"><span data-stu-id="de32d-106">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="de32d-107">L'expérience de conversation native pour les membres d'autres organisations est désactivée pour tous les locataires Teams, mais toutes les personnes ne sont pas éligibles.</span><span class="sxs-lookup"><span data-stu-id="de32d-107">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="de32d-108">Pour obtenir une expérience de conversation native, l'expéditeur et le récepteur doivent être configurés pour le mode de mise à niveau de TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="de32d-108">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="de32d-109">Pour en savoir plus sur les stratégies de mise à niveau, [lisez Définir vos paramètres de coexistence et de mise à niveau.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="de32d-109">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="de32d-110">Pour consulter la liste des fonctionnalités pour les utilisateurs d'accès externe dans Teams, voir [Comparer l'accès externe et invité.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="de32d-110">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="de32d-111">Comment savoir si je suis dans une conversation native ?</span><span class="sxs-lookup"><span data-stu-id="de32d-111">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="de32d-112">Si vous pouvez uniquement échanger du texte dans votre conversation avec des personnes d'autres organisations, vous êtes dans une conversation standard d'accès externe (fédéré).</span><span class="sxs-lookup"><span data-stu-id="de32d-112">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="de32d-113">Si vous avez toutes les autres fonctionnalités de conversation, notamment la mise en forme, les @mentions, les emojis, etc., vous êtes dans une conversation Teams native.</span><span class="sxs-lookup"><span data-stu-id="de32d-113">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="de32d-114">Teams vérifie régulièrement le mode de mise à niveau pour les membres d'autres organisations et, lorsqu'elle trouve qu'elles exécutent Teams en mode de mise à niveau TeamsOnly, vous êtes invité à basculer vers une conversation Teams native et à verrouiller la conversation d'origine.</span><span class="sxs-lookup"><span data-stu-id="de32d-114">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="de32d-115">Lorsque vous basculez vers une conversation Teams native, Teams ne fusionne pas les deux conversations.</span><span class="sxs-lookup"><span data-stu-id="de32d-115">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="de32d-116">Au lieu de cela, vous verrez les deux conversations dans votre flux de conversation.</span><span class="sxs-lookup"><span data-stu-id="de32d-116">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="de32d-117">La nouvelle conversation Teams native est active, mais l'ancienne conversation uniquement textuelle est verrouillée.</span><span class="sxs-lookup"><span data-stu-id="de32d-117">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="de32d-118">Que se passe-t-il si un utilisateur n'est plus en mode Teams uniquement ?</span><span class="sxs-lookup"><span data-stu-id="de32d-118">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="de32d-119">Si vous parliez teams native avec des membres d'autres organisations et que l'une d'entre vous sort du mode de mise à niveau TeamsOnly, Teams verrouille la conversation Teams native et vous fournit un lien pour une conversation limitée par SMS uniquement.</span><span class="sxs-lookup"><span data-stu-id="de32d-119">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="de32d-120">Vous ne pourrez pas continuer dans la conversation Teams native.</span><span class="sxs-lookup"><span data-stu-id="de32d-120">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="de32d-121">Vous pouvez toujours lire la conversation Teams native, mais vous ne pouvez pas poursuivre la conversation dans cette conversation.</span><span class="sxs-lookup"><span data-stu-id="de32d-121">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="de32d-122">Si Teams trouve une ancienne conversation par SMS uniquement avec cette personne, elle l'aura fait.</span><span class="sxs-lookup"><span data-stu-id="de32d-122">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="de32d-123">Sinon, Teams crée une conversation par SMS uniquement.</span><span class="sxs-lookup"><span data-stu-id="de32d-123">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="de32d-124">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="de32d-124">Related topics</span></span>

[<span data-ttu-id="de32d-125">Gérer l'accès externe dans Teams</span><span class="sxs-lookup"><span data-stu-id="de32d-125">Manage external access in Teams</span></span>](manage-external-access.md)
