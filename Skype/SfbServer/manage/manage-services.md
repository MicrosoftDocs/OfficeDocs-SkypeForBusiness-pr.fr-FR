---
title: Gérer les services de Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: Cet article explique comment gérer les services qui s’exécutent dans un Skype pour la topologie du serveur d’entreprise.
ms.openlocfilehash: d2068f5b485e4beb76016c9cad4388f157fdae97
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898296"
---
# <a name="manage-services-for-skype-for-business-server"></a>Gérer les services de Skype pour Business Server

Cet article explique comment gérer les services qui s’exécutent dans un Skype pour la topologie du serveur d’entreprise.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Afficher la liste des ordinateurs qui exécutent Skype pour Business Server
<a name="view_list"> </a>

Vous pouvez utiliser Skype pour Business Server Control Panel pour afficher une liste de tous les ordinateurs qui exécutent Skype pour Business Server dans votre topologie et voir le statut de service de chacun d’eux. Vous pouvez trier la liste par ordinateur, pool ou site. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>Pour afficher la liste des ordinateurs qui exécutent Skype pour Business Server

1. À partir d’un compte d’utilisateur qui est affecté à un des rôles d’administration prédéfinis Skype pour Business Server, ouvrez une session n’importe quel ordinateur dans votre déploiement interne. Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Skype pour Business Server, voir **Planning for Role-Based Access Control**.   
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.   
3. Dans la barre de navigation de gauche, cliquez sur **topologie** , puis cliquez sur **état**.   
4. Dans la page **d’état** , effectuez l’une des opérations suivantes selon vos besoins :
   - Triez la liste en cliquant sur **l’ordinateur**, un **Pool**ou un en-tête de colonne de **Site** , puis cliquez sur la flèche vers le haut ou la flèche vers le bas. 
   - Cliquez sur **Actualiser** pour afficher la liste la plus récente.  
   - Recherche d’un ordinateur spécifique en tapant le nom d’ordinateur dans le champ de recherche.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>Afficher l’état des services exécutés sur un Skype pour Business server
<a name="view-status"> </a>

Vous pouvez utiliser Skype pour Business Server Control Panel pour afficher tous les services qui sont exécutent sur un ordinateur donné de votre Skype pour la topologie du serveur d’entreprise et voir le statut de chaque service.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>Pour afficher l’état des services s’exécutant sur un ordinateur

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
3. Dans la barre de navigation de gauche, cliquez sur **la topologie**. 
4. Dans la page **statut** , triez ou recherchez dans la liste, selon les besoins, pour rechercher l’ordinateur que qui vous intéresse, puis cliquez sur le nom de l’ordinateur.
5. Effectuez l’une des opérations suivantes :
   - Pour afficher le dernier statut des services qui s’exécutent sur l’ordinateur, cliquez sur **obtenir l’état du service**.
   - Pour afficher la liste des services spécifiques en cours d’exécution sur l’ordinateur et le statut de chaque service, cliquez sur **Propriétés**, puis cliquez sur **Fermer** pour revenir à la liste.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Affichage de l’état du service avec les applets de commande Windows Powershell

Vous pouvez également afficher l’état de service à l’aide de Windows PowerShell et l’applet de commande **Get-CsWindowsService** . Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server.
  
### <a name="to-view-service-status"></a>Pour afficher l’état du service

Pour afficher l’état du service sur un ordinateur, tapez une commande semblable à ce qui suit dans le Skype pour Business Server Management Shell et appuyez sur ENTRÉE :
  
