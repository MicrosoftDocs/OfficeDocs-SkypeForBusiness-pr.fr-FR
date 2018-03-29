---
title: Gérer les services de Skype pour Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: Cet article décrit comment gérer les services s’exécutant dans un Skype pour la topologie de Business Server 2015.
ms.openlocfilehash: f8406d473b1d2ae644ac56d071313d2b488169fa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-services-for-skype-for-business-server-2015"></a>Gérer les services de Skype pour Business Server 2015

Cet article décrit comment gérer les services s’exécutant dans un Skype pour la topologie de Business Server 2015.
  
## <a name="view-a-list-of-computers-running-skype-for-business-server-2015"></a>Afficher la liste des ordinateurs exécutant Skype pour Business Server 2015
<a name="view_list"> </a>

Vous pouvez utiliser Skype pour le panneau de configuration de Business Server pour afficher une liste de tous les ordinateurs qui exécutent le Skype pour 2015 de serveur d’entreprise dans votre topologie et voir l’état de service de chaque. Vous pouvez trier la liste par ordinateur, de pool ou de site. 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>Pour afficher une liste d’ordinateurs exécutant Skype pour Business Server

1. À partir d’un compte d’utilisateur qui est affecté à un des rôles d’administration prédéfinis pour Skype pour Business Server 2015, vous connecter à n’importe quel ordinateur dans votre déploiement interne. Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Skype pour Business Server 2015, consultez **planification de contrôle d’accès basée sur les rôles**.   
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.   
3. Dans la barre de navigation de gauche, cliquez sur **la topologie** et puis cliquez sur **état**.   
4. Sur la page **état** , effectuez l’une des suivantes si nécessaire :
   - Trier la liste en cliquant sur **l’ordinateur**, un **Pool**ou un en-tête de colonne de **Site** , puis cliquez sur la flèche haut ou la flèche vers le bas. 
   - Cliquez sur **Actualiser** pour afficher la liste la plus récente.  
   - Recherche d’un ordinateur spécifique en tapant le nom de l’ordinateur dans le champ de recherche.
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-2015-server"></a>Afficher l’état des services exécutés sur un Skype pour serveur d’entreprise 2015
<a name="view-status"> </a>

Vous pouvez utiliser Skype pour le panneau de configuration de Business Server permet d’afficher tous les services qui sont exécutent sur un ordinateur spécifique dans votre Skype pour la topologie du serveur de l’entreprise et de consulter l’état de chaque service.
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>Pour afficher l’état des services exécutés sur un ordinateur

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
3. Dans la barre de navigation de gauche, cliquez sur **la topologie**. 
4. Sur la page **état** , trier et recherche dans la liste, si nécessaire, pour trouver l’ordinateur qui que vous intéresse, puis cliquez sur le nom de l’ordinateur.
5. Effectuez l’une des opérations suivantes :
   - Pour afficher le dernier état de services en cours d’exécution sur l’ordinateur, cliquez sur **obtenir l’état du service**.
   - Pour afficher une liste de services spécifiques en cours d’exécution sur l’ordinateur et l’état de chaque service, cliquez sur **Propriétés**, puis cliquez sur **Fermer** pour revenir à la liste.
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>Affichage de l’état de service avec les applets de commande Windows Powershell

Vous pouvez également afficher le statut du service à l’aide de Windows PowerShell et l’applet de commande **Get-CsWindowsService** . Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server.
  
### <a name="to-view-service-status"></a>Pour afficher l’état du service

Pour afficher l’état du service sur un ordinateur, tapez une commande semblable à la suivante dans le Skype pour Business Server Management Shell et appuyez sur ENTRÉE :
  
