---
title: Sauvegarde et restauration des bases de données de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Résumé : Apprenez à sauvegarder et restaurer des bases de données de serveur de conversation permanents dans Skype pour Business Server 2015.'
ms.openlocfilehash: 419085219ea995c680fe31fcca3597a884ceba5d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Sauvegarde et restauration des bases de données de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment sauvegarder et restaurer des bases de données de serveur de conversation permanents dans Skype pour Business Server 2015.
  
Serveur de conversation persistant nécessite un logiciel de base de données SQL Server pour stocker les données de salle de conversation, par exemple l’historique contenu, configuration, mise en service de l’utilisateur et autres métadonnées pertinentes. En outre, si votre organisation dispose d’une réglementation qui nécessitent l’activité de conversation permanent à archiver, et le service de mise en conformité facultatif est activé, logiciel de base de données SQL Server est utilisé pour stocker les données de la conformité, y compris le contenu de la conversation et d’événements, tels que rejoindre / quitter des salles. Contenu de la salle de conversation est stocké dans la base de données Chat persistant (mgc). Les données de conformité sont conservées dans la base de données de conformité (mgccomp). Il s’agit de données vitales qui doivent être sauvegardées régulièrement. 
  
## <a name="back-up-the-databases"></a>Sauvegarde des bases de données

Il existe deux façons de sauvegarde des données de conversation permanent. 
  
- Sauvegarde SQL Server
    
- L’applet de commande **Exportation-CsPersistentChatData** , qui exporte des données de Chat persistant sous la forme d’un fichier
    
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

Comment vous restaurez vos données de conversation permanent dépend de la méthode qui vous permet de sauvegarder. Si vous avez utilisé des procédures de sauvegarde SQL Server, vous devez utiliser des procédures de restauration SQL Server. Si vous avez utilisé l’applet de commande de **CsPersistentChatData à l’exportation** pour sauvegarder les données de Chat permanente, vous devez utiliser la cmdlet **Import-CsPersistentChatData** pour restaurer les données :
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

ou
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```


