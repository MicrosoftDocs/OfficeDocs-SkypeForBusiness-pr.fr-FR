---
title: Expérience de conversation native pour les utilisateurs externes (fédérés) au Microsoft Teams
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
description: Découvrez l’expérience de conversation Teams native pour les utilisateurs à accès externe (fédérés) dans Microsoft Teams où les deux utilisateurs sont en mode de mise à niveau TeamsOnly.
ms.openlocfilehash: 992b4dd28d17f1ba8abf7217d622da18813c3118
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138230"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Expérience de conversation native pour les utilisateurs externes (fédérés) au Microsoft Teams

Lorsqu’un Microsoft Teams un utilisateur discute avec un utilisateur externe (fédéré), l’expérience de conversation est limitée au texte. Toutefois, si votre utilisateur Teams et la personne d’une autre organisation sont en mode de mise à niveau TeamsOnly, vous pouvez avoir une « expérience de conversation native Teams », qui inclut une mise en forme enrichie, des @mentions et d’autres fonctionnalités de conversation.

L’expérience de conversation native pour les utilisateurs d’autres organisations est Teams client, mais toutes les personnes ne sont pas éligibles. Pour obtenir une expérience de conversation native, l’expéditeur et le récepteur doivent être configurés pour le mode de mise à niveau de TeamsOnly. Pour en savoir plus sur les stratégies de mise à niveau, [lisez Définir vos paramètres de coexistence et de mise à niveau.](setting-your-coexistence-and-upgrade-settings.md)

Pour consulter la liste des fonctionnalités pour les utilisateurs d’accès externe dans Teams, voir Comparer les accès externe [et invité.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Comment savoir si je suis dans une conversation native ?

Si vous pouvez uniquement échanger du texte dans votre conversation avec des personnes d’autres organisations, vous êtes dans une conversation standard d’accès externe (fédéré). Si vous avez d’autres fonctionnalités de conversation, notamment la mise en forme, les @mentions, les emojis, etc., vous êtes dans une conversation instantanée native Teams conversation. 

Teams vérifie régulièrement le mode de mise à niveau pour les membres d’autres organisations et, lorsqu’il trouve un Teams en mode de mise à niveau de TeamsOnly, il vous invite à basculer vers une conversation Teams native et à verrouiller la conversation d’origine.

Lorsque vous basculez vers une conversation Teams, Teams ne fusionne pas les deux conversations. Au lieu de cela, vous verrez les deux conversations dans votre flux de conversation. La nouvelle conversation de langue Teams native est active, mais l’ancienne conversation uniquement textuelle est verrouillée.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>Que se passe-t-il si un utilisateur n’est plus en Teams uniquement ?

Si vous passiez une conversation Teams native avec des personnes d’autres organisations et que l’une d’entre vous sort du mode de mise à niveau de TeamsOnly, Teams verrouille la conversation Teams native et vous fournit un lien pour une conversation limitée par SMS uniquement. Vous ne pourrez pas continuer dans la conversation native Teams conversation. Vous pouvez toujours lire le texte natif Teams conversation, mais vous ne pouvez pas poursuivre la conversation dans cette conversation.

Si Teams trouve une ancienne conversation par SMS uniquement avec cette personne, celle-ci sera rétablie. Sinon, Teams crée une conversation par SMS uniquement.


## <a name="related-topics"></a>Sujets associés

[Gérer l’accès externe dans Teams](manage-external-access.md)
