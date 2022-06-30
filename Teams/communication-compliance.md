---
title: Conformité des communications avec Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Découvrez la conformité des communications, qui fait partie de l’ensemble de solutions à risque interne, du point de vue de Microsoft Teams (cela fait partie des fonctionnalités de conformité des communications M365).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b96108f3bf548475cd19822967ba4e484fb26703
ms.sourcegitcommit: b383b309dbdf9caac7ad7e4a94df8d89016dc485
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66551201"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Conformité des communications avec Microsoft Teams

Conformité des communications Microsoft Purview est une solution à risque interne dans Microsoft 365 qui permet de réduire les risques de communication en vous aidant à détecter, capturer et agir sur des messages inappropriés dans votre organisation.

Pour Microsoft Teams, la conformité des communications permet d’identifier les [types de contenu inapproprié suivants](/microsoft-365/compliance/communication-compliance-feature-reference) dans les canaux Teams, les canaux Teams privés ou dans les conversations de groupe et 1:1 :

- Langage offensant, profane et harcelant
- Images adultes, racées et gory
- Partage d’informations sensibles

Pour plus d’informations sur la conformité des communications et la configuration des stratégies pour votre organisation, consultez [En savoir plus sur la conformité des communications](/microsoft-365/compliance/communication-compliance).

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Utilisation de la conformité des communications dans Microsoft Teams

La conformité des communications et Microsoft Teams sont étroitement intégrés et peuvent aider à réduire les risques de communication au sein de votre organisation. Une fois que vous avez configuré vos premières stratégies de conformité des communications, vous pouvez gérer activement les messages et le contenu Microsoft Teams inappropriés qui sont automatiquement marqués dans les alertes.

### <a name="getting-started"></a>Prise en main

La prise en main de la conformité des communications dans Microsoft Teams commence par [la planification](/microsoft-365/compliance/communication-compliance-plan) et la création de stratégies prédéfinies ou personnalisées pour identifier les activités utilisateur inappropriées dans les canaux Teams ou dans 1:1 et les groupes. N’oubliez pas que vous devez [configurer](/microsoft-365/compliance/communication-compliance-configure) certaines autorisations et conditions préalables de base dans le cadre du processus de configuration.

Les administrateurs Teams peuvent configurer des stratégies de conformité des communications aux niveaux suivants :

- **Niveau utilisateur** : les stratégies de ce niveau s’appliquent à un utilisateur Teams individuel ou peuvent être appliquées à tous les utilisateurs Teams de votre organisation. Ces stratégies couvrent les messages que ces utilisateurs peuvent envoyer dans des conversations de groupe ou 1:1. Les communications de conversation pour les utilisateurs sont automatiquement surveillées dans toutes les Équipes Microsoft où les utilisateurs sont membres.
- **Niveau Teams** : les stratégies à ce niveau s’appliquent à un canal Microsoft Teams, y compris un canal privé. Ces stratégies couvrent uniquement les messages envoyés dans le canal Teams.

### <a name="report-a-concern-in-microsoft-teams"></a>Signaler une préoccupation dans Microsoft Teams

>[!NOTE]
>La disponibilité des messages signalés par l’utilisateur pour les organisations sous licence et utilisant [la conformité des communications](/microsoft-365/compliance/communication-compliance-configure#subscriptions-and-licensing) et Microsoft Teams a démarré en mai 2022. Cette fonctionnalité sera disponible d’ici le 31 août 2022 pour toutes les organisations sous licence et utilisant la conformité des communications jusqu’en juillet 2022. Pour les organisations qui commencent à utiliser la conformité des communications après juillet 2022, la disponibilité de la stratégie de messages signalés par l’utilisateur peut prendre jusqu’à 30 jours à compter de la date de votre licence et de la première utilisation de la conformité des communications.

L’option *Signaler une préoccupation* pour les messages de conversation personnelle et de groupe Teams est activée par défaut et peut être contrôlée via des stratégies de messagerie Teams dans le [Centre d’administration Teams](/microsoftteams/manage-teams-in-modern-portal). Cela permet aux utilisateurs de votre organisation d’envoyer des messages de conversation interne inappropriés pour révision par les réviseurs de conformité des communications pour la stratégie. Pour plus d’informations sur les messages signalés par l’utilisateur dans la conformité des communications, consultez [Stratégies de conformité des communications](/microsoft-365/compliance/communication-compliance-policies#user-reported-messages-policy).

![Signaler un menu d’inquiétude.](./media/communication-compliance-report-a-concern-full-menu.png)

Après avoir envoyé le message pour révision, l’utilisateur reçoit une confirmation de l’envoi dans Microsoft Teams. Les autres participants à la conversation ne voient pas cette notification.

![Signalez une confirmation de préoccupation.](./media/communication-compliance-report-a-concern.png)

Les utilisateurs de votre organisation obtiennent automatiquement la stratégie globale, sauf si vous créez et affectez une stratégie personnalisée. Modifiez les paramètres de la stratégie globale ou créez et affectez une ou plusieurs stratégies personnalisées pour activer ou désactiver cette fonctionnalité. Pour plus d’informations, consultez [Gérer les stratégies de messagerie dans Teams](/microsoftteams/messaging-policies-in-teams).

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Agir sur les messages inappropriés dans Microsoft Teams

Une fois que vous avez configuré vos stratégies et reçu des alertes de conformité des communications pour les messages Microsoft Teams, il est temps pour les réviseurs de conformité de votre organisation d’agir sur ces messages. Cela inclut également les messages signalés par l’utilisateur s’ils sont activés pour votre organisation. Les réviseurs peuvent aider à protéger votre organisation en examinant les alertes de conformité des communications et en supprimant les messages marqués d’indicateurs dans Microsoft Teams.

![Supprimez un message dans Teams.](./media/communication-compliance-remove-teams-message.png)

Les messages et le contenu supprimés sont remplacés par des notifications pour les visionneuses expliquant que le message ou le contenu a été supprimé et quelle stratégie est applicable à la suppression. L’expéditeur du message ou du contenu supprimé est également averti de l’état de suppression et fourni avec le contenu du message d’origine pour le contexte relatif à sa suppression. L’expéditeur peut également afficher la condition de stratégie spécifique qui s’applique à la suppression du message.

Exemple de conseil de stratégie vu par l’expéditeur :

![Conseil de stratégie pour l’expéditeur.](./media/communication-compliance-warning-1.png)

Exemple de notification de stratégie vue par l’expéditeur :

![Informations de condition de stratégie pour l’expéditeur.](./media/communication-compliance-warning-2.png)

Exemple de conseil de stratégie vu par le destinataire :

![Conseil de stratégie pour le destinataire.](./media/communication-compliance-warning-3.png)