---
title: Correctifs ou mise à jour d’un serveur principal ou Standard Edition server dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Résumé : Découvrez comment installer une mise à jour ou un correctif sur un serveur principal Skype pour Business Server.'
ms.openlocfilehash: d00f740ef328abe7a58a61d831c4fcd0eae93fc8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911993"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Correctifs ou mise à jour d’un serveur principal ou Standard Edition server dans Skype pour Business Server
 
**Résumé :** Découvrez comment installer une mise à jour ou un correctif sur un serveur principal Skype pour Business Server.
  
Cette rubrique explique comment installer une mise à jour sur un serveur Enterprise Edition Back ou un serveur Standard Edition server.
  
Si un serveur principal est vers le bas au moins 30 minutes pendant que vous mettez à niveau il, les utilisateurs peuvent passer en mode résistance. Lorsque la mise à niveau est terminée et les serveurs principaux est connecté à nouveau avec les serveurs frontaux du pool, les utilisateurs sont renvoyées pour toutes les fonctionnalités. Si la mise à niveau dure moins de 30 minutes, les utilisateurs ne sont pas affectés.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Pour mettre à jour un serveur principal ou un serveur Standard Edition

1. Connectez-vous au serveur que vous mettez à niveau en tant que membre du rôle CsAdministrator.
    
2. Téléchargez la mise à jour et extrayez-la sur le disque dur local.
    
3. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour les entreprises**, puis cliquez sur **Skype pour Business Server Management Shell**...
    
4. Arrêtez Skype pour les services Business Server. À partir de la ligne de commande, tapez :
    
    ```
    Stop-CsWindowsService
    ```

5. Arrêtez les services World Wide Web. À partir de la ligne de commande, tapez :
    
    ```
    net stop w3svc
   ```

6. Fermez toutes les Skype pour windows Business Server Management Shell.
    
7. Installez la mise à jour.
    
8. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour les entreprises**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
9. Arrêtez Skype pour les services Business Server pour intercepter les assemblys -d Global Assembly Cache (GAC). À partir de la ligne de commande, tapez :
    
    ```
    Stop-CsWindowsService
    ```

10. Redémarrez les services World Wide Web. À partir de la ligne de commande, tapez :
    
    ```
    net start w3svc
    ```

11. Appliquez les modifications apportées aux bases de données SQL Server en effectuant l’une des opérations suivantes :
    
    - Si c’est un serveur Enterprise Edition fin et aucun des bases de données COLOCALISÉES sur ce serveur, telles que l’archivage ou les bases de données de surveillance, puis tapez ce qui suit sur la ligne de commande :
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Si c’est un serveur Enterprise Edition fin et il existe des bases de données COLOCALISÉES sur ce serveur, puis tapez ce qui suit sur la ligne de commande :
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - S’il s’agit d’un serveur Standard Edition server, tapez ce qui suit sur la ligne de commande :
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
