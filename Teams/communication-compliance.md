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
# <a name="communication-compliance-with-microsoft-teams"></a>Conformité de la communication avec Microsoft teams

Le respect de la communication est une solution de risque Insider dans Microsoft 365 qui permet de réduire les risques de communication en vous aidant à détecter, capturer et agir sur des messages inappropriés au sein de votre organisation.

Dans Microsoft Teams, la conformité de la communication permet d’identifier les types de contenus inappropriés [suivants](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) dans les canaux d’équipe ou dans 1:1 et les discussions de groupe :

- Langage injurieux, profanes et harceler
- Images adultes, racy et Gory
- Partage d’informations sensibles

Pour plus d’informations sur la conformité de la communication et la configuration des stratégies pour votre organisation, voir [conformité de la communication dans Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Utilisation de la conformité de la communication dans Microsoft teams

Le respect des communications et Microsoft teams sont étroitement intégrés et permettent de limiter les risques de communication au sein de votre organisation. Après avoir configuré votre première stratégie de conformité des communications, vous pouvez gérer activement les messages et le contenu de Microsoft teams inappropriés, qui est automatiquement signalé dans alertes.

### <a name="getting-started"></a>Prise en main

La mise en route de la conformité de la communication dans Microsoft teams commence par la [planification](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) et la création de stratégies prédéfinies ou personnalisées permettant d’identifier les activités utilisateur inappropriées dans les canaux d’équipe ou dans 1:1 et groupes. Gardez à l’esprit que vous devrez [configurer](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) des autorisations et des conditions préalables de base dans le cadre du processus de configuration.

Les administrateurs d’équipes peuvent configurer les stratégies de conformité des communications aux niveaux suivants :

- **Niveau utilisateur**: les stratégies à ce niveau s’appliquent à un utilisateur de teams individuel ou peuvent être appliquées à tous les utilisateurs d’équipes au sein de votre organisation. Ces stratégies couvrent les messages que les utilisateurs peuvent envoyer dans 1:1 ou les discussions de groupe. Les communications de conversation pour les utilisateurs sont automatiquement surveillées sur toutes les équipes Microsoft teams dont les utilisateurs sont membres.
- **Niveau équipes**: les stratégies à ce niveau s’appliquent à un canal d’équipe Microsoft. Ces stratégies couvrent uniquement les messages envoyés uniquement dans le canal Teams.

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Agir sur des messages indésirables dans Microsoft teams

Une fois que vous avez configuré vos stratégies et que vous avez reçu des alertes de conformité de communication pour les messages de Microsoft Teams, il est temps que les réviseurs de conformité de votre organisation effectuent des actions sur ces messages. Les réviseurs peuvent contribuer à la protection de votre organisation en passant en revue les alertes de conformité des communications et en supprimant les messages avec indicateur dans Microsoft Teams.

![Supprimer un message dans teams](./media/communication-compliance-remove-teams-message.png)

Les messages et le contenu supprimés ont été remplacés par les notifications de visionneuses qui décrivent que le message ou le contenu a été supprimé et la stratégie applicable à la suppression. L’expéditeur du message ou du contenu supprimé est également averti de l’état de suppression et est fourni avec le contenu du message d’origine pour le contexte relatif à sa suppression. L’expéditeur peut également afficher la condition de stratégie spécifique qui s’applique à la suppression du message.

Exemple de Conseil de stratégie présenté par l’expéditeur :

![Conseil de stratégie pour l’expéditeur](./media/communication-compliance-warning-1.png)

Exemple de notification de condition de stratégie affichée par l’expéditeur :

![Informations de conditions de stratégie pour l’expéditeur](./media/communication-compliance-warning-2.png)

Exemple de Conseil de stratégie présenté par le destinataire :

![Conseil de stratégie pour le destinataire](./media/communication-compliance-warning-3.png)
