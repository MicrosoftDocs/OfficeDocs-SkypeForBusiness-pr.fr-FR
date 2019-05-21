---
title: Gestion des services pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: Cet article explique comment gérer les services exécutés dans une topologie Skype entreprise Server.
ms.openlocfilehash: 9d1a79226422da57eee36e27590769f76b89b560
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279619"
---
# <a name="manage-services-for-skype-for-business-server"></a>Gestion des services pour Skype entreprise Server

Cet article explique comment gérer les services exécutés dans une topologie Skype entreprise Server.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Affichage de la liste des ordinateurs exécutant Skype entreprise Server
<a name="view_list"> </a>

Le panneau de configuration Skype entreprise Server vous permet d’afficher la liste de tous les ordinateurs qui exécutent Skype entreprise Server dans votre topologie et de consulter l’état des services. Vous pouvez trier la liste sur un ordinateur, un pool ou un site. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>Pour afficher une liste d’ordinateurs exécutant Skype entreprise Server

1. À partir d’un compte d’utilisateur affecté à un des rôles d’administration prédéfinis pour Skype entreprise Server, connectez-vous à n’importe quel ordinateur dans votre déploiement interne. Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Skype entreprise Server, voir **planification du contrôle d’accès basé sur un rôle**.   
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.   
3. Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur Status ( **statut**).   
4. Dans la page **État** , effectuez l’une des opérations suivantes si nécessaire:
   - Triez la liste en cliquant sur l’en-tête de la colonne **ordinateur**, **pool**ou **site** , puis en cliquant sur la flèche vers le haut ou la flèche vers le bas. 
   - Cliquez **** sur Actualiser pour afficher la liste la plus à jour.  
   - Recherchez un ordinateur en particulier en tapant le nom de l’ordinateur dans le champ de recherche.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>Affichage de l’état des services en cours d’exécution sur un serveur Skype entreprise
<a name="view-status"> </a>

Le panneau de configuration Skype entreprise Server vous permet d’afficher tous les services en cours d’exécution sur un ordinateur spécifique dans votre topologie Skype entreprise Server et de consulter l’état de chaque service.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>Pour afficher l’état des services en cours d’exécution sur un ordinateur

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
3. Dans la barre de navigation de gauche, cliquez sur **Topology**. 
4. Dans la page **État** , triez ou effectuez une recherche dans la liste, si nécessaire, pour trouver l’ordinateur qui vous intéresse, puis cliquez sur le nom de l’ordinateur.
5. Effectuez l’une des opérations suivantes :
   - Pour afficher le dernier état des services en cours d’exécution sur l’ordinateur, cliquez sur **obtenir l’état du service**.
   - Pour afficher une liste de services spécifiques en cours d’exécution sur l’ordinateur et l’état de chaque service, cliquez sur **Propriétés**, puis sur **Fermer** pour revenir à la liste.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Affichage de l’état du service à l’aide des cmdlets Windows PowerShell

