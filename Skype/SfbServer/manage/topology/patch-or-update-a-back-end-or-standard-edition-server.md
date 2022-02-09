---
title: Patch or update a Back End Server or Édition Standard server in Skype Entreprise Server
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
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Résumé : Découvrez comment installer une mise à jour ou un correctif sur un serveur principal dans Skype Entreprise Server.'
ms.openlocfilehash: 69c597aae05950d38b78c8e84d46165a68fd8959
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397658"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Patch or update a Back End Server or Édition Standard server in Skype Entreprise Server
 
**Résumé :** Découvrez comment installer une mise à jour ou un correctif sur un serveur principal dans Skype Entreprise Server.
  
Cette rubrique explique comment installer une mise à jour sur un serveur Êdition Entreprise principal ou un serveur Édition Standard serveur principal.
  
Si un serveur principal est arrêté durant au moins 30 minutes lors de sa mise à niveau, les utilisateurs peuvent être placés en mode Résilience. Lorsque la mise à mise à niveau est terminée et que les serveurs principaux sont encore connectés aux serveurs frontaux du pool, les utilisateurs repassent en fonctionnalité complète. Si la mise à niveau dure moins de 30 minutes, les utilisateurs ne seront pas affectés.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Pour mettre à jour un serveur principal ou un Édition Standard serveur principal

1. Connectez-vous au serveur que vous mettez à niveau en tant que membre du rôle CsAdministrator.
    
2. Téléchargez la mise à jour et extrayez-la sur le disque dur local.
    
3. Démarrez l Skype Entreprise Server Management Shell : cliquez sur Démarrer **, sur** Tous les **programmes, sur** **Skype Entreprise**, puis sur Skype Entreprise Server **Management Shell**.
    
4. Arrêtez Skype Entreprise Server services. À partir de la ligne de commande, tapez :
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. Arrêtez le service World Wide Web. À partir de la ligne de commande, tapez :
    
    ```PowerShell
    net stop w3svc
   ```

6. Fermez toutes les fenêtres Skype Entreprise Server Management Shell.
    
7. Installez la mise à jour.
    
8. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise**, puis sur Skype Entreprise Server **Management Shell**.
    
9. Arrêtez Skype Entreprise Server services pour capturer les assemblys GAC (Global Assembly Cache) -d. À partir de la ligne de commande, tapez :
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. Redémarrez le service World Wide Web. À partir de la ligne de commande, tapez :
    
    ```PowerShell
    net start w3svc
    ```

11. Appliquez les modifications apportées aux bases SQL Server données en faisant l’une des choses suivantes :
    
    - S’il s’agit d’un serveur principal Êdition Entreprise et qu’il n’y a pas de bases de données cingl es sur ce serveur, telles que les bases de données d’archivage ou de surveillance, tapez ce qui suit sur une ligne de commande :
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - S’il s’agit d Êdition Entreprise serveur principal et qu’il existe des bases de données c c colloquées sur ce serveur, tapez ce qui suit sur une ligne de commande :
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - S’il s’agit d Édition Standard serveur, tapez ce qui suit sur une ligne de commande :
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
