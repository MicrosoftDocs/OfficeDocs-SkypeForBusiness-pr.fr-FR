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
ms.openlocfilehash: 572087d86672294b566cd99365599dbead1aa3e7
ms.sourcegitcommit: 1448bb2e66074322b8f4bf234fce36ea9c8f9913
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39966757"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Une interface utilisateur native pour les discussions pour les utilisateurs externes de Microsoft teams
======================================

Lorsqu’un utilisateur de Microsoft teams discute avec un utilisateur externe (fédéré), l’interface de conversation est limitée au texte. Toutefois, si votre client teams et celui de l’utilisateur externe se trouvent dans le mode de mise à niveau de TeamsOnly, vous pouvez avoir une « expérience de conversation en équipe native » qui inclut une mise en forme enrichie, @mentions et d’autres fonctionnalités de conversation. En d’autres termes, vous pouvez utiliser la même expérience de conversation d’équipe 1:1 avec les utilisateurs externes éligibles, comme vous le faites avec les utilisateurs de votre organisation. Les discussions d’équipe natives avec des utilisateurs externes sont toujours limitées aux discussions 1:1 uniquement (les utilisateurs externes ne peuvent pas faire des discussions de groupe).

L’interface de conversation native pour les utilisateurs externes est activée pour tous les clients Teams, mais tous les utilisateurs ne sont pas éligibles. Pour vous offrir une conversation native, l’expéditeur et le destinataire doivent être sur un client d’équipe exécutant le mode de mise à niveau TeamsOnly. Pour en savoir plus sur les stratégies de mise à niveau, voir [définir vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md).

Pour afficher une liste de fonctionnalités pour les utilisateurs d’accès externe dans Teams, voir [comparer des accès externes et invités](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Comment savoir si je suis en mode conversation ?

Si vous ne pouvez échanger uniquement du texte dans votre conversation avec un utilisateur externe, vous êtes dans une conversation à accès externe standard (fédéré). Si vous disposez de toutes les autres fonctionnalités de conversation, y compris la mise en forme, les @mentions, les emoji, etc., vous êtes dans une conversation en équipe native avec votre utilisateur externe. 

Teams vérifie régulièrement le mode de mise à niveau pour les utilisateurs externes et, lorsqu’il trouve un utilisateur externe exécutant teams dans le mode de mise à niveau d’TeamsOnly, il vous invite à passer à une discussion d’équipe native et à verrouiller la discussion d’origine.

Lorsque vous basculez vers une conversation d’équipe native, Teams ne fusionne pas les deux conversations. À la place, vous verrez les deux discussions dans votre fil de discussion. Le nouveau chat natif-teams est actif, mais l’ancien message texte uniquement est verrouillé.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>Que se passe-t-il si un utilisateur n’est pas en mode uniquement en équipe ?

Si vous avez une conversation d’équipe native avec un utilisateur externe et que vous êtes à l’extérieur du mode de mise à niveau d’TeamsOnly, teams verrouille la discussion d’équipe native et vous donne un lien pour une conversation de texte limitée. Vous ne serez pas en mesure de continuer dans la conversation d’équipe native. Vous pouvez toujours lire les discussions d’équipe natives, mais vous ne pouvez pas continuer la conversation.

Si teams recherche une ancienne conversation textuelle uniquement avec cet utilisateur externe, il le réutilisera. Dans le cas contraire, teams crée une discussion de texte uniquement.


## <a name="related-topics"></a>Voir aussi

[Gérer l’accès externe dans teams](manage-external-access.md)
