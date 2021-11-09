---
title: Surveiller, démarrer et arrêter les services de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Résumé : Découvrez comment démarrer, arrêter et surveiller les services de conversation permanente dans Skype Entreprise Server 2015.'
ms.openlocfilehash: 9d25654a222b956fa5c8a1902e5d3a90674829e8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833380"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Surveiller, démarrer et arrêter les services de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment démarrer, arrêter et surveiller les services de conversation permanente dans Skype Entreprise Server 2015.
  
Les services de conversation permanente et les services de conformité de conversation permanente font partie de la topologie Skype Entreprise Server et peuvent donc être surveillés, arrêtés et démarrés à l’aide des cmdlets suivantes :
  
|Cmdlet|Fonction|
|:-----|:-----|
|get-CsWindowsService  <br/> |Retourne des informations détaillées sur Skype Entreprise Server 2015 qui s’exécutent en tant Windows services.  <br/> |
|start-CsWindowsService  <br/> |Démarre le service.  <br/> |
|stop-CsWindowsService  <br/> |Arrête le service.  <br/> |
   
> [!NOTE]
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015. 

Pour plus d’informations sur l’utilisation des cmdlets, voir [Skype Entreprise Server 2015 Management Shell](../management-shell.md).
  

