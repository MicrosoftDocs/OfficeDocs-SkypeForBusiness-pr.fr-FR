---
title: Gérer les services pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: Cet article explique comment gérer les services en cours d’exécution dans Skype Entreprise Server topologie.
ms.openlocfilehash: 3bb4092d2538bc994de3f71467cb03aedf8dc302
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856671"
---
# <a name="manage-services-for-skype-for-business-server"></a>Gérer les services pour Skype Entreprise Server

Cet article explique comment gérer les services en cours d’exécution dans Skype Entreprise Server topologie.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Afficher la liste des ordinateurs exécutant Skype Entreprise Server
<a name="view_list"> </a>

Vous pouvez utiliser Skype Entreprise Server panneau de commande pour afficher la liste de tous les ordinateurs qui exécutent des Skype Entreprise Server dans votre topologie et voir l’état du service de chacun d’eux. Vous pouvez trier la liste par ordinateur, pool ou site. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>Pour afficher la liste des ordinateurs exécutant Skype Entreprise Server

1. À partir d’un compte d’utilisateur affecté à l’un des rôles d’administration prédéfin Skype Entreprise Server, connectez-vous à n’importe quel ordinateur de votre déploiement interne. Pour plus d’informations sur les rôles d’administration prédéfin Skype Entreprise Server, voir **Planning for Role-Based Access Control**.   
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.   
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.   
4. Dans la page **Statut**, effectuez l’une des opérations suivantes selon vos besoins :
   - Triez la liste en cliquant sur le titre de colonne **Ordinateur**, **Pool** ou **Site**, puis en cliquant sur la flèche vers le haut ou vers le bas. 
   - Cliquez sur **Actualiser** pour afficher la liste la plus à jour.  
   - Recherchez un ordinateur spécifique en tapant son nom dans le champ de recherche.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>Afficher l’état des services en cours d’exécution sur Skype Entreprise serveur
<a name="view-status"> </a>

Vous pouvez utiliser Skype Entreprise Server Panneau de Skype Entreprise Server pour afficher tous les services qui s’exécutent sur un ordinateur spécifique dans votre topologie Skype Entreprise Server et afficher l’état de chaque service.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>Pour afficher l’état des services en cours d’exécution sur un ordinateur

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
3. Dans la barre de navigation de gauche, cliquez sur **Topologie.** 
4. Dans la page **État,** tiez ou recherchez la liste, si nécessaire, pour trouver l’ordinateur qui vous intéresse, puis cliquez sur le nom de l’ordinateur.
5. Effectuez l’une des opérations suivantes :
   - Pour consulter le dernier état des services en cours d’exécution sur l’ordinateur, cliquez **sur Obtenir l’état du service.**
   - Pour voir la liste des services spécifiques en cours d’exécution sur l’ordinateur et l’état de chaque service, cliquez sur Propriétés, puis cliquez sur **Fermer** pour revenir à la liste.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Affichage de l’état du service Windows cmdlets PowerShell

