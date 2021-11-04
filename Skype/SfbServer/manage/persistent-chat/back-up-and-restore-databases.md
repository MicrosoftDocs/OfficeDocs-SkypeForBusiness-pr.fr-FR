---
title: Back up and restore Persistent Chat databases in Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Résumé : Découvrez comment back up and restore Persistent Chat Server databases in Skype Entreprise Server 2015.'
ms.openlocfilehash: 0f875fd62eab26873b8dcc3617de709a397f4ba8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762342"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>Back up and restore Persistent Chat databases in Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment back up and restore Persistent Chat Server databases in Skype Entreprise Server 2015.
  
Le serveur de conversation permanente SQL Server un logiciel de base de données pour stocker les données de salle de conversation, telles que l’historique et le contenu, la configuration, la mise en service des utilisateurs et d’autres métadonnées pertinentes. En outre, si votre organisation a des réglementations qui exigent l’archivage de l’activité de conversation permanente et que le service de conformité facultatif est activé, le logiciel de base de données SQL Server est utilisé pour stocker les données de conformité, y compris le contenu et les événements de conversation, tels que la jointation et la sortie de salles. Le contenu de la salle de conversation est stocké dans la base de données de conversation permanente (mgc). Les données de conformité sont stockées dans la base de données de conformité (mgccomp). Il s’agit de données critiques qui doivent être régulièrement backed. 
  
> [!NOTE]
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015. 

## <a name="back-up-the-databases"></a>Back up the databases

Il existe deux façons de la backing up Persistent Chat data. 
  
- SQL Server Sauvegarde
    
- Cmdlet **Export-CsPersistentChatData,** qui exporte les données de conversation permanente en tant que fichier
    
Les données créées à l’aide d’une sauvegarde SQL Server nécessitent beaucoup plus d’espace disque (20 fois plus éventuellement) que celles créées par **l';export-CsPersistentChatData,** mais la sauvegarde SQL Server est probablement une procédure que vous connaissez déjà.
  
Si vous souhaitez utiliser des procédures SQL Server de sauvegarde, consultez la documentation de votre SQL pour plus d’informations. 
  
Si vous souhaitez utiliser l’cmdlet **Export-CsPersistentChatData,** vous pouvez spécifier la commande comme suit :
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

ou
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

Par exemple, la commande suivante exporte les données de conversation permanente à partir de la base de données de conversation permanente située sur le serveur atl-sql-001.contoso.com ; les données exportées sont stockées dans le fichier C:\Logs\PersistentChatData.zip. Étant donné que le paramètre Level n’a pas été spécifié, la commande exporte entièrement les informations de conversation permanente :
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>Restaurer les bases de données

La façon dont vous restituer vos données de conversation permanente dépend de la méthode que vous avez utilisée pour les restaurer. Si vous avez utilisé SQL Server procédures de sauvegarde, vous devez utiliser SQL Server de restauration automatique. Si vous avez utilisé l’cmdlet **Export-CsPersistentChatData** pour la restauration des données de conversation permanente, vous devez utiliser l’cmdlet **Import-CsPersistentChatData** pour restaurer les données :
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

ou
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
