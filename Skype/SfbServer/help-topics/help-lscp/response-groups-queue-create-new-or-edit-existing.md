---
title: File d’attente de réponse groupes créer ou modifier une existante
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: Files d’attente de la réponse groupe contiennent des appels à un groupe de réponse jusqu'à ce qu’un agent répond à l’appel.
ms.openlocfilehash: f5223aaca700c10a25631131db69a55de1362ddc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>File d’attente Response Group : création d’une file d’attente ou modification d’une file d’attente existante
 
Files d’attente de la réponse groupe contiennent des appels à un groupe de réponse jusqu'à ce qu’un agent répond à l’appel.
  
## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.
  
- **Nom** Chaque file d’attente doit avoir un nom. Tapez un nom descriptif pour la file d’attente.
    
- **Description** Ce champ est facultatif. Elle permet de fournir des détails supplémentaires sur la file d’attente.
    
- **Groupes** Sélectionnez les groupes de l’agent que vous souhaitez attribuer à la file d’attente. Cliquez sur **Sélectionner** pour ajouter des groupes de l’agent à la liste. Cliquez sur **Supprimer** pour supprimer le groupe sélectionné de l’agent à partir de la liste.
    
    Les flèches vers le haut et vers le bas déplacent un groupe d’agents sélectionné vers le haut et vers le bas de la liste. L’ordre des groupes de l’agent affecte l’ordre dans lequel Skype pour Business Server recherche un agent disponible. Ainsi, un agent disponible est recherché en premier dans le premier groupe répertorié, puis dans le deuxième groupe, etc.
    
- **Activer le délai d’attente de la file d’attente** Activez cette case à cocher pour spécifier une période maximale d’un appelant doit attendre un agent répond à l’appel en attente. Si vous sélectionnez cette option, vous devez également spécifier les éléments suivants :
    
  - **Délai d’attente (en secondes)** Sélectionnez ou tapez le nombre maximal de secondes pendant lesquelles qu'un appelant peut attendre avant un agent répond à l’appel.
    
  - **Appeler l’action** Sélectionnez l’action qui se produit lorsqu’un appel arrive à expiration. Les choix possibles sont :
    
  - **Déconnexion**
    
  - **Transférer à la messagerie vocale** Si vous sélectionnez cette option, dans **l’adresse de SIP**, tapez une adresse de messagerie vocale au format sip :<username> @ <domainname> (par exemple, sip:bob@contoso.com).
    
  - **Transférer à un numéro de téléphone** Si vous sélectionnez cette option, dans le **SIP adresse** tapez le numéro de téléphone au format sip :<number> @ <domainname> (par exemple, sip:+14255550121@contoso.com).
    
  - **Transférer à l’adresse SIP** Sélectionnez cette option pour transférer l’appel à un autre utilisateur. Dans **adresse de SIP**, tapez l’URI de l’utilisateur au format sip :<username>@<domainname>.
    
  - **Transférer à une autre file d’attente de** Si vous sélectionnez cette option, accédez à la file d’attente pour recevoir des appels lorsque le délai d’attente appels.
    
- **Activer le dépassement de la file d’attente** Activez cette case à cocher pour spécifier un nombre maximal d’appels de la file d’attente. Si vous sélectionnez cette option, vous devez également spécifier les éléments suivants :
    
  - **Nombre maximal d’appels** Sélectionnez ou tapez le nombre maximal d’appels de que la file d’attente.
    
  - **Transférer l’appel** Sélectionnez l’appel doit intervenir lorsque le seuil de dépassement de capacité de file d’attente est atteint.
    
  - **Appeler l’action** Sélectionnez l’action qui se produit lorsque le seuil de dépassement de capacité de file d’attente est atteint. Les choix possibles sont :
    
  - **Déconnexion**
    
  - **Transférer à la messagerie vocale** Si vous sélectionnez cette option, dans **l’adresse de SIP**, tapez une adresse de messagerie vocale au format sip :<username> @ <domainname> (par exemple, sip:bob@contoso.com).
    
  - **Transférer à un numéro de téléphone** Si vous sélectionnez cette option, dans le **SIP adresse** tapez le numéro de téléphone au format sip :<number> @ <domainname> (par exemple, sip:+14255550121@contoso.com).
    
  - **Transférer à l’adresse SIP** Sélectionnez cette option pour transférer l’appel à un autre utilisateur. Dans **adresse de SIP**, tapez l’URI de l’utilisateur au format sip :<username>@<domainname>.
    
  - **Transférer à une autre file d’attente de** Si vous sélectionnez cette option, accédez à la file d’attente qui est à recevoir des appels lorsque le seuil de dépassement de capacité de file d’attente est remplie.
    
Pour plus d’informations sur les fonctionnalités de groupe de la réponse de, afficher un [Plan pour l’application de groupe de réponse dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) dans la documentation de planification. Pour plus d’informations sur l’utilisation des files d’attente, voir [Gérer les files d’attente de réponse groupe](http://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) dans la documentation sur les opérations.
  

