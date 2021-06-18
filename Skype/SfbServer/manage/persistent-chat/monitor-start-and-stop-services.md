---
title: Surveiller, démarrer et arrêter les services de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Résumé : Découvrez comment démarrer, arrêter et surveiller les services de conversation permanente dans Skype Entreprise Server 2015.'
ms.openlocfilehash: 31285fe5f7eefaa6579f2891a4b29111324de22d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814134"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Surveiller, démarrer et arrêter les services de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment démarrer, arrêter et surveiller les services de conversation permanente dans Skype Entreprise Server 2015.
  
Les services de conversation permanente et les services de conformité de conversation permanente font partie de la topologie Skype Entreprise Server et peuvent donc être surveillés, arrêtés et démarrés à l’aide des cmdlets suivantes :
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |Retourne des informations détaillées sur les composants Skype Entreprise Server 2015 qui s’exécutent en tant que services Windows.  <br/> |
|start-CsWindowsService  <br/> |Démarre le service.  <br/> |
|stop-CsWindowsService  <br/> |Arrête le service.  <br/> |
   
> [!NOTE]
> La conversation permanente est disponible dans Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [La mise à niveau de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez migrer les utilisateurs nécessitant cette fonctionnalité vers Teams ou continuer à utiliser Skype Entreprise Server 2015. 

Pour plus d’informations sur l’utilisation des cmdlets, voir [Skype Entreprise Server 2015 Management Shell.](../management-shell.md)
  

