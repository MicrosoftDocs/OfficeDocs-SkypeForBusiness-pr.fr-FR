---
title: 'Client mobile : créer ou modifier la configuration des notifications Push'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: Les notifications Push et le centre d’échange de notifications Push (PNCH) sont deux éléments clés de la fonctionnalité de mobilité. Une notification push correspond au processus dans lequel un message est envoyé au centre d’échanges de notifications push. Ce message y est conservé jusqu’à ce qu’il puisse être remis au client mobile ou que le délai d’expiration soit dépassé.
ms.openlocfilehash: ebc548658fad03af743acdaa25db4b5307549b4c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751113"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>Client mobile : Créer ou modifier une configuration des notifications push
 
Les notifications Push et le centre d’échange de notifications Push (PNCH) sont deux éléments clés de la fonctionnalité de mobilité. Une notification push correspond au processus dans lequel un message est envoyé au centre d’échanges de notifications push. Ce message y est conservé jusqu’à ce qu’il puisse être remis au client mobile ou que le délai d’expiration soit dépassé. 
  
> [!NOTE]
> Le délai est défini au centre d’échanges de notifications push et ne peut pas être configuré par l’utilisateur ni par l’administrateur de votre déploiement. 
  
Pour activer les notifications push, procédez comme suit :
  
1. **Étendue :** Notez l’étendue de cette stratégie. Il peut être **Global**, qui s’applique à tous les utilisateurs dans ce déploiement, ou **Site**, qui est uniquement les utilisateurs affectés à des serveurs d’accueil dans le site spécifié.
    
    > [!IMPORTANT]
    > Les paramètres de stratégie appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La priorité de la stratégie est la : la stratégie utilisateur (la plus influente) remplace une stratégie de site, puis une stratégie de site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet. 
  
2. Sélectionnez les services de notification push que vous voulez activer en cochant la case correspondante :
    
   - **Activer la notification Push De Microsoft** activera la notification Push au PNCH basé sur le cloud pour les Windows Phone l’application Skype Entreprise web
    
   - Activer **la notification Push Apple** activera la notification Push au PNCH Apple pour les appareils exécutant iOS d’Apple (par exemple, iPhone, iPad) et utilisant l’application Skype Entreprise
    
3. Une fois que vous avez terminé les modifications de la stratégie, cliquez sur **Valider** pour enregistrer ces modifications. Si vous avez besoin de supprimer les modifications apportées, sélectionnez **Annuler**. Aucune modification ne sera enregistrée dans la stratégie.
    