Vous pouvez également afficher l’état du service à l’aide de Windows PowerShell et de l’applet **de connexion Get-CsWindowsService** . Vous pouvez exécuter cette applet de commande dans Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [«démarrage rapide: gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype entreprise Server.
  
### <a name="to-view-service-status"></a>Pour afficher l’état du service

Pour afficher l’état du service sur un ordinateur, tapez une commande similaire à celle qui suit dans Skype entreprise Server Management Shell, puis appuyez sur entrée:
  
```
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Cette commande renvoie le type d’informations suivant :
  
|**RoleName**|**État**|
|:-----|:-----|
|W3SVC  <br/> |Ordinateur  <br/> |
|{CentralManagement}  <br/> | Ordinateur <br/> |
|{ClsAgent}  <br/> |Ordinateur  <br/> |
|{Registrar, UserServer, EdgeServer}  <br/> |Ordinateur  <br/> |
|{ApplicationServer}  <br/> |Ordinateur  <br/> |
|{ConferencingServer}  <br/> |Ordinateur  <br/> |
|{MediationServer}  <br/> |Ordinateur  <br/> |
   
Pour plus d’informations, consultez la rubrique [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).
  
## <a name="view-details-about-a-service"></a>Afficher les détails d’un service
<a name="view_details"> </a>

Le panneau de configuration Skype entreprise Server vous permet d’afficher des détails sur les services en cours d’exécution sur un ordinateur spécifique de votre topologie. Vous pouvez afficher l’état de chaque service et des détails, tels que les bases de données, ports et services dépendants associés.
  
### <a name="to-view-details-for-a-service"></a>Pour afficher les détails d’un service

1. À partir d’un compte d’utilisateur affecté à un des rôles d’administration prédéfinis pour Skype entreprise Server, connectez-vous à n’importe quel ordinateur dans votre déploiement interne. Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Skype entreprise Server, voir **planification du contrôle d’accès basé sur un rôle**.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
3. Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur Status ( **statut**).
4. Dans la page **État** , triez ou effectuez une recherche dans la liste, puis cliquez sur l’ordinateur que vous voulez afficher.
5. Cliquez sur **Propriétés**.
6. Dans la fenêtre **afficher les détails** de l’ordinateur, triez la liste des services, le cas échéant, puis cliquez sur le service que vous souhaitez afficher.
7. Effectuez l’une des opérations suivantes selon vos besoins:
   - Pour afficher le dernier état de ce service, cliquez sur **obtenir l’état du service**.
   - Pour afficher les détails de ce service, cliquez sur **Propriétés** , puis sur **Fermer**.
   - Pour revenir à la liste de tous les ordinateurs de votre topologie, cliquez sur **Fermer**.
    
## <a name="start-or-stop-skype-for-business-server-services"></a>Démarrer ou arrêter des services Skype entreprise Server
<a name="StartStop"> </a>

Vous pouvez utiliser le panneau de configuration Skype entreprise Server pour démarrer ou arrêter l’exécution de tous les services Skype entreprise Server sur un ordinateur spécifique ou pour démarrer ou arrêter un service spécifique.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>Pour démarrer ou arrêter tous les services Skype entreprise sur un ordinateur

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. . Vous pouvez déterminer si vous avez reçu le rôle CsServerAdministrator ou CsAdministrator RBAC en exécutant une commande semblable à ce qui suit:
    
   ```
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
3. Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur Status ( **statut**).
4. Dans la page **État** , triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant les services que vous voulez démarrer ou arrêter, puis cliquez dessus.
5. Cliquez sur **action**.
6. Cliquez sur **Démarrer tout le service** ou **arrêter tous les services**.
    
### <a name="to-start-or-stop-a-specific-service"></a>Pour démarrer ou arrêter un service spécifique

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
3. Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur Status ( **statut**).
4. Dans la page **État** , triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant le service que vous voulez démarrer ou arrêter, puis cliquez dessus.
5. Cliquez sur **Propriétés**.
6. Triez la liste des services, si nécessaire, puis cliquez sur le service que vous voulez démarrer ou arrêter.
7. Cliquez sur **action**.
8. Cliquez sur **Démarrer le service** ou arrêter le **service**.
9. Cliquez sur **Fermer**.
    
## <a name="prevent-sessions-for-services"></a>Empêcher l’exécution de sessions de services
<a name="prevent_session"> </a>

Le panneau de configuration Skype entreprise Server vous permet d’éviter de nouvelles sessions pour tous les services Skype entreprise Server en cours d’exécution sur un ordinateur spécifique ou d’empêcher de nouvelles sessions pour un service Skype entreprise Server spécifique.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>Pour éviter de nouvelles sessions pour tous les services Skype entreprise sur un ordinateur

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
3. Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur Status ( **statut**).
4. Dans la page **État** , triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant les services pour lesquels vous voulez éviter de nouvelles sessions, puis cliquez dessus.
5. Cliquez sur **action**.
6. Cliquez sur **empêcher de nouvelles sessions pour tous les services**.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>Pour empêcher de nouvelles sessions pour un service spécifique

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
3. Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur Status ( **statut**).
4. Dans la page **État** , triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant le service que vous voulez démarrer ou arrêter, puis cliquez dessus. 
5. Cliquez sur **Propriétés**.
6. Triez la liste des services, si nécessaire, puis cliquez sur le service pour lequel vous souhaitez éviter de nouvelles sessions.
7. Cliquez sur **action**.
8. Cliquez sur **empêcher de nouvelles sessions pour le service**.
9. Cliquez sur **Fermer**.
    