Vous pouvez également afficher l’état du service à l’Windows PowerShell et l’cmdlet **Get-CsWindowsService.** Vous pouvez exécuter cette applet de commande à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype Entreprise Server, voir [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Le processus est le même dans Skype Entreprise Server.
  
### <a name="to-view-service-status"></a>Pour afficher l’état du service

Pour afficher l’état du service sur un ordinateur, tapez une commande semblable à la suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Cette commande renvoie des informations comme celles-ci :
  
|**RoleName**|**État**|
|:-----|:-----|
|{W3SVC}  <br/> |En cours d’exécution  <br/> |
|{CentralManagement}  <br/> | En cours d’exécution <br/> |
|{ClsAgent}  <br/> |En cours d’exécution  <br/> |
|{Registrar, UserServer, EdgeServer}  <br/> |En cours d’exécution  <br/> |
|{ApplicationServer}  <br/> |En cours d’exécution  <br/> |
|{ConferencingServer}  <br/> |En cours d’exécution  <br/> |
|{MediationServer}  <br/> |En cours d’exécution  <br/> |
   
Pour plus d’informations, [voir Get-CsWindowsService.](/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)
  
## <a name="view-details-about-a-service"></a>Afficher les détails d’un service
<a name="view_details"> </a>

Vous pouvez utiliser Skype Entreprise Server panneau de commande pour afficher des détails sur chaque service en cours d’exécution sur un ordinateur spécifique de votre topologie. Vous pouvez consulter le statut de chaque service, ainsi que des données détaillées relatives aux bases de données associées, aux ports et aux services dépendants.
  
### <a name="to-view-details-for-a-service"></a>Pour afficher les détails d’un service

1. À partir d’un compte d’utilisateur affecté à l’un des rôles d’administration prédéfin Skype Entreprise Server, connectez-vous à n’importe quel ordinateur de votre déploiement interne. Pour plus d’informations sur les rôles d’administration prédéfin Skype Entreprise Server, voir **Planning for Role-Based Access Control**.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.
4. Dans la page **Statut**, triez la liste ou effectuez-y une recherche, puis cliquez sur l’ordinateur à afficher.
5. Cliquez sur **Propriétés**.
6. Dans la fenêtre **Détail de l’ordinateur**, triez la liste des services, si besoin est, puis cliquez sur le service à consulter.
7. Effectuez les opérations suivantes, le cas échéant :
   - Pour afficher le dernier statut du service concerné, cliquez sur **Obtenir le statut du service**.
   - Pour afficher les détails du service en question, cliquez sur **Propriétés**, puis sur **Fermer**.
   - Pour obtenir une liste de tous les ordinateurs de votre topologie, cliquez sur **Fermer**.
    
## <a name="start-or-stop-skype-for-business-server-services"></a>Démarrer ou arrêter Skype Entreprise Server services
<a name="StartStop"> </a>

Vous pouvez utiliser Skype Entreprise Server panneau de Skype Entreprise Server pour démarrer ou arrêter tous les services Skype Entreprise Server en cours d’exécution sur un ordinateur spécifique ou pour démarrer ou arrêter un service spécifique.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>Pour démarrer ou arrêter tous les services Skype Entreprise sur un ordinateur

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server. Vous pouvez déterminer si le rôle RBAC CsServerAdministrator ou CsAdministrator vous a été affecté en exécutant une commande semblable à la suivante :
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.
4. Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute les services que vous souhaitez démarrer ou arrêter, ou triez cette liste, puis cliquez sur cet ordinateur.
5. Cliquez sur **Action**.
6. Cliquez sur **Démarrer tous les services** ou **Arrêter tous les services**.
    
### <a name="to-start-or-stop-a-specific-service"></a>Pour démarrer ou arrêter un service spécifique

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.
4. Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter, ou triez cette liste, puis cliquez sur cet ordinateur.
5. Cliquez sur **Propriétés**.
6. Triez la liste de services, si nécessaire et cliquez sur le service que vous souhaitez démarrer ou arrêter.
7. Cliquez sur **Action**.
8. Cliquez sur **Démarrer le service** ou **Arrêter le service**.
9. Cliquez sur **Fermer**.
    
## <a name="prevent-sessions-for-services"></a>Empêcher l’exécution de sessions de services
<a name="prevent_session"> </a>

Vous pouvez utiliser le Panneau de Skype Entreprise Server pour empêcher l’exécution de nouvelles sessions pour tous les services Skype Entreprise Server sur un ordinateur spécifique ou pour empêcher de nouvelles sessions pour un service Skype Entreprise Server spécifique.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>Pour empêcher de nouvelles sessions pour tous les services Skype Entreprise sur un ordinateur

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.
4. Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute les services pour lesquels vous souhaitez empêcher toute nouvelle session, puis cliquez sur cet ordinateur.
5. Cliquez sur **Action**.
6. Cliquez sur **Empêcher de nouvelles sessions pour tous les services**.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>Pour empêcher l’exécution de nouvelles sessions d’un service spécifique

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.
4. Dans la page **État**, recherchez dans la liste l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter, ou triez cette liste, puis cliquez sur cet ordinateur. 
5. Cliquez sur **Propriétés**.
6. Triez la liste de services, si nécessaire, et cliquez sur le service pour lequel vous souhaitez empêcher toute nouvelle session.
7. Cliquez sur **Action**.
8. Cliquez sur **Empêcher de nouvelles sessions pour le service**.
9. Cliquez sur **Fermer**.
