---
title: Stratégie d’emplacement
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: Les stratégies d’emplacement déterminent si le service E9-1-1 (Enhanced 9-1-1) doit être activé et définissent son mode d’utilisation. Elles indiquent également la façon dont les informations d’emplacement sont traitées pour les utilisateurs et les contacts.
ms.openlocfilehash: e780256ba025328c6a84d709aaa4c6f522b219df
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700099"
---
# <a name="location-policy"></a>Stratégie d’emplacement

Les stratégies d’emplacement déterminent si le service E9-1-1 (Enhanced 9-1-1) doit être activé et définissent son mode d’utilisation. Elles indiquent également la façon dont les informations d’emplacement sont traitées pour les utilisateurs et les contacts.

Les stratégies d’emplacement incluent la stratégie globale, ainsi, éventuellement, qu’une ou plusieurs stratégies de site et utilisateur :

- **Politique globale :** La stratégie globale est créée par défaut. Vous pouvez modifier la stratégie globale sans pouvoir la supprimer. Si vous tentez de supprimer la stratégie globale, tous les paramètres sont réinitialisés aux valeurs par défaut.

- **Stratégies de site (facultatif) :** Vous pouvez créer une ou plusieurs stratégies d’emplacement de site qui s’appliquent à un site spécifique. Les stratégies de site remplacent la stratégie globale.

- **Stratégies utilisateur (facultatif) :** Vous pouvez créer une ou plusieurs stratégies d’emplacement utilisateur, qui s’appliquent à un utilisateur ou à un groupe d’utilisateurs spécifiques. Les stratégies utilisateur remplacent la stratégie globale et les stratégies de site.

> [!NOTE]
> Vous pouvez également attribuer des stratégies d’emplacement à des sites réseau, qui sont des groupes de sous-réseaux. Les stratégies d’emplacement attribuées aux sites réseau prévalent sur toutes les autres stratégies utilisateur. Pour plus d’informations sur l’attribution de stratégies d’emplacement aux sites réseau à l’aide d’applets de connexion, voir [Ajouter une stratégie d’emplacement à un site réseau dans Skype entreprise Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md). Pour plus d’informations sur l’utilisation du panneau de configuration Skype entreprise Server pour assigner une stratégie d’emplacement à un site réseau, voir [configurer les sites réseau](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).

La page **Stratégie d’emplacement** affiche la liste de toutes les stratégies d’emplacement définies pour votre organisation.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Stratégie d’emplacement**, vous pouvez effectuer les tâches suivantes :

- Création d’une stratégie d’emplacement de site ou d’une stratégie d’emplacement utilisateur

- Modification de la stratégie globale, d’une stratégie de site ou d’une stratégie utilisateur existante

- Suppression d’une stratégie de site ou d’une stratégie utilisateur

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les commandes de la page.

- **Nouvelle** Démarre une nouvelle stratégie d’emplacement du site ou une nouvelle stratégie d’emplacement utilisateur.

- **Modifier** Ouvre la stratégie d’emplacement sélectionnée pour la modifier, sélectionne toutes les stratégies d’emplacement dans la liste, ou supprime la stratégie de site ou la stratégie d’utilisateur sélectionnée.

    > [!NOTE]
    > Pour la stratégie globale, l’option **Supprimer** restaure les valeurs par défaut des paramètres.

- **Actualiser** Actualise la liste des stratégies d’emplacement.

La liste ci-dessous décrit les champs de la page.

- **Nom** Identifie la stratégie d’emplacement.

- **Scope** Identifie l’étendue de la stratégie d’emplacement : global, site ou utilisateur.

- **E9-1-1** Activé si les utilisateurs auxquels cette stratégie d’emplacement est affectée sont activés pour E9-1-1.

- **Emplacement** Spécifie si les utilisateurs sont invités à entrer des informations d’emplacement lorsque le client s’inscrit à Skype entreprise Server à un nouvel emplacement, et qu’ils voient une exclusion de responsabilité s’ils ignorent l’invite sans entrer d’informations d’emplacement.

- **Utilisation PSTN** Spécifie l’utilisation de réseau téléphonique commuté (PSTN) qui est utilisée pour déterminer l’itinéraire vocal utilisé pour diriger les appels d’urgence de clients à l’aide de ce profil.

- **E9-1-1 nombre** Spécifie le numéro numéroté pour contacter les services d’urgence.

- **E9-1-1 Mask** Spécifie un numéro qu’un utilisateur compose puis traduit par le numéro de téléphone d’urgence.

Pour plus d’informations sur les fonctionnalités et les fonctionnalités du service d’urgence entreprise voix entreprise, voir [vue d’ensemble de E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) dans la documentation de planification. Pour plus d’informations sur l’utilisation des stratégies d’emplacement, reportez-vous à la rubrique [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) de la documentation des opérations.


