---
title: Numéro de téléphone non attribué
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.
ms.openlocfilehash: 910b83f18350bc2a26da281f2e0660e8aa8913b9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690389"
---
# <a name="unassigned-phone-number"></a>Numéro de téléphone non attribué

> [!NOTE]
> La messagerie unifiée Exchange reste disponible dans Skype entreprise Server 2019 lorsque vous intégrez Skype entreprise 2019 avec Exchange 2013 ou Exchange 2016. En raison des modifications apportées à la prise en charge dans Exchange 2019, l’intégration de la messagerie unifiée Exchange est mise en évidence dans les fonctionnalités de messagerie vocale et de standard automatique Cloud.

Les numéros non attribués sont des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.

La manière dont vous configurez la table des numéros non attribués dépend de l’utilisation envisagée. Vous pouvez configurer la table avec toutes les numéros de poste valides de votre organisation, avec uniquement les numéros de poste non attribués ou avec une combinaison des deux types de numéro. La table des numéros non attribués peut comporter des numéros attribués et des numéros non attribués, mais elle n’est appelée que lorsqu’un appelant compose un numéro qui n’est pas attribué. Si vous intégrez tous les numéros de poste valides dans la table des numéros non attribués, vous pouvez spécifier la réponse si une personne quitte l’organisation, sans avoir à reconfigurer la table. Si vous intégrez des numéros de poste non attribués à la table, vous pouvez personnaliser la réponse à certains numéros. Par exemple, si vous modifiez le numéro de poste de votre bureau de service client, vous pouvez inclure l’ancien numéro dans la table et l’attribuer à une annonce qui indique le nouveau numéro.

> [!IMPORTANT]
> Avant de configurer la table des numéros non attribués, vous devez avoir défini une ou plusieurs annonces ou configuré un standard automatique de la messagerie unifiée Exchange.

La page **Numéro non attribué** affiche la liste des plages de numéros non attribués définies pour votre organisation.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Numéro non attribué**, vous pouvez effectuer les tâches suivantes :

- Création d’une plage de numéros non attribués

- Modification d’une plage de numéros non attribués existante

- Suppression d’une plage de numéros non attribués

- Modification de l’ordre des plages de numéros non attribués pour déterminer la première action à appliquer à un appel entrant correspondant à un numéro non attribué.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les commandes de la page.

- **Nouvelle** Commence une nouvelle plage de numéros non attribués.

- **Modifier** Ouvre la plage de numéros non attribués sélectionnée pour modification, sélectionne toutes les plages de nombres non attribués dans la liste, ou supprime la plage de numéros non attribués sélectionnée.

- **Monter** Déplace la plage de numéros non attribués sélectionnés vers le haut dans la liste de telle sorte que Skype entreprise Server le trouve plus tôt et applique l’action spécifiée avant d’appliquer des actions spécifiées pour d’autres plages dans la liste.

    > [!NOTE]
    > Skype entreprise Server effectue une recherche dans la table des numéros non attribués de haut en bas, et utilise la première plage qui correspond au numéro non attribué. Par exemple, si une plage spécifie une action de dernier recours, assurez-vous qu’elle se trouve en bas de la liste.

- **Descendre** Déplace la plage de nombres non affectées sélectionnée de la liste vers le bas.

- **Valider tout** Enregistre toutes les modifications que vous avez apportées aux plages de nombres non affectées.

    > [!IMPORTANT]
    > Cette commande enregistre toutes les modifications apportées dans la page **Nouveau numéro non attribué** et dans la page **Modifier le numéro non attribué**.

- **Actualiser** Actualise la liste des plages de nombres non affectées.

La liste ci-dessous décrit les champs de la page.

- **Nom** Nom unique identifiant la plage de nombres non attribués.

- **État** Indique les plages de nombres qui ont été enregistrées dans la base de données et celles qui ne le sont pas.

- **Plage de début** Le numéro de début de la plage de nombres non attribués.

- **Plage de fin** Le numéro de fin de la plage de nombres non attribués.

- **Destination (destination** ) ID de service du service d’application qui héberge l’application d’annonce qui traitera les appels entrants de cette plage de numéros non attribués.

- **Annonce** Annonce qui sera lue pour cette série de numéros non attribués.

Pour plus d’informations sur les fonctionnalités et les fonctionnalités d’annonce, voir [planifier l’application d’annonce dans Skype entreprise](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) dans la documentation de planification. Pour plus d’informations sur l’utilisation de plages de numéros non attribués, reportez-vous à la rubrique [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) de la documentation des opérations.


