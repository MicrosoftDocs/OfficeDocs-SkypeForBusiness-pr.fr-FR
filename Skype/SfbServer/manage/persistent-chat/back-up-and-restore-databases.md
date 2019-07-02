---
title: Sauvegarde et restauration des bases de données de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Résumé: Découvrez comment sauvegarder et restaurer des bases de données serveur de chat permanent dans Skype entreprise Server 2015.'
ms.openlocfilehash: 0bb4895ef85ac9f38f2f9ef414769efcac6894b4
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35417959"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Sauvegarde et restauration des bases de données de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé:** Découvrez comment sauvegarder et restaurer des bases de données serveur de chat permanent dans Skype entreprise Server 2015.
  
Le serveur Chat permanent nécessite le logiciel de base de données SQL Server pour stocker des données de salle de conversation, telles que l’historique, le contenu, la configuration, la mise en service des utilisateurs et d’autres métadonnées pertinentes. De plus, si votre organisation a des réglementations qui nécessitent l’archivage de l’activité de conversation permanente et que le service de conformité facultatif est activé, le logiciel de base de données SQL Server est utilisé pour stocker les données de conformité, y compris le contenu et les événements de conversation, comme salle de réunion et de départ. Le contenu d’une salle de conversation est stocké dans la base de données de chat permanent (MGC). Les données de conformité sont conservées dans la base de données de conformité (mgccomp). Il s’agit de données vitales qui doivent être sauvegardées régulièrement. 
  
> [!NOTE]
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015. 

## <a name="back-up-the-databases"></a>Sauvegarde des bases de données

Il existe deux méthodes pour sauvegarder les données de conversation permanente. 
  
- Sauvegarde SQL Server
    
- L’applet de passe **Export-CsPersistentChatData** , qui exporte les données de chat permanent en tant que fichier
    
Les données créées à l’aide de la sauvegarde SQL Server nécessitent beaucoup plus d’espace disque (jusqu’à 20 fois plus) que celles créées par l’applet de commande **Export-CsPersistentChatData**, mais la sauvegarde SQL Server est sans doute une procédure plus familière.
  
Si vous souhaitez utiliser les procédures de sauvegarde SQL Server, reportez-vous à votre documentation SQL pour en savoir plus. 
  
Si vous souhaitez utiliser l’applet de commande **Export-CsPersistentChatData**, vous pouvez préciser la commande comme suit :
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

ou
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

Par exemple, la commande suivante exporte les données de conversation permanente de la base de données de conversation permanente située sur le serveur atl-sql-001.contoso.com ; les données exportées seront stockées dans le fichier C:\Logs\PersistentChatData.zip. Dans la mesure où le paramètre Level n’est pas spécifié, la commande exportera l’intégralité des informations de conversation permanente.
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>Restauration des bases de données

Le mode de restauration des données de conversation persistante dépend de la méthode que vous avez utilisée pour les sauvegarder. Si vous avez utilisé des procédures de sauvegarde SQL Server, vous devez utiliser des procédures de restauration SQL Server. Si vous avez utilisé l’applet de cmdlet **Export-CsPersistentChatData** pour sauvegarder les données de conversation permanente, vous devez utiliser l’applet de passe **Import-CsPersistentChatData** pour restaurer les données:
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

ou
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
