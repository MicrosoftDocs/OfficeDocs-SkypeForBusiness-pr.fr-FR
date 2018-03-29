---
title: Correction ou mise à jour d’un serveur principal ou d’un serveur Standard Edition dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Résumé : Apprenez à installer une mise à jour ou un correctif sur un serveur principal dans Skype pour Business Server.'
ms.openlocfilehash: 14acff1aea501bf47dff95053259187570d2f990
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server-2015"></a>Correction ou mise à jour d’un serveur principal ou d’un serveur Standard Edition dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment installer une mise à jour ou un correctif sur un serveur principal dans Skype pour Business Server.
  
Cette rubrique explique comment installer une mise à jour sur une entreprise Edition serveur principal ou un serveur Standard Edition.
  
Si un serveur principal est hors service pendant au moins 30 minutes pendant que vous mettez à niveau il, les utilisateurs peuvent passer en mode de résilience. Lors de la mise à niveau est terminée et les serveurs principaux en a à nouveau connecté avec les serveurs frontaux dans le pool, les utilisateurs sont retournés toutes les fonctionnalités. Si la mise à niveau dure moins de 30 minutes, les utilisateurs ne sont pas affectés.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Pour mettre à jour un serveur principal ou un serveur Standard Edition

1. Connectez-vous au serveur que vous mettez à niveau en tant que membre du rôle CsAdministrator.
    
2. Téléchargez la mise à jour et extrayez-la sur le disque dur local.
    
3. Démarrer le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour entreprise 2015**, puis cliquez sur **Skype pour Business Server Management Shell**...
    
4. Arrêter Skype pour les services de serveur d’entreprise. À partir de la ligne de commande, tapez :
    
    ```
    Stop-CsWindowsService
    ```

5. Arrêtez les services World Wide Web. À partir de la ligne de commande, tapez :
    
    ```
    net stop w3svc
   ```

6. Fermez tous les Skype pour windows de Business Server Management Shell.
    
7. Installez la mise à jour.
    
8. Démarrer le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour entreprise 2015**, puis cliquez sur **Skype pour Business Server Management Shell**...
    
9. Arrêter Skype pour les services de serveur de l’entreprise pour détecter les assemblys -d du Global Assembly Cache (GAC). À partir de la ligne de commande, tapez :
    
    ```
    Stop-CsWindowsService
    ```

10. Redémarrez les services World Wide Web. À partir de la ligne de commande, tapez :
    
    ```
    net start w3svc
    ```

11. Appliquez les modifications apportées aux bases de données SQL Server en effectuant l’une des opérations suivantes :
    
    - Si c’est un serveur Enterprise Edition fin précédent et aucun COLOCALISÉES bases de données sur ce serveur, comme l’archivage ou les bases de données de suivi, puis tapez ce qui suit à une ligne de commande :
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Si c’est un serveur Enterprise Edition fin précédent et consolider des bases de données sont sur ce serveur, puis tapez ce qui suit à une ligne de commande :
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - S’il s’agit d’un serveur Standard Edition server, tapez ce qui suit à l’invite :
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```


