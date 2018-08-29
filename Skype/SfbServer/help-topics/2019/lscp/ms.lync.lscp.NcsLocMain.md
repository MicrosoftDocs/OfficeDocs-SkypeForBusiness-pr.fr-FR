---
title: Stratégie d’emplacement
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: Les stratégies d’emplacement déterminent si le service E9-1-1 (Enhanced 9-1-1) doit être activé et définissent son mode d’utilisation. Elles indiquent également la façon dont les informations d’emplacement sont traitées pour les utilisateurs et les contacts.
ms.openlocfilehash: a7528ea173d03714a8dc20c474d4e1f3d74a5bc2
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23245082"
---
# <a name="location-policy"></a>Stratégie d’emplacement

Les stratégies d’emplacement déterminent si le service E9-1-1 (Enhanced 9-1-1) doit être activé et définissent son mode d’utilisation. Elles indiquent également la façon dont les informations d’emplacement sont traitées pour les utilisateurs et les contacts.

Les stratégies d’emplacement incluent la stratégie globale, ainsi, éventuellement, qu’une ou plusieurs stratégies de site et utilisateur :

- **Stratégie globale :** La stratégie globale créée par défaut. Vous pouvez modifier la stratégie globale, mais vous ne pouvez pas le supprimer. Si vous essayez de supprimer la stratégie globale, tous les paramètres sont réinitialisées sur les valeurs par défaut.

- **(Facultatifs) des stratégies de site :** Vous pouvez créer des stratégies d’emplacement site un ou plusieurs, chacun d'entre eux s’applique à un site spécifique. Stratégies de site remplacent la stratégie globale.

- **Stratégies utilisateur (facultatifs) :** Vous pouvez créer des stratégies d’emplacement utilisateur un ou plusieurs, chacun d'entre eux s’applique à un utilisateur spécifique ou un groupe d’utilisateurs. Remplacent les stratégies utilisateur la stratégie globale et les stratégies de site.

> [!NOTE]
> Vous pouvez également attribuer des stratégies d’emplacement à des sites réseau, qui sont des groupes de sous-réseaux. Les stratégies d’emplacement attribuées aux sites réseau prévalent sur toutes les autres stratégies utilisateur. Pour plus d’informations sur l’attribution de stratégies d’emplacement aux sites du réseau à l’aide des applets de commande, voir [Ajouter une stratégie d’emplacement à un site réseau dans Skype pour Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md). Pour plus d’informations sur l’utilisation de Skype pour Business Server Control Panel pour affecter une stratégie d’emplacement à un site réseau, voir [Configuration des Sites réseau](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).

La page **Stratégie d’emplacement** affiche la liste de toutes les stratégies d’emplacement définies pour votre organisation.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Stratégie d’emplacement**, vous pouvez effectuer les tâches suivantes :

- Création d’une stratégie d’emplacement de site ou d’une stratégie d’emplacement utilisateur

- Modification de la stratégie globale, d’une stratégie de site ou d’une stratégie utilisateur existante

- Suppression d’une stratégie de site ou d’une stratégie utilisateur

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les commandes de la page.

- **Nouveau** Démarre une nouvelle stratégie d’emplacement de site ou d’une stratégie d’emplacement utilisateur.

- **Modifier** Ouvre la stratégie d’emplacement sélectionné pour le modifier, sélectionne toutes les stratégies d’emplacement dans la liste ou supprime la stratégie de site sélectionné ou utilisateur.

    > [!NOTE]
    > Pour la stratégie globale, l’option **Supprimer** restaure les valeurs par défaut des paramètres.

- **Actualiser** Actualise la liste des stratégies d’emplacement.

La liste ci-dessous décrit les champs de la page.

- **Nom** Identifie la stratégie d’emplacement.

- **Étendue** Identifie l’étendue de la stratégie d’emplacement : globale, site ou utilisateur.

- **E9-1-1** Vérifiez si les utilisateurs affectés cette stratégie d’emplacement sont activés pour E9-1-1.

- **Emplacement** Spécifie si les utilisateurs sont invités à entrer les informations d’emplacement lors de leur client inscrit avec Skype pour Business Server à un nouvel emplacement, et selon qu’ils voient une notification d’exclusion si elles ignorer l’invite sans saisir les informations d’emplacement.

- **Utilisation PSTN** Spécifie l’utilisation du réseau (PSTN) public commuté qui est utilisée pour déterminer l’itinéraire de communications vocales utilisé pour acheminer les appels d’urgence à partir de clients utilisant ce profil.

- **Nombre de E9-1-1** Spécifie le numéro qui est composé pour joindre les services d’urgence.

- **Masque E9-1-1** Spécifie un numéro qu’un utilisateur compose est ensuite converti dans le numéro d’urgence.

Pour plus d’informations sur les fonctionnalités de service d’urgence Enterprise Voice, voir [vue d’ensemble de E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) dans la documentation de planification. Pour plus d’informations sur l’utilisation des stratégies d’emplacement, voir [Configuration de stratégie d’emplacement](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) dans la documentation des opérations.


