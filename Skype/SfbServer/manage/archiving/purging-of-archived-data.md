---
title: Gestion de la purge des données archivées dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Résumé : Apprenez à gérer la purge des données archivées pour Skype pour Business Server 2015.'
ms.openlocfilehash: caeddcd927c20f0622cbd45b6d93abb2bf5d6618
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server-2015"></a>Gestion de la purge des données archivées dans Skype Entreprise Server 2015

**Résumé :** Découvrez comment gérer la purge des données archivées pour Skype pour Business Server 2015.
  
La base de données d’archivage n’est pas conçue pour la rétention à long terme et Skype pour Business Server 2015 ne fournit pas une solution e-discovery (recherche) pour les données archivées, les données doivent être déplacés vers d’autres systèmes de stockage. Skype pour Business Server fournit un outil d’exportation de session que vous pouvez utiliser pour exporter des données archivées dans les relevés de notes de recherche. Vous devez définir quand exécuter la purge des données archivées et exportées. 
  
Pour plus d’informations sur l’exportation de données à l’aide de l’applet de commande de **CsArchivingData de l’exportation** , voir [exportation des données archivées dans Skype pour Business Server 2015](export-archived-data.md).
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Gestion de la purge des données à l’aide du panneau de configuration

Pour gérer la purge des données archivées à l’aide du panneau de configuration :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.
    
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
    
La commande suivante, permet de purger toutes les données archivées, par exemple. Après l’exécution de cette commande, Skype pour Business Server supprime tous les enregistrements d’archivage antérieures à la valeur spécifiée pour le paramètre KeepArchivingDataForDays. 
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

La commande suivante limite la purge aux enregistrements archivés qui ont été exportés dans un fichier de données (à l’aide de l’applet de commande **Export-CSArchivingData**). Vous devez également définir le paramètre PurgeExportedArchivesOnly sur True ($True) :
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Après l’exécution de cette commande, Skype pour Business Server supprime uniquement, l’archivage des enregistrements qui répondent aux deux critères : 1) qu’ils sont plus anciens que la valeur spécifiée pour le paramètre KeepArchivingDataForDays ; et 2) qu’ils ont été exportés à l’aide de l’applet de commande **Exportation-CsArchivingData** .
  
Pour désactiver la purge automatique des enregistrements archivés, définissez le paramètre EnablePurging sur False ($False) :
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

L’exemple suivant utilise l’applet de commande **Invoke-CsArchivingDatabasePurge** pour purger tous les enregistrements à plus de 24 heures à partir de la base de données d’archivage sur atl-sql-001.contoso.com. Pour vous assurer que tous les enregistrements sont supprimés, y compris les enregistrements qui n’ont pas été exportés, le paramètre PurgeExportedArchivesOnly est défini sur False ($False) :
  
```
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```