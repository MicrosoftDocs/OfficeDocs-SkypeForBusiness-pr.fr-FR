---
title: Gestion de la suppression de données archivées dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Résumé : Découvrez comment gérer la suppression définitive des données archivées pour Skype entreprise Server.'
ms.openlocfilehash: f168f7fe744ef388de246cbcd2dd9de0fc2ef805
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991609"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Gestion de la suppression de données archivées dans Skype entreprise Server

**Résumé :** Découvrez comment gérer la suppression définitive des données archivées pour Skype entreprise Server.
  
La base de données d’archivage n’est pas destinée à la conservation longue durée, et Skype entreprise Server ne fournit pas de solution de découverte électronique pour les données archivées, de sorte que les données doivent être déplacées vers un autre stockage. Skype entreprise Server fournit un outil d’exportation de session que vous pouvez utiliser pour exporter des données archivées dans les transcriptions de recherche. Vous devez définir quand exécuter la purge des données archivées et exportées. 
  
Pour plus d’informations sur l’exportation de données à l’aide de l’applet de passe **Export-CsArchivingData** , voir [exporter des données archivées dans Skype entreprise Server](export-archived-data.md).
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Gestion de la purge des données à l’aide du panneau de configuration

Pour gérer la purge des données archivées à l’aide du panneau de configuration :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.
    
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
    
La commande suivante, permet de purger toutes les données archivées, par exemple. Après l’exécution de la commande, Skype entreprise Server efface tous les enregistrements d’archivage antérieurs à la valeur spécifiée pour le paramètre KeepArchivingDataForDays. 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

La commande suivante limite la purge aux enregistrements archivés qui ont été exportés dans un fichier de données (à l’aide de l’applet de commande **Export-CSArchivingData**). Vous devez également définir le paramètre PurgeExportedArchivesOnly sur True ($True) :
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Après l’exécution de la commande, Skype entreprise Server purge uniquement les enregistrements qui répondent aux deux critères suivants : 1) dont la valeur est antérieure à celle spécifiée pour le paramètre KeepArchivingDataForDays. et 2) elles ont été exportées à l’aide de l’applet de passe **Export-CsArchivingData** .
  
Pour désactiver la purge automatique des enregistrements archivés, définissez le paramètre EnablePurging sur False ($False) :
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

L’exemple suivant utilise l’applet de commande **Invoke-CsArchivingDatabasePurge** pour purger tous les enregistrements de plus de 24 heures de la base de données d’archivage sur ATL-SQL-001.contoso.com. Pour garantir la suppression de tous les enregistrements, y compris les enregistrements qui n’ont pas été exportés, le paramètre PurgeExportedArchivesOnly est défini sur False ($False) :
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