```
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Cette commande renvoie le type d’informations suivant :
  
|**RoleName**|**État**|
|:-----|:-----|
|{W3SVC}  <br/> |En cours d’exécution  <br/> |
|{CentralManagement}  <br/> | En cours d’exécution <br/> |
|Et {ClsAgent}  <br/> |En cours d’exécution  <br/> |
|{Serveur d’inscriptions, UserServer, EdgeServer}  <br/> |En cours d’exécution  <br/> |
|{ApplicationServer}  <br/> |En cours d’exécution  <br/> |
|{ConferencingServer}  <br/> |En cours d’exécution  <br/> |
|{MediationServer}  <br/> |En cours d’exécution  <br/> |
   
Pour plus d’informations, voir [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).
  
## <a name="view-details-about-a-service"></a>Afficher les détails d’un service
<a name="view_details"> </a>

Vous pouvez utiliser Skype pour Business Server Control Panel pour afficher plus d’informations sur chaque service qui s’exécute sur un ordinateur spécifique dans votre topologie. Vous pouvez afficher l’état de chaque service et les détails tels que les bases de données associées, les ports et les services dépendants.
  
### <a name="to-view-details-for-a-service"></a>Pour afficher les détails d’un service

1. À partir d’un compte d’utilisateur qui est affecté à un des rôles d’administration prédéfinis Skype pour Business Server, ouvrez une session n’importe quel ordinateur dans votre déploiement interne. Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Skype pour Business Server, voir **Planning for Role-Based Access Control**.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
3. Dans la barre de navigation de gauche, cliquez sur **topologie** , puis cliquez sur **état**.
4. Dans la page **statut** , triez ou effectuer une recherche dans la liste, puis cliquez sur l’ordinateur que vous souhaitez afficher.
5. Cliquez sur **Propriétés**.
6. Dans la fenêtre **Détail de l’ordinateur** , triez la liste des services, si nécessaire, cliquez sur le service que vous souhaitez afficher.
7. Effectuez l’une des opérations suivantes selon vos besoins :
   - Pour afficher le dernier statut du service concerné, cliquez sur **obtenir l’état du service**.
   - Pour afficher les détails de ce service spécifique, cliquez sur **Propriétés** , puis cliquez sur **Fermer**.
   - Pour revenir à la liste de tous les ordinateurs de votre topologie, cliquez sur **Fermer**.
    
## <a name="start-or-stop-skype-for-business-server-services"></a>Démarrer ou arrêter Skype pour les services Business Server
<a name="StartStop"> </a>

Vous pouvez utiliser Skype pour Business Server Control Panel pour démarrer ou arrêter tous les Skype pour les services Business Server s’exécutant sur un ordinateur spécifique ou pour démarrer ou arrêter un service spécifique.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>Pour démarrer ou arrêter tous les Skype pour les services sur un ordinateur

1. À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server . Vous pouvez déterminer si vous avez reçu le CsServerAdministrator ou le rôle CsAdministrator RBAC en exécutant une commande semblable à ce qui suit :
    
   ```
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
3. Dans la barre de navigation de gauche, cliquez sur **topologie** , puis cliquez sur **état**.
4. Sur la page **d’état** , de tri ou de recherche par le biais de la liste pour trouver l’ordinateur qui exécute les services que vous souhaitez démarrer ou arrêter, puis cliquez dessus.
5. Cliquez sur **Action**.
6. Cliquez sur **Démarrer tous les services** ou **Arrêter tous les services**.
    
### <a name="to-start-or-stop-a-specific-service"></a>Pour démarrer ou arrêter un service spécifique

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
3. Dans la barre de navigation de gauche, cliquez sur **topologie** , puis cliquez sur **état**.
4. Sur la page **d’état** , de tri ou de recherche par le biais de la liste selon vos besoins pour rechercher l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter, puis cliquez dessus.
5. Cliquez sur **Propriétés**.
6. Triez la liste des services, si nécessaire, cliquez sur le service que vous souhaitez démarrer ou arrêter.
7. Cliquez sur **Action**.
8. Cliquez sur **Démarrer le service** ou **Arrêter le service**.
9. Cliquez sur **Fermer**.
    
## <a name="prevent-sessions-for-services"></a>Empêcher l’exécution de sessions de services
<a name="prevent_session"> </a>

Vous pouvez utiliser Skype pour Business Server Control Panel pour empêcher de nouvelles sessions pour tous les Skype pour les services Business Server s’exécutant sur un ordinateur spécifique ou de nouvelles sessions pour un Skype spécifique pour le service Business Server.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>Pour empêcher les nouvelles sessions pour tous les Skype pour les services sur un ordinateur

1. À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
3. Dans la barre de navigation de gauche, cliquez sur **topologie** , puis cliquez sur **état**.
4. Sur la page **état** du tri ou recherche par le biais de la liste en tant que nécessaire pour trouver l’ordinateur qui exécute les services pour laquelle vous souhaitez empêcher de nouvelles sessions, puis cliquez dessus.
5. Cliquez sur **Action**.
6. Cliquez sur **empêcher de nouvelles sessions pour tous les services**.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>Pour empêcher les nouvelles sessions pour un service spécifique

1. À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
3. Dans la barre de navigation de gauche, cliquez sur **topologie** , puis cliquez sur **état**.
4. Sur la page **d’état** , de tri ou de recherche par le biais de la liste selon vos besoins pour rechercher l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter, puis cliquez dessus. 
5. Cliquez sur **Propriétés**.
6. Triez la liste des services, si nécessaire, cliquez sur le service pour lequel vous voulez empêcher de nouvelles sessions.
7. Cliquez sur **Action**.
8. Cliquez sur **empêcher de nouvelles sessions de service**.
9. Cliquez sur **Fermer**.
    

