---
title: Surveillance, lancement et arrête des services de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Résumé : Découvrez comment démarrer, arrêter et surveiller les services de conversation permanente dans Skype pour Business Server 2015.'
ms.openlocfilehash: 272ea0f4270b1109ff77b5d809472051705b6f10
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20991588"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Surveillance, lancement et arrête des services de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment démarrer, arrêter et surveiller les services de conversation permanente dans Skype pour Business Server 2015.
  
Les services de conversation permanente et conformité de conversation permanente font partie de la Skype pour la topologie du serveur d’entreprise et peut donc être surveillés, arrêté et démarré à l’aide des applets de commande suivantes :
  
|||
|:-----|:-----|
|Get-CsWindowsService  <br/> |Renvoie des informations détaillées sur Skype pour les composants Business Server 2015 qui s’exécutent en tant que services Windows.  <br/> |
|Start-CsWindowsService  <br/> |Démarre le service.  <br/> |
|Stop-CsWindowsService  <br/> |Arrête le service.  <br/> |
   
> [!NOTE]
> Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015. 

Pour plus d’informations sur la façon d’utiliser les applets de commande, voir [Skype pour Business Server 2015 Management Shell](../management-shell.md).
  

