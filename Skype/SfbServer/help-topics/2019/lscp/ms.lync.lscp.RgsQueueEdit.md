---
title: Mise en file d’attente de groupes de réponse créer un nouveau ou modifier un groupe existant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: Les files d’attente de groupe de réponse contiennent les appels d’un groupe de réponse tant qu’un agent ne répond pas à l’appel.
ms.openlocfilehash: 20a2066cbbece953e8f050919d8531f887f676ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292604"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>File d’attente Response Group : création d’une file d’attente ou modification d’une file d’attente existante

Les files d’attente de groupe de réponse contiennent les appels d’un groupe de réponse tant qu’un agent ne répond pas à l’appel.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.

- **Nom** Chaque file d’attente doit avoir un nom. Tapez un nom descriptif pour la file d’attente.

- **Description** Ce champ est facultatif. Utilisez-la pour fournir des informations supplémentaires sur la file d’attente.

- **Groupes** Sélectionnez les groupes d’agents que vous voulez affecter à la file d’attente. Cliquez sur **Sélectionner** pour ajouter des groupes d’agents à la liste. Cliquez sur **supprimer** pour supprimer le groupe d’agents sélectionné de la liste.

    Les flèches vers le haut et vers le bas déplacent un groupe d’agents sélectionné vers le haut et vers le bas de la liste. L’ordre des groupes d’agents affecte l’ordre dans lequel le serveur Skype entreprise recherche un agent disponible. Ainsi, un agent disponible est recherché en premier dans le premier groupe répertorié, puis dans le deuxième groupe, etc.

- **Temps d’activation de la file d’attente** Activez cette case à cocher pour spécifier un délai maximal pendant lequel l’appelant doit patienter avant d’avoir répondu à l’appel. Si vous sélectionnez cette option, vous devez également spécifier les éléments suivants:

  - **Période de délai (secondes)** Sélectionnez ou tapez le nombre maximal de secondes qu’un appelant peut patienter avant qu’un agent réponde à l’appel.

  - **Action appeler** Sélectionner l’action qui se produit lorsqu’un appel arrive à expiration. Les choix possibles sont les suivants:

  - **Déconnexion**

  - **Transférer vers la messagerie vocale** Si vous sélectionnez cette option, dans **adresse SIP**, tapez une adresse de messagerie vocale au format SIP:<username> @ <domainname> (par exemple, SIP:Bob@contoso.com).

  - **Transférer vers le numéro de téléphone** Si vous sélectionnez cette option, dans **adresse SIP** , tapez le numéro de téléphone au format SIP<number> @ <domainname> : (par exemple, SIP:+14255550121@contoso.com).

  - **Transférer vers l’adresse SIP** Sélectionnez cette option pour transférer l’appel vers un autre utilisateur. Dans **adresse SIP**, tapez l’URI de l’utilisateur au format SIP:<username>@<domainname>.

  - **Transférer vers une autre file d’attente** Si vous sélectionnez cette option, naviguez jusqu’à la file d’attente pour recevoir des appels lorsque le délai d’appels est écoulé.

- **Activer le dépassement de la file d’attente** Activez cette case à cocher pour spécifier un nombre maximal d’appels que la file d’attente peut contenir. Si vous sélectionnez cette option, vous devez également spécifier les éléments suivants:

  - **Nombre maximum d’appels** Sélectionnez ou tapez le nombre maximal d’appels que la file d’attente peut contenir.

  - **Transférer l’appel** Sélectionnez l’appel qui doit agir lorsque le seuil de dépassement de la file d’attente est atteint.

  - **Action appeler** Sélectionnez l’action qui se produit lorsque le seuil de dépassement de la file d’attente est atteint. Les choix possibles sont les suivants:

  - **Déconnexion**

  - **Transférer vers la messagerie vocale** Si vous sélectionnez cette option, dans **adresse SIP**, tapez une adresse de messagerie vocale au format SIP:<username> @ <domainname> (par exemple, SIP:Bob@contoso.com).

  - **Transférer vers le numéro de téléphone** Si vous sélectionnez cette option, dans **adresse SIP** , tapez le numéro de téléphone au format SIP<number> @ <domainname> : (par exemple, SIP:+14255550121@contoso.com).

  - **Transférer vers l’adresse SIP** Sélectionnez cette option pour transférer l’appel vers un autre utilisateur. Dans **adresse SIP**, tapez l’URI de l’utilisateur au format SIP:<username>@<domainname>.

  - **Transférer vers une autre file d’attente** Si vous sélectionnez cette option, naviguez jusqu’à la file d’attente pour recevoir des appels lorsque le seuil de dépassement de la file d’attente est atteint.

Pour plus d’informations sur les fonctionnalités et les fonctionnalités des groupes de réponse, voir [planifier l’application Response Group dans Skype entreprise Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) dans la documentation de planification. Pour plus d’informations sur l’utilisation des files d’attente, reportez-vous à la rubrique [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) de la documentation des opérations.


