---
title: Correctif ou mise à jour d’un serveur principal ou d’un serveur Standard Edition dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Résumé: Découvrez comment installer une mise à jour ou un correctif sur un serveur principal dans Skype entreprise Server.'
ms.openlocfilehash: b8a0280577147e37c52ab11aa3061541bae27610
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275121"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Correctif ou mise à jour d’un serveur principal ou d’un serveur Standard Edition dans Skype entreprise Server
 
**Résumé:** Découvrez comment installer une mise à jour ou un correctif sur un serveur principal dans Skype entreprise Server.
  
Cette rubrique explique comment installer une mise à jour sur un serveur principal Enterprise Edition ou un serveur Standard Edition Server.
  
Si un serveur principal est arrêté pendant au moins 30 minutes lors de la mise à niveau, les utilisateurs peuvent alors basculer en mode de résilience. Lorsque la mise à niveau est terminée et que les serveurs dorsaux sont à nouveau connectés avec les serveurs frontaux de la liste, les utilisateurs sont retournés à toutes les fonctionnalités. Si la mise à niveau dure moins de 30 minutes, les utilisateurs ne sont pas affectés.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Pour mettre à jour un serveur principal ou un serveur Standard Edition

1. Connectez-vous au serveur que vous mettez à niveau en tant que membre du rôle CsAdministrator.
    
2. Téléchargez la mise à jour et extrayez-la sur le disque dur local.
    
3. Démarrer Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
4. Arrêtez les services Skype entreprise Server. À partir de la ligne de commande, tapez :
    
    ```
    Stop-CsWindowsService
    ```

5. Arrêtez les services World Wide Web. À partir de la ligne de commande, tapez :
    
    ```
    net stop w3svc
   ```

6. Fermez toutes les fenêtres de Skype entreprise Server Management Shell.
    
7. Installez la mise à jour.
    
8. Démarrer Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
9. Arrêtez de nouveau les services Skype entreprise Server pour intercepter les assemblys du cache d’assembly global. À partir de la ligne de commande, tapez :
    
    ```
    Stop-CsWindowsService
    ```

10. Redémarrez les services World Wide Web. À partir de la ligne de commande, tapez :
    
    ```
    net start w3svc
    ```

11. Appliquez les modifications apportées aux bases de données SQL Server en effectuant l’une des opérations suivantes :
    
    - S’il s’agit d’un serveur principal Enterprise Edition et qu’il n’y a pas de bases de données colocalisées sur ce serveur, telles que des bases de données d’archivage ou de surveillance, tapez les informations suivantes dans une ligne de commande:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - S’il s’agit d’une base de données serveur principal de la version Enterprise Edition et de bases de données colocalisées sur ce serveur, tapez les informations suivantes à partir de la ligne de commande suivante:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - S’il s’agit d’un serveur Standard Edition Server, tapez les informations suivantes dans une ligne de commande:
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
