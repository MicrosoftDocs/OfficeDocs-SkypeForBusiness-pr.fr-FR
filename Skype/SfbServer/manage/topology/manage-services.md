---
title: Gestion des services dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Apprenez à afficher l’état du service, à démarrer et arrêter des services, et à empêcher les sessions pour les services.
ms.openlocfilehash: c3c0ad3a61543caf7866582413a67968c4c1c2d6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275149"
---
# <a name="manage-services-in-skype-for-business-server"></a>Gestion des services dans Skype entreprise Server

Le panneau de configuration Skype entreprise Server vous permet d’afficher la liste de tous les ordinateurs qui exécutent Skype entreprise Server dans votre topologie, de consulter l’état des services, de démarrer ou d’arrêter des services et d’empêcher les sessions pour les services.

- [Affichage de la liste des ordinateurs exécutant Skype entreprise Server](#view-a-list-of-computers-running-skype-for-business-server)
- [Affichage de l’état des services en cours d’exécution sur un ordinateur dans Skype entreprise](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Démarrer ou arrêter des services Skype entreprise](#start-or-stop-skype-for-business-services)
- [Empêcher l’exécution de sessions de services](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Affichage de la liste des ordinateurs exécutant Skype entreprise Server

Le panneau de configuration Skype entreprise Server vous permet d’afficher la liste de tous les ordinateurs qui exécutent Skype entreprise dans votre topologie et de consulter l’état des services. Vous pouvez trier la liste sur un ordinateur, un pool ou un site. 

1. À partir d’un compte d’utilisateur affecté à un des rôles d’administration prédéfinis pour Skype entreprise Server, connectez-vous à n’importe quel ordinateur dans votre déploiement interne. Pour plus d’informations, reportez-vous à la rubrique [contrôle d’accès basé sur les rôles (RBAC) pour Skype entreprise Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Skype entreprise Server, voir [installer et ouvrir les outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**. 
4. Dans la page État, effectuez l’une des opérations suivantes selon vos besoins:
    - Triez la liste en cliquant sur l’en-tête de la colonne **ordinateur**, **pool**ou **site** , puis en cliquant sur la flèche vers le haut ou la flèche vers le bas.
    - Cliquez **** sur Actualiser pour afficher la liste la plus à jour.
    - Recherchez un ordinateur en particulier en tapant le nom de l’ordinateur dans le champ de recherche.
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Affichage de l’état des services en cours d’exécution sur un ordinateur dans Skype entreprise

Servez-vous du panneau de configuration Skype entreprise Server pour afficher tous les services en cours d’exécution sur un ordinateur spécifique dans votre topologie Skype entreprise Server et afficher l’état de chaque service.

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Skype entreprise Server, voir [installer et ouvrir les outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Dans la barre de navigation de gauche, cliquez sur **Topology**.
4. Dans la page État, triez ou effectuez une recherche dans la liste, si nécessaire, pour trouver l’ordinateur qui vous intéresse, puis cliquez sur le nom de l’ordinateur.
5. Effectuez l’une des opérations suivantes:
    - Pour afficher le dernier état des services en cours d’exécution sur l’ordinateur, cliquez sur **obtenir l’état du service**.
    - Pour afficher une liste de services spécifiques en cours d’exécution sur l’ordinateur et l’état de chaque service, cliquez sur **Propriétés**, puis sur **Fermer** pour revenir à la liste.

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Affichage de l’état du service à l’aide des cmdlets Windows PowerShell

Vous pouvez également afficher l’état du service à l’aide de Windows PowerShell et de l’applet de connexion Get-CsWindowsService. Vous pouvez exécuter cette applet de commande dans Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations, reportez-vous à la rubrique [Skype entreprise Server Management Shell](../management-shell.md).

**Pour afficher l’état du service**

Pour afficher l’état du service sur un ordinateur, tapez une commande similaire à celle qui suit dans Skype entreprise Server Management Shell, puis appuyez sur entrée:

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

Cette commande renvoie le type d’informations suivant :

```
RoleName                                  Status
--------                                  ------
{W3SVC}                                   Running
{CentralManagement}                       Running
{ClsAgent}                                Running
{Registrar, UserServer, EdgeServer}       Running
{ApplicationServer}                       Running
{ConferencingServer}                      Running
{MediationServer}                         Running
```

Pour plus d’informations, consultez la rubrique [Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService).

## <a name="start-or-stop-skype-for-business-services"></a>Démarrer ou arrêter des services Skype entreprise

Servez-vous du panneau de configuration Skype entreprise Server pour démarrer ou arrêter l’exécution de tous les services Skype entreprise Server sur un ordinateur spécifique ou pour démarrer ou arrêter un service spécifique.

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>Démarrer ou arrêter tous les services Skype entreprise Server sur un ordinateur

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. . Vous pouvez déterminer si vous avez reçu le rôle CsServerAdministrator ou CsAdministrator RBAC en exécutant une commande semblable à ce qui suit:

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Skype entreprise Server, voir [installer et ouvrir les outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**. 
4. Dans la page État, triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant les services que vous voulez démarrer ou arrêter, puis cliquez dessus.
5. Cliquez sur **action**.
6. Cliquez sur **Démarrer tout le service** ou **arrêter tous les services**.

### <a name="start-or-stop-a-specific-service"></a>Démarrer ou arrêter un service spécifique

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Skype entreprise Server, voir [installer et ouvrir les outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**. 
4. Dans la page État, triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant le service que vous voulez démarrer ou arrêter, puis cliquez dessus.
5. Cliquez sur **Propriétés**.
6. Triez la liste des services, si nécessaire, puis cliquez sur le service que vous voulez démarrer ou arrêter.
7. Cliquez sur **action**.
8. Cliquez sur **Démarrer le service** ou arrêter le **service**.
9. Cliquez sur **Fermer**.


## <a name="prevent-sessions-for-services"></a>Empêcher l’exécution de sessions de services

Le panneau de configuration Skype pour les entreprises vous permet d’éviter de nouvelles sessions pour tous les services Skype entreprise Server en cours d’exécution sur un ordinateur spécifique ou d’empêcher de nouvelles sessions pour un service spécifique.

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>Empêcher de nouvelles sessions pour tous les services Skype entreprise Server sur un ordinateur

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Skype entreprise Server, voir [installer et ouvrir les outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Dans la barre de navigation de gauche, cliquez sur **Topology** , puis sur Status ( **statut**).
4. Dans la page État, triez ou effectuez une recherche dans la liste selon vos besoins pour trouver l’ordinateur exécutant les services pour lesquels vous voulez éviter de nouvelles sessions, puis cliquez dessus.
5. Cliquez sur **action**.
6. Cliquez sur **empêcher de nouvelles sessions pour tous les services**.

### <a name="prevent-new-sessions-for-a-specific-service"></a>Empêcher de nouvelles sessions pour un service spécifique

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Skype entreprise Server, voir [installer et ouvrir les outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**. 
4. Cliquez sur **Propriétés**.
5. Triez la liste des services, si nécessaire, puis cliquez sur le service pour lequel vous souhaitez éviter de nouvelles sessions.
6. Cliquez sur **action**.
7. Cliquez sur **empêcher de nouvelles sessions pour le service**.
8. Cliquez sur **Fermer**.
