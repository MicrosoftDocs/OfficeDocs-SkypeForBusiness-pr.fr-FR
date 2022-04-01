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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33a2f72307b82fa4264f264e0f98a4d0aed45ae4
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592839"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Conformité des communications avec les Microsoft Teams

La conformité des communications est une solution insider à risque au Microsoft 365 qui permet de minimiser les risques de communication en vous aidant à détecter, capturer et agir sur les messages inappropriés dans votre organisation.

Par Microsoft Teams, la conformité des communications permet d’identifier les [types](/microsoft-365/compliance/communication-compliance-feature-reference) de contenus inappropriés suivants dans les canaux Teams, les canaux de Teams privés ou dans les conversations en tête-à-tête et de groupe :

- Langage choquant, choquant et choquant
- Images pour adultes, racy et gory
- Partage d’informations sensibles

Pour plus d’informations sur la conformité des communications et la configuration des stratégies pour votre organisation, consultez [la conformité des communications dans Microsoft 365](/microsoft-365/compliance/communication-compliance). Pour plus d’informations sur Microsoft 365 abonnements qui incluent la conformité des communications, voir [les solutions de risque Insider](/microsoft-365/compliance/insider-risk-solution-overview#communication-compliance).

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Comment utiliser la conformité des communications dans Microsoft Teams

La conformité et les Microsoft Teams communication sont étroitement intégrés et peuvent contribuer à minimiser les risques de communication dans votre organisation. Après avoir configuré vos premières stratégies de conformité aux communications, vous pouvez gérer activement les messages Microsoft Teams et le contenu signalés automatiquement par des alertes.

### <a name="getting-started"></a>Prise en main

La mise en place de la conformité des communications dans Microsoft Teams commence par [](/microsoft-365/compliance/communication-compliance-plan) la planification et la création de stratégies prédéfinës ou personnalisées permettant d’identifier les activités inappropriées des utilisateurs dans les canaux Teams ou dans les deux ou en deux et groupes. N’oubliez pas que vous devez configurer [](/microsoft-365/compliance/communication-compliance-configure) certaines autorisations et conditions préalables de base dans le cadre du processus de configuration.

Teams administrateurs peuvent configurer des stratégies de conformité des communications aux niveaux suivants :

- **Niveau utilisateur** : Les stratégies de ce niveau s’appliquent à Teams utilisateur individuel ou peuvent être appliquées à tous Teams utilisateurs de votre organisation. Ces stratégies couvrent les messages que ces utilisateurs peuvent envoyer dans des conversations à deux ou de groupe. Les communications de conversation pour les utilisateurs sont automatiquement contrôlées dans toutes les Microsoft Teams où les utilisateurs en sont membres.
- **Teams niveau :** les stratégies à ce niveau s’appliquent à Microsoft Teams canal, y compris un canal privé. Ces stratégies couvrent les messages envoyés dans Teams canal uniquement.

### <a name="report-a-concern-in-microsoft-teams"></a>Signaler un problème dans Microsoft Teams

*L’option* Signaler un problème dans Teams messages est activée par défaut et peut être contrôlée via les stratégies de messagerie Teams dans le Teams [d’administration](/microsoftteams/manage-teams-in-modern-portal). Cela permet aux utilisateurs de votre organisation d’envoyer des messages inappropriés pour révision par les réviseurs de conformité des communications pour la stratégie. Pour plus d’informations sur les messages signalés par les utilisateurs en conformité avec les communications, voir [Stratégies de conformité des communications](/microsoft-365/compliance/communication-compliance-policies#user-reported-messages-policy).

![Signaler un menu de problème.](./media/communication-compliance-report-a-concern-full-menu.png)

Après avoir envoyé le message pour révision, l’utilisateur reçoit une confirmation de l’envoi dans Microsoft Teams. Les autres participants à la conversation ne voient pas cette notification.

![Signalez une confirmation de problème.](./media/communication-compliance-report-a-concern.png)

Les utilisateurs de votre organisation obtiennent automatiquement la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée. Modifiez les paramètres de la stratégie globale ou créez et affectez une ou plusieurs stratégies personnalisées pour activer ou désactiver cette fonctionnalité. Pour plus d’informations, [voir Gérer les stratégies de messagerie dans Teams](/microsoftteams/messaging-policies-in-teams).

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Agir sur les messages inappropriés dans Microsoft Teams

Après avoir configuré vos stratégies et reçu des alertes de conformité aux communications pour les messages Microsoft Teams, les réviseurs de conformité de votre organisation doivent agir sur ces messages. Cela inclura également les messages signalés par l’utilisateur s’ils sont activés pour votre organisation. Les réviseurs peuvent vous aider à protéger votre organisation en filant les alertes de conformité aux communications et en supprimant les messages marqués d’un Microsoft Teams.

![Supprimer un message dans Teams.](./media/communication-compliance-remove-teams-message.png)

Les messages et le contenu supprimés sont remplacés par des notifications pour les utilisateurs qui leur expliquent que le message ou le contenu ont été supprimés et quelle stratégie s’applique à la suppression. L’expéditeur du message ou du contenu supprimé est également informé de l’état de suppression et fournit le contenu du message d’origine pour le contexte relatif à sa suppression. L’expéditeur peut également afficher la condition de stratégie spécifique qui s’applique à la suppression du message.

Exemple de conseil de stratégie vu par l’expéditeur :

![Conseil de stratégie pour l’expéditeur.](./media/communication-compliance-warning-1.png)

Exemple de notification de stratégie vu par l’expéditeur :

![Informations sur les conditions de stratégie de l’expéditeur.](./media/communication-compliance-warning-2.png)

Exemple de conseil de stratégie vu par le destinataire :

![Conseil de stratégie pour le destinataire.](./media/communication-compliance-warning-3.png)