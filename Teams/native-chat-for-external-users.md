---
title: Expérience de conversation native pour les utilisateurs externes (fédérés) dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Découvrez l’expérience de conversation Teams native pour les utilisateurs à accès externe (fédéré) dans Microsoft Teams où les deux utilisateurs sont en mode de mise à niveau TeamsOnly.
ms.openlocfilehash: 759ad4f03de099637df0e92a7a8925a7c18ae3fd
ms.sourcegitcommit: 8f26bf0ff88f1f6881de32914be00d5f0cc7396a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2023
ms.locfileid: "69740799"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Expérience de conversation native pour les utilisateurs externes (fédérés) dans Microsoft Teams

Lorsqu’un utilisateur Microsoft Teams discute avec un utilisateur externe (fédéré), l’expérience de conversation est limitée au texte. Toutefois, si votre utilisateur Teams et la personne d’une autre organisation sont en mode de mise à niveau TeamsOnly, vous pouvez disposer d’une « expérience de conversation Teams native », qui inclut une mise en forme enrichie, des @mentions et d’autres fonctionnalités de conversation.

L’expérience de conversation native pour les personnes d’autres organisations est activée pour tous les locataires Teams, mais toutes les personnes ne sont pas éligibles. Pour obtenir une expérience de conversation native, l’expéditeur et le destinataire doivent être configurés pour le mode de mise à niveau TeamsOnly. Pour en savoir plus sur les stratégies de mise à niveau, consultez [Définition de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md).

Pour afficher la liste des fonctionnalités pour les utilisateurs d’accès externe dans Teams, consultez [Comparer l’accès externe et l’accès invité](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).

> [!NOTE]
> L’expérience de conversation native n’est pas disponible pour les environnements cloud Microsoft 365 : Microsoft 365 WorldWide (y compris GCC) depuis/vers GCC High, GCC High depuis/vers DoD, ou WW depuis/vers DoD.

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Comment faire savoir si je suis dans une conversation native ?

Si vous pouvez uniquement échanger du texte dans votre conversation avec des personnes d’autres organisations, vous êtes dans une conversation standard avec accès externe (fédéré). Si vous avez d’autres fonctionnalités de conversation, notamment la mise en forme, les @mentions, les emojis, etc., vous êtes dans une conversation Teams native. 

Teams vérifie régulièrement le mode de mise à niveau pour les personnes d’autres organisations et, lorsqu’il trouve un exécutant Teams dans le mode de mise à niveau TeamsOnly, il vous invite à basculer vers une conversation Teams native et à verrouiller la conversation d’origine.

Lorsque vous basculez vers une conversation Teams native, Teams ne fusionne pas les deux conversations. Au lieu de cela, vous verrez les deux conversations dans votre flux de conversation. La nouvelle conversation native teams est active, mais l’ancienne conversation texte uniquement est verrouillée.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>Que se passe-t-il si un utilisateur n’est plus en mode Teams uniquement ?

Si vous avez eu une conversation Teams native avec des personnes d’autres organisations et que l’un d’entre vous est sorti du mode de mise à niveau TeamsOnly, Teams verrouille la conversation Teams native et vous donne un lien pour une conversation limitée, texte uniquement. Vous ne pourrez pas continuer dans la conversation Teams native. Vous pouvez toujours lire la conversation Teams native, mais vous ne pouvez pas y poursuivre la conversation.

Si Teams trouve une ancienne conversation en texte uniquement avec cette personne, elle réactivera cette conversation. Sinon, Teams crée une conversation texte uniquement.


## <a name="related-topics"></a>Rubriques connexes

[Gérer l’accès externe dans Teams](manage-external-access.md)
