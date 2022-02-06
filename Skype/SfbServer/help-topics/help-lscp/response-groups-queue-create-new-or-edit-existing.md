---
title: 'File d’attente Response Groups : création d’une file d’attente ou modification d’une file d’attente existante'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: Les files d’attente Response Group tiennent les appels à un groupe Response Group jusqu’à ce qu’un agent réponde à l’appel.
---

# <a name="response-groups-queue-create-new-or-edit-existing"></a>File d’attente des services Response Groups : création d’une nouvelle ou modification d’une file existante

Les files d’attente Response Group tiennent les appels à un groupe Response Group jusqu’à ce qu’un agent réponde à l’appel.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste suivante décrit les champs de la page.

- **Nom** Chaque file d’attente doit avoir un nom. Tapez un nom descriptif pour la file d’attente.

- **Description** Ce champ est facultatif. Utilisez-le pour fournir des détails supplémentaires sur la file d’attente.

- **Groupes** Sélectionnez les groupes d’agents que vous souhaitez affecter à la file d’attente. Cliquez **sur Sélectionner** pour ajouter des groupes d’agents à la liste. Cliquez **sur Supprimer** pour supprimer le groupe d’agents sélectionné de la liste.

    Les flèches vers le haut et vers le bas déplacent un groupe d’agents sélectionné vers le haut et vers le bas dans la liste. L’ordre des groupes d’agents affecte l’ordre dans lequel Skype Entreprise Server recherche un agent disponible. Ainsi, un agent disponible est recherché en premier dans le premier groupe répertorié, puis dans le deuxième groupe, etc.

- **Activer le délai d’attente de file d’attente** Cochez cette case pour spécifier une durée maximale pendant combien de temps un appelant doit attendre en attente avant qu’un agent réponde à l’appel. Si vous sélectionnez cette option, vous devez également spécifier les options suivantes :

  - **Délai d’attente (secondes)** Sélectionnez ou tapez le nombre maximal de secondes qu’un appelant peut attendre avant qu’un agent réponde à l’appel.

  - **Action d’appel** Sélectionnez l’action qui se produit lorsqu’un appel arrive à son moment d’attente. Vous avez le choix entre :

  - **Disconnect**

  - **Forward to voice mail** Si vous sélectionnez cette option, dans l’adresse **SIP**, tapez une adresse de messagerie vocale au format sip :\<username>@\<domainname> (par exemple, sip:bob@contoso.com).

  - **Forward to telephone number** Si vous sélectionnez cette option, dans l’adresse **SIP** , tapez le numéro de téléphone au format sip (\<number>@\<domainname> par exemple, sip:+14255550121@contoso.com).

  - **Passer à l’adresse SIP** Sélectionnez cette option pour que l’appel soit transmis à un autre utilisateur. Dans **l’adresse SIP**, tapez l’URI de l’utilisateur au format sip:\<username>@\<domainname>.

  - **Forward to another queue** Si vous sélectionnez cette option, accédez à la file d’attente qui doit recevoir les appels au moment où les appels ont été mis à l’heure d’attente.

- **Activer le dépassement de la file d’attente** Cochez cette case pour spécifier un nombre maximal d’appels que la file d’attente peut contenir. Si vous sélectionnez cette option, vous devez également spécifier les options suivantes :

  - **Nombre maximal d’appels** Sélectionnez ou tapez le nombre maximal d’appels que la file d’attente peut contenir.

  - **Forward the call** Sélectionnez l’appel à prendre en compte lorsque le seuil de dépassement de la file d’attente est atteint.

  - **Action d’appel** Sélectionnez l’action qui se produit lorsque le seuil de dépassement de la file d’attente est atteint. Vos choix est les suivants :

  - **Disconnect**

  - **Forward to voice mail** Si vous sélectionnez cette option, dans l’adresse **SIP**, tapez une adresse de messagerie vocale au format sip :\<username>@\<domainname> (par exemple, sip:bob@contoso.com).

  - **Forward to telephone number** Si vous sélectionnez cette option, dans l’adresse **SIP** , tapez le numéro de téléphone au format sip (\<number>@\<domainname> par exemple, sip:+14255550121@contoso.com).

  - **Passer à l’adresse SIP** Sélectionnez cette option pour que l’appel soit transmis à un autre utilisateur. Dans **l’adresse SIP**, tapez l’URI de l’utilisateur au format sip:\<username>@\<domainname>.

  - **Forward to another queue** Si vous sélectionnez cette option, accédez à la file d’attente qui doit recevoir des appels lorsque le seuil de dépassement de la file d’attente est atteint.

Pour plus d’informations sur les fonctionnalités de Response Group, voir [Plan for the Response Group application in Skype Entreprise Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation. Pour plus d’informations sur l’utilisation des files d’attente, voir [Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues) dans la documentation des opérations.