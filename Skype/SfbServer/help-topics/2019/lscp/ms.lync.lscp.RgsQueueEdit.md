---
title: File d’attente de groupes de réponses créer ou modifier une existant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: Files d’attente les appels vers un groupe de réponse jusqu'à ce qu’un agent répond à l’appel.
ms.openlocfilehash: cb1777a87e32baac6d2bbb13a692abcf59da5931
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891389"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>File d’attente Response Group : création d’une file d’attente ou modification d’une file d’attente existante

Files d’attente les appels vers un groupe de réponse jusqu'à ce qu’un agent répond à l’appel.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.

- **Nom** Chaque file d’attente doit avoir un nom. Tapez un nom descriptif pour la file d’attente.

- **Description** Ce champ est facultatif. Utilisez-le pour fournir plus d’informations sur la file d’attente.

- **Groupes** Sélectionnez les groupes d’agents que vous souhaitez attribuer à la file d’attente. Cliquez sur **Sélectionner** pour ajouter des groupes d’agents à la liste. Cliquez sur **Supprimer** pour supprimer le groupe d’agents sélectionné dans la liste.

    Les flèches vers le haut et vers le bas déplacent un groupe d’agents sélectionné vers le haut et vers le bas de la liste. L’ordre des groupes d’agents affecte l’ordre dans lequel Skype pour Business Server recherche un agent disponible. Ainsi, un agent disponible est recherché en premier dans le premier groupe répertorié, puis dans le deuxième groupe, etc.

- **Activer le délai d’expiration de la file d’attente** Activez cette case à cocher pour spécifier une durée maximale pour l’appelant doit attendre un agent répond à l’appel en attente. Si vous sélectionnez cette option, vous devez également spécifier les éléments suivants :

  - **Délai d’expiration (secondes)** Sélectionnez ou tapez le nombre maximal de secondes de que l’appelant peut attendre avant qu’un agent répond à l’appel.

  - **Action d’appel** Sélectionnez l’action qui se produit lorsqu’un appel arrive à expiration. Vos choix est les suivants :

  - **Déconnexion**

  - **Transférer vers la messagerie vocale** Si vous sélectionnez cette option, dans **adresse SIP**, tapez une adresse de messagerie vocale au format sip :<username> @ <domainname> (par exemple, sip:bob@contoso.com).

  - **Transférer au numéro de téléphone** Si vous sélectionnez cette option, dans **adresse SIP** tapez le numéro de téléphone au format sip :<number> @ <domainname> (par exemple, sip:+14255550121@contoso.com).

  - **Transférer à l’adresse SIP** Sélectionnez cette option pour transférer l’appel vers un autre utilisateur. Dans **adresse IP**, tapez l’URI de l’utilisateur au format sip :<username>@<domainname>.

  - **Transférer vers une autre file d’attente** Si vous sélectionnez cette option, accédez à la file d’attente qui est à recevoir des appels lorsque le délai d’attente les appels.

- **Activer le débordement de la file d’attente** Activez cette case à cocher pour spécifier un nombre maximal d’appels que la file d’attente. Si vous sélectionnez cette option, vous devez également spécifier les éléments suivants :

  - **Nombre maximal d’appels** Sélectionnez ou tapez le nombre maximal d’appels de que la file d’attente.

  - **Transférer l’appel** Sélectionnez l’appel d’effectuer une action lorsque le seuil de saturation de file d’attente est remplie.

  - **Action d’appel** Sélectionnez l’action qui se produit lorsque le seuil de saturation de file d’attente est remplie. Vos choix est les suivants :

  - **Déconnexion**

  - **Transférer vers la messagerie vocale** Si vous sélectionnez cette option, dans **adresse SIP**, tapez une adresse de messagerie vocale au format sip :<username> @ <domainname> (par exemple, sip:bob@contoso.com).

  - **Transférer au numéro de téléphone** Si vous sélectionnez cette option, dans **adresse SIP** tapez le numéro de téléphone au format sip :<number> @ <domainname> (par exemple, sip:+14255550121@contoso.com).

  - **Transférer à l’adresse SIP** Sélectionnez cette option pour transférer l’appel vers un autre utilisateur. Dans **adresse IP**, tapez l’URI de l’utilisateur au format sip :<username>@<domainname>.

  - **Transférer vers une autre file d’attente** Si vous sélectionnez cette option, accédez à la file d’attente qui recevra les appels lorsque le seuil de saturation de file d’attente est remplie.

Pour plus d’informations sur les fonctionnalités de Response Group, consultez [planification de l’application Response Group dans Skype pour Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) dans la documentation de planification. Pour plus d’informations sur l’utilisation des files d’attente, reportez-vous à la rubrique [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) de la documentation des opérations.


