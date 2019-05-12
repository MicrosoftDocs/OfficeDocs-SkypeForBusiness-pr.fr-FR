---
title: Gérer la purge des données archivées dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Résumé : Découvrez comment gérer le vidage des données archivées de Skype pour Business Server.'
ms.openlocfilehash: e6bc7cf077a17a3f4f6eaaf9f3026d170ddacfbd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902839"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Gérer la purge des données archivées dans Skype pour Business Server

**Résumé :** Découvrez comment gérer le vidage des données archivées de Skype pour Business Server.
  
La base de données d’archivage n’est pas conçue pour la rétention à long terme et Skype pour Business Server ne fournit pas une solution d’e-discovery (recherche) pour les données archivées, afin que les données doivent être déplacés vers d’autres systèmes de stockage. Skype pour Business Server fournit un outil d’exportation de session que vous pouvez utiliser pour exporter des données archivées dans des transcriptions de recherche. Vous devez définir quand exécuter la purge des données archivées et exportées. 
  
Pour plus d’informations sur l’exportation de données à l’aide de l’applet de commande **Export-CsArchivingData** , voir [exporter des données archivées dans Skype pour Business Server](export-archived-data.md).
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Gestion de la purge des données à l’aide du panneau de configuration

Pour gérer la purge des données archivées à l’aide du panneau de configuration :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **Configuration de l’archivage**.
    
4. Cliquez sur le nom de la configuration de site, de pool ou globale appropriée dans la liste des configurations d’archivage, puis sur **Modifier**, sur **Afficher les détails** et procédez comme suit :
    
   - Pour activer le vidage, activez la case à cocher **Activer le vidage des données d’archivage** et effectuez l’une des actions suivantes :
    
     - Pour vider tous les enregistrements, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.
    
     - Pour ne purger que les données qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.
    
   - Pour désactiver le vidage, désactivez la case à cocher **Activer le vidage des données d’archivage**.
    
5. Cliquez sur **Valider**.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Gestion de la purge des données à l’aide de Windows PowerShell

Vous pouvez gérer la purge des données archivées à l’aide des applets de commande de Windows PowerShell :
  
- Utilisez l’applet de commande **Set-CsArchivingConfiguration** avec le paramètre EnablePurging pour activer ou désactiver la purge des données archivées.
    
- Utilisez l’applet **Invoke-CsArchivingDatabasePurge** pour purger manuellement les enregistrements de la base de données d’archivage.
    
La commande suivante, permet de purger toutes les données archivées, par exemple. Une fois que cette commande est exécutée, Skype pour Business Server supprime tous les enregistrements d’archivage antérieurs à la valeur spécifiée pour le paramètre KeepArchivingDataForDays. 
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

La commande suivante limite la purge aux enregistrements archivés qui ont été exportés dans un fichier de données (à l’aide de l’applet de commande **Export-CSArchivingData**). Vous devez également définir le paramètre PurgeExportedArchivesOnly sur True ($True) :
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Une fois que cette commande est exécutée, Skype pour Business Server ne purge que les enregistrements d’archivage qui répondent à deux critères : 1) ils sont antérieurs à la valeur spécifiée pour le paramètre KeepArchivingDataForDays ; et, 2) ils ont été exportés à l’aide de l’applet de commande **Export-CsArchivingData** .
  
Pour désactiver la purge automatique des enregistrements archivés, définissez le paramètre EnablePurging sur False ($False) :
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

L’exemple suivant utilise l’applet de commande **Invoke-CsArchivingDatabasePurge** pour vider tous les enregistrements plus de 24 heures à partir de la base de données d’archivage sur atl-sql-001.contoso.com. Pour garantir la suppression de tous les enregistrements, y compris les enregistrements qui n’ont pas été exportés, le paramètre PurgeExportedArchivesOnly est défini sur False ($False) :
  
```
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
