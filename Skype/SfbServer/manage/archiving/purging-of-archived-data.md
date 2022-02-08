---
title: Gérer la purge des données archivées dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Résumé : Découvrez comment gérer la purge des données archivées pour Skype Entreprise Server.'
ms.openlocfilehash: 9868277bc79a95b869383025da7e1c52aed35921
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395376"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Gérer la purge des données archivées dans Skype Entreprise Server

**Résumé :** Découvrez comment gérer la purge des données archivées pour Skype Entreprise Server.
  
La base de données d’archivage n’est pas destinée à une rétention à long terme et Skype Entreprise Server ne fournit pas de solution de découverte électronique (recherche) pour les données archivées, de sorte que les données doivent être déplacées vers un autre stockage. Skype Entreprise Server fournit un outil d’exportation de session que vous pouvez utiliser pour exporter des données archivées dans des transcriptions utilisables dans une recherche. Vous devez définir quand purger les données archivées et exportées. 
  
Pour plus d’informations sur l’exportation de données à l’aide de l’cmdlet **Export-CsArchivingData**, voir Exporter les données [archivées dans Skype Entreprise Server](export-archived-data.md).
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Gérer la purge des données à l’aide du Panneau de contrôle

Pour gérer la purge des données archivées à l’aide du Panneau de contrôle :
  
1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.
    
4. Cliquez sur le nom de la configuration appropriée (globale, du site ou du pool) dans la liste des configurations d’archivage, cliquez sur **Modifier**, sur **Afficher les détails**, puis procédez comme suit :
    
   - Pour activer le vidage, activez la case à cocher **Activer le vidage des données d’archivage** et effectuez l’une des actions suivantes :
    
     - Pour vider tous les enregistrements, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.
    
     - Pour ne purger que les données qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.
    
   - Pour désactiver le vidage, désactivez la case à cocher **Activer le vidage des données d’archivage**.
    
5. Cliquez sur **Valider**.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Gérer la purge des données à l’aide Windows PowerShell

Vous pouvez gérer la purge des données archivées à l’aide des cmdlets Windows PowerShell suivantes :
  
- **L’cmdlet Set-CsArchivingConfiguration** avec le paramètre EnablePurging vous permet d’activer ou de désactiver la purge des données archivées.
    
- **Invoke-CsArchivingDatabasePurge** vous permet de vider manuellement les enregistrements de la base de données d’archivage.
    
Par exemple, la commande suivante permet de purger toutes les données archivées. Une fois cette commande exécuté, Skype Entreprise Server tous les enregistrements d’archivage plus anciens que la valeur spécifiée pour le paramètre KeepArchivingDataForDays. 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

La commande suivante limite le purge aux enregistrements archivés qui ont été exportés vers un fichier de données (à l’aide de l’cmdlet **Export-CSArchivingData** ). Vous devez également définir le paramètre PurgeExportedArchivesOnly sur True ($True) :
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Une fois cette commande exécuté, Skype Entreprise Server purgera uniquement les enregistrements d’archivage qui répondent à deux critères : 1) ils sont plus anciens que la valeur spécifiée pour le paramètre KeepArchivingDataForDays ; et, 2) ils ont été exportés à l’aide de l’cmdlet **Export-CsArchivingData**.
  
Pour désactiver le  purge automatique des enregistrements d’archivage, définissez le paramètre EnablePurging sur False ($False) :
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

L’exemple suivant utilise l’cmdlet **Invoke-CsArchivingDatabasePurge** pour vider tous les enregistrements de plus de 24 heures de la base de données d’archivage sur atl-sql-001.contoso.com. Pour vous assurer que tous les enregistrements sont supprimés, y compris les enregistrements qui n’ont pas été exportés, le paramètre PurgeExportedArchivesOnly est définie sur False ($False) :
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