```
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Cette commande renvoie le type d’informations suivant :
  
|**RoleName**|**État**|
|:-----|:-----|
|{W3SVC}  <br/> |En cours d’exécution  <br/> |
|{CentralManagement}  <br/> | En cours d’exécution <br/> |
|{ClsAgent}  <br/> |En cours d’exécution  <br/> |
|{Greffier, UserServer, EdgeServer}  <br/> |En cours d’exécution  <br/> |
|{ApplicationServer}  <br/> |En cours d’exécution  <br/> |
|{ConferencingServer}  <br/> |En cours d’exécution  <br/> |
|{MediationServer}  <br/> |En cours d’exécution  <br/> |
   
Pour plus d’informations, consultez [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).
  
## <a name="view-details-about-a-service"></a>Afficher des détails sur un service
<a name="view_details"> </a>

Vous pouvez utiliser Skype pour le panneau de configuration de Business Server pour afficher les détails de chaque service qui s’exécute sur un ordinateur spécifique dans votre topologie. Vous pouvez afficher l’état de chaque service et les détails tels que les bases de données associées, les ports et les services qui en dépendent.
  
### <a name="to-view-details-for-a-service"></a>Pour afficher les détails d’un service

1. À partir d’un compte d’utilisateur qui est affecté à un des rôles d’administration prédéfinis pour Skype pour Business Server 2015, vous connecter à n’importe quel ordinateur dans votre déploiement interne. Pour plus d’informations sur les rôles d’administration prédéfinis disponibles dans Skype pour Business Server 2015, consultez **planification de contrôle d’accès basée sur les rôles**.
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
3. Dans la barre de navigation de gauche, cliquez sur **la topologie** et puis cliquez sur **état**.
4. Dans la page **état** , trier et effectuer une recherche dans la liste puis cliquez sur l’ordinateur que vous souhaitez afficher.
5. Cliquez sur **Propriétés**.
6. Dans la fenêtre **Ordinateur afficher les détails** , trier la liste des services, si nécessaire, puis cliquez sur le service que vous souhaitez afficher.
7. Effectuez l’une des opérations suivantes selon vos besoins :
   - Pour afficher le dernier état de ce service spécifique, cliquez sur **obtenir l’état du service**.
   - Pour afficher les détails de ce service spécifique, cliquez sur **Propriétés** , puis sur **Fermer**.
   - Pour revenir à la liste de tous les ordinateurs dans votre topologie, cliquez sur **Fermer**.
    
## <a name="start-or-stop-skype-for-business-server-2015-services"></a>Démarrer ou arrêter Skype pour les services d’entreprise serveur 2015
<a name="StartStop"> </a>

Vous pouvez utiliser Skype pour le panneau de configuration de Business Server pour démarrer ou arrêter tous le Skype pour services 2015 de serveur d’entreprise s’exécutant sur un ordinateur spécifique, ou pour démarrer ou arrêter un service spécifique.
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>Pour démarrer ou arrêter tous les Skype pour les services sur un ordinateur

1. À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou dispose de droits d’utilisateur équivalent), ou le rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur sur le réseau dans lequel vous avez déployé Skype pour Business Server 2015. Vous pouvez déterminer si vous avez reçu le CsServerAdministrator ou le rôle CsAdministrator RBAC en exécutant une commande semblable à la suivante :
    
  ```
  Get-CsAdminRoleAssignment -Identity "kenmyer"

  ```

2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
3. Dans la barre de navigation de gauche, cliquez sur **la topologie** et puis cliquez sur **état**.
4. Sur la page **d’état** , de tri ou de recherche dans la liste pour trouver l’ordinateur qui exécute les services que vous souhaitez démarrer ou arrêter et cliquez dessus.
5. Cliquez sur **Action**.
6. Cliquez sur **Démarrer tous les services** ou les **Arrêter tous les services**.
    
### <a name="to-start-or-stop-a-specific-service"></a>Pour démarrer ou arrêter un service spécifique

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
3. Dans la barre de navigation de gauche, cliquez sur **la topologie** et puis cliquez sur **état**.
4. Sur la page **d’état** , de tri ou de recherche dans la liste pour trouver l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter et cliquez dessus.
5. Cliquez sur **Propriétés**.
6. Trier la liste des services, si nécessaire, puis cliquez sur le service que vous souhaitez démarrer ou arrêter.
7. Cliquez sur **Action**.
8. Cliquez sur **Démarrer le service** ou **Arrêter le service**.
9. Cliquez sur **Fermer**.
    
## <a name="prevent-sessions-for-services"></a>Empêcher les sessions pour les services
<a name="prevent_session"> </a>

Vous pouvez utiliser Skype pour le panneau de configuration de Business Server afin d’éviter de nouvelles sessions pour tous le Skype pour services 2015 de serveur d’entreprise s’exécutant sur un ordinateur spécifique ou pour éviter de nouvelles sessions pour un Skype spécifique pour le service de Business Server 2015.
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>Pour empêcher les nouvelles sessions pour tous les Skype pour les services sur un ordinateur

1. À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou dispose de droits d’utilisateur équivalent), ou le rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur sur le réseau dans lequel vous avez déployé Skype pour Business Server 2015.
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
3. Dans la barre de navigation de gauche, cliquez sur **la topologie** et puis cliquez sur **état**.
4. Sur la page **état du** tri ou recherche dans la liste en tant que nécessaire pour trouver l’ordinateur qui exécute les services pour lesquels vous souhaitez empêcher de nouvelles sessions, puis cliquez dessus.
5. Cliquez sur **Action**.
6. Cliquez sur **empêcher les nouvelles sessions de tous les services**.
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>Pour empêcher les nouvelles sessions pour un service spécifique

1. À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou dispose de droits d’utilisateur équivalent), ou le rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur sur le réseau dans lequel vous avez déployé Skype pour Business Server 2015.
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
3. Dans la barre de navigation de gauche, cliquez sur **la topologie** et puis cliquez sur **état**.
4. Sur la page **d’état** , de tri ou de recherche dans la liste pour trouver l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter et cliquez dessus. 
5. Cliquez sur **Propriétés**.
6. Trier la liste des services, si nécessaire, puis cliquez sur le service pour lequel vous souhaitez empêcher de nouvelles sessions.
7. Cliquez sur **Action**.
8. Cliquez sur **empêcher les nouvelles sessions de service**.
9. Cliquez sur **Fermer**.
    

