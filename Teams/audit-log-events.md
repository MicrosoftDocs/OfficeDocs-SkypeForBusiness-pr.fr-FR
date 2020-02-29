---
title: Rechercher des événements Microsoft Teams dans le journal d'audit
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: Découvrez comment récupérer des données Microsoft Teams à partir du journal d'audit d’Office 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f53d1a0b5e600de9d38233b243dba3486b88bf1
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341622"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Rechercher des événements Microsoft Teams dans le journal d'audit

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Le journal d’audit peut vous aider à vérifier des activités spécifiques dans les services Office 365. Pour Teams, voici certaines des activités qui sont vérifiées :

- Création d'une équipe

- Suppression d'une équipe

- Ajout d'un canal

- Modification d'un paramètre

> [!NOTE]
> Les événements d’audit provenant de canaux privés sont également enregistrés tels qu’ils sont destinés aux canaux des équipes et des canaux standard.

Pour la liste complète des activités qui sont vérifiées dans Office 365, consultez la rubrique [Effectuer des recherches dans le journal d'audit dans le Centre de sécurité et de conformité d'Office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="turn-on-auditing-in-teams"></a>Activer l’audit dans Teams

Pour pouvoir voir les données d’audit, vous devez d’abord activer l’audit dans le [Centre de sécurité & conformité](https://protection.office.com). Pour obtenir de l’aide sur la fonctionnalité d’audit, consultez la rubrique [Activer ou désactiver la recherche du journal d’audit d’Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).

> [!IMPORTANT]
> Les données d'audit sont disponibles uniquement à partir du point d'activation de la fonctionnalité d'audit.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Récupérer des données Teams à partir du journal d'audit

1. Pour récupérer les journaux d’audit, accédez au [Centre de sécurité et de conformité](https://go.microsoft.com/fwlink/?linkid=855775). Sous **Rechercher**, sélectionnez **Rechercher dans le journal d’audit**.
1. Utilisez l’option **Rechercher** pour filtrer les données en fonction des activités, dates et utilisateurs que vous souhaitez vérifier.
1. Pour une analyse plus approfondie, exportez les résultats dans Excel.

> [!IMPORTANT]
> Les données d’audit sont visibles dans le journal d’audit si la fonctionnalité d’audit est activée.

## <a name="external-user-scenario"></a>Scénario d’utilisateur externe

Dans le cas d’un scénario d’entreprise, l’ajout d’utilisateurs externes à votre environnement d’équipes peut être un scénario. Si les utilisateurs externes sont activés, il est recommandé de surveiller leur présence.

![Capture d’écran d’une liste d’événements déclenchés par des suppressions massiques](media/TeamsExternalUserAddPolicy.png)

La capture d’écran de cette stratégie pour contrôler l’ajout d’utilisateurs externes vous permet d’attribuer un nom à la stratégie, de définir la gravité en fonction des besoins de votre entreprise, de la définir comme (dans ce cas) sur une activité unique, puis de définir les paramètres qui surveilleront spécifiquement l’ajout. d’utilisateurs non internes et limiter cette activité à Microsoft Teams.

Les résultats de cette stratégie pourront alors être affichés dans le journal des activités :

![Capture d’écran d’une liste d’événements déclenchés par des suppressions massiques](media/TeamsExternalUserList.png)

Dans cette section, vous pouvez passer en revue les correspondances à la stratégie que vous avez définie et procéder aux modifications nécessaires ou exporter les résultats pour les utiliser ailleurs.

## <a name="mass-delete-scenario"></a>Scénario de suppression massive

Comme mentionné ci-dessus, vous pouvez surveiller des scénarios de suppression. Il est possible de créer une stratégie qui surveillerait la suppression massive des sites d’équipe :

![Capture d’écran de la page de création d’une stratégie montrant la création d’une stratégie pour la détection de suppression d’équipe en masse](media/TeamsMassDeletePolicy.png)

Comme le montre la capture d’écran, vous pouvez définir de nombreux paramètres différents pour cette stratégie afin de surveiller les suppressions d’équipe, y compris la gravité, l’action unique ou répétée, et les paramètres limitant ce paramètre à la suppression des équipes et des sites. Cette opération peut être réalisée indépendamment d’un modèle, ou vous avez peut-être créé un modèle pour baser cette stratégie, en fonction des besoins de votre organisation.

Après avoir établi une stratégie qui fonctionnera pour votre entreprise, vous pouvez passer en revue les résultats dans le journal d’activité en tant qu’événements déclenchés :

![Capture d’écran d’une liste d’événements déclenchés par des suppressions massiques](media/TeamsMassDeleteList.png)

Vous pouvez filtrer vers le bas jusqu’à la stratégie que vous avez définie pour afficher les résultats de cette stratégie. Si les résultats que vous obtenez dans le journal d’activité ne sont pas satisfaisants (il est possible que vous voyiez un grand nombre de résultats ou qu’il n’y en ait aucun), cela peut vous aider à peaufiner la requête afin de la rendre plus pertinente pour ce que vous en avez besoin.

## <a name="video-techtip-using-audit-log-search-in-teams"></a>Vidéo : Conseil technique : utilisation de la recherche du journal d’audit dans Teams

Rejoignez Ansuman Acharya, gestionnaire de programmes pour Teams, qui explique comment effectuer une recherche du journal d’audit pour Teams dans la Centre de sécurité et de conformité d’Office 365.

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
