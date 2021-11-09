---
title: Numéro de téléphone non attribué
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: Les numéros non attribués sont des numéros de téléphone valides pour votre organisation mais qui ne sont pas attribués à un utilisateur ou un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.
ms.openlocfilehash: fa7fd55f0c0fae22643d0dde66cae32c2610bdcd
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834522"
---
# <a name="unassigned-phone-number"></a>Numéro de téléphone non attribué

> [!NOTE]
> Exchange La um reste disponible dans Skype Entreprise Server 2019 lorsque vous intégrez Skype Entreprise 2019 à Exchange 2013 ou Exchange 2016. En raison des modifications apportées à la prise en charge dans Exchange 2019, l’intégration de la Exchange de la Exchange est mise en avant au profit des fonctionnalités Messagerie vocale infonuagique et Cloud Standard automatique.

Les numéros non attribués sont des numéros de téléphone valides pour votre organisation mais qui ne sont pas attribués à un utilisateur ou un téléphone. Le tableau des numéros non attribués identifie le mode de traitement des appels vers les numéros non attribués.

La manière dont vous configurez la table des numéros non attribués dépend de la façon dont vous comptez l’utiliser. Vous pouvez configurer la table avec tous les numéros de poste valides de votre organisation, avec uniquement les numéros de poste non attribués ou avec une combinaison des deux types de numéros. La table des numéros non attribués peut comporter des numéros attribués et des numéros non attribués, mais elle appelée uniquement lorsqu’un appelant compose un numéro qui n’est pas attribué. Si vous intégrez tous les numéros de poste valides dans la table des numéros non attribués, vous pouvez spécifier la réponse si une personne quitte l’organisation, sans avoir à reconfigurer la table. Si vous intégrez des numéros de poste non attribués à la table, vous pouvez personnaliser la réponse à certains numéros. Par exemple, si vous modifiez le numéro de poste de votre bureau de service client, vous pouvez inclure l’ancien numéro dans la table et l’attribuer à une annonce qui indique le nouveau numéro.

> [!IMPORTANT]
> Avant de configurer la table des numéros non attribués, vous devez avoir défini une ou plusieurs annonces ou configuré un standard automatique de la messagerie unifiée Exchange.

La page **Numéro non attribué** affiche la liste des plages de numéros non attribués définies pour votre organisation.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Numéro non attribué** :

- Créer une nouvelle plage de numéros non attribués

- Modifier une plage de numéros non attribués existante

- Supprimer une plage de numéros non attribués

- Modifier l’ordre des plages de numéros non attribués pour déterminer la première action qui doit être appliquée à un appel entrant correspondant à un numéro non attribué.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste suivante décrit les commandes de la page.

- **Nouveau** Démarre une nouvelle plage de numéro non assignés.

- **Modifier** Ouvre la plage de numéro non assignées sélectionnée pour modification, sélectionne toutes les plages de numéro non assignées dans la liste ou supprime la plage de numéro non assignées sélectionnée.

- **Monter** Déplace la plage de numéro non spécifiés sélectionnée vers le haut dans la liste afin que Skype Entreprise Server la trouve plus tôt et applique l’action spécifiée avant d’appliquer les actions spécifiées pour les autres plages de la liste.

    > [!NOTE]
    > Skype Entreprise Server recherche de haut en bas dans la table des chiffres non signés et utilise la première plage qui correspond au numéro non assigné. Par exemple, si une plage spécifie une action de dernier recours, assurez-vous qu’elle se trouve en bas de la liste.

- **Déplacer vers le bas** Déplace la plage de numéro non assignés sélectionnée vers le bas dans la liste.

- **Valider tout** Enregistre toutes les modifications que vous avez apportées aux plages de numéro non assignés.

    > [!IMPORTANT]
    > Cette commande enregistre toutes les modifications que vous avez effectuées dans la page **Nouveau numéro non attribué** et dans la page **Modifier le numéro non attribué**.

- **Actualiser** Actualise la liste des plages de nombres non résignés.

La liste suivante décrit les champs de la page.

- **Nom** Nom unique qui identifie la plage de numéro non assignés.

- **État** Indique les plages de nombres qui ont été enregistrées dans la base de données et qui n’ont pas été enregistrées.

- **Plage de début** Numéro de début de la plage de numéro non signés.

- **Plage de fin** Numéro de fin de la plage de numéro non assignés.

- **Destination** ID de service du service d’application qui héberge l’application d’annonce qui gérera les appels entrants vers cette plage de numéros non assignés.

- **Annonce** Annonce à lire pour cette plage de numéros non signés.

Pour plus d’informations sur les fonctionnalités d’annonce, voir [Plan for the Announcement application in Skype Entreprise](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation. Pour plus d’informations sur l’utilisation de plages de numéros non attribués, voir [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) dans la documentation des opérations.