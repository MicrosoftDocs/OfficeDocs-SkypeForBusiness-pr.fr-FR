---
title: Gérer les services dans Skype Entreprise Server
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
description: Découvrez comment afficher l’état du service, démarrer et arrêter des services et empêcher les sessions pour les services.
ms.openlocfilehash: cc5218f5347eb2124f42b8881bce730c74889bda
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864731"
---
# <a name="manage-services-in-skype-for-business-server"></a>Gérer les services dans Skype Entreprise Server

Vous pouvez utiliser le Panneau de Skype Entreprise Server pour afficher la liste de tous les ordinateurs exécutant des Skype Entreprise Server dans votre topologie, afficher l’état des services, démarrer ou arrêter des services et empêcher les sessions pour les services.

- [Afficher la liste des ordinateurs exécutant Skype Entreprise Server](#view-a-list-of-computers-running-skype-for-business-server)
- [Afficher l’état des services en cours d’exécution sur un ordinateur Skype Entreprise](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Démarrer ou arrêter Skype Entreprise services](#start-or-stop-skype-for-business-services)
- [Empêcher l’exécution de sessions de services](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Afficher la liste des ordinateurs exécutant Skype Entreprise Server

Utilisez le Panneau de Skype Entreprise Server pour afficher la liste de tous les ordinateurs qui exécutent Skype Entreprise dans votre topologie et voir l’état du service de chacun d’eux. Vous pouvez trier la liste par ordinateur, pool ou site. 

1. À partir d’un compte d’utilisateur affecté à l’un des rôles d’administration prédéfin Skype Entreprise Server, connectez-vous à n’importe quel ordinateur de votre déploiement interne. Pour plus d’informations, voir contrôle d’accès basé sur un rôle [(RBAC) pour Skype Entreprise Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Panneau de Skype Entreprise Server, voir Installer et ouvrir les [outils d’administration.](../../management-tools/install-and-open-administrative-tools.md)
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.
4. Dans la page État, faites l’une des choses suivantes selon les besoins :
    - Triez la liste en cliquant sur le titre de colonne **Ordinateur**, **Pool** ou **Site**, puis en cliquant sur la flèche vers le haut ou vers le bas.
    - Cliquez sur **Actualiser** pour afficher la liste la plus à jour.
    - Recherchez un ordinateur spécifique en tapant son nom dans le champ de recherche.
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Afficher l’état des services en cours d’exécution sur un ordinateur Skype Entreprise

Utilisez le Panneau de Skype Entreprise Server pour afficher tous les services qui s’exécutent sur un ordinateur spécifique dans votre topologie Skype Entreprise Server et voir l’état de chaque service.

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Panneau de Skype Entreprise Server, voir Installer et ouvrir les [outils d’administration.](../../management-tools/install-and-open-administrative-tools.md)
3. Dans la barre de navigation de gauche, cliquez sur **Topologie.**
4. Dans la page État, tiez ou recherchez la liste, si nécessaire, pour trouver l’ordinateur qui vous intéresse, puis cliquez sur le nom de l’ordinateur.
5. Effectuez l’une des opérations suivantes :
    - Pour consulter le dernier état des services en cours d’exécution sur l’ordinateur, cliquez **sur Obtenir l’état du service.**
    - Pour voir la liste des services spécifiques en cours d’exécution sur l’ordinateur et l’état de chaque service, cliquez sur Propriétés, puis cliquez sur **Fermer** pour revenir à la liste.

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Affichage de l’état du service à l’Windows PowerShell cmdlets

Vous pouvez également afficher l’état du service à l’Windows PowerShell l'Get-CsWindowsService cmdlet. Vous pouvez exécuter cette applet de commande à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations, [voir Skype Entreprise Server Management Shell.](../management-shell.md)

**Pour afficher l’état du service**

Pour afficher l’état du service sur un ordinateur, tapez une commande semblable à la suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :

```powershell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

Cette commande renvoie des informations comme celles-ci :

```console
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

Pour plus d’informations, [voir Get-CsWindowsService.](/powershell/module/skype/get-cswindowsservice)

## <a name="start-or-stop-skype-for-business-services"></a>Démarrer ou arrêter Skype Entreprise services

Utilisez le Panneau de Skype Entreprise Server pour démarrer ou arrêter tous les services Skype Entreprise Server en cours d’exécution sur un ordinateur spécifique ou pour démarrer ou arrêter un service spécifique.

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>Démarrer ou arrêter tous les services Skype Entreprise Server sur un ordinateur

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server. Vous pouvez déterminer si le rôle RBAC CsServerAdministrator ou CsAdministrator vous a été affecté en exécutant une commande semblable à la suivante :

    ```powershell
    Get-CsAdminRoleAssignment -Identity "kenmyer"`
    ```

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Panneau de Skype Entreprise Server, voir Installer et ouvrir les [outils d’administration.](../../management-tools/install-and-open-administrative-tools.md)
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.
4. Dans la page État, recherchez dans la liste l’ordinateur qui exécute les services que vous souhaitez démarrer ou arrêter, ou triez cette liste, puis cliquez sur cet ordinateur.
5. Cliquez sur **Action**.
6. Cliquez sur **Démarrer tous les services** ou **Arrêter tous les services**.

### <a name="start-or-stop-a-specific-service"></a>Démarrer ou arrêter un service spécifique

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Panneau de Skype Entreprise Server, voir Installer et ouvrir les [outils d’administration.](../../management-tools/install-and-open-administrative-tools.md)
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.
4. Dans la page État, recherchez dans la liste l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter, ou triez cette liste, puis cliquez sur cet ordinateur.
5. Cliquez sur **Propriétés**.
6. Triez la liste de services, si nécessaire et cliquez sur le service que vous souhaitez démarrer ou arrêter.
7. Cliquez sur **Action**.
8. Cliquez sur **Démarrer le service** ou **Arrêter le service**.
9. Cliquez sur **Fermer**.


## <a name="prevent-sessions-for-services"></a>Empêcher l’exécution de sessions de services

Utilisez le Panneau de Skype Entreprise pour empêcher l’exécution de nouvelles sessions pour tous les services Skype Entreprise Server sur un ordinateur spécifique ou pour empêcher de nouvelles sessions pour un service spécifique.

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>Empêcher de nouvelles sessions pour tous les services Skype Entreprise Server sur un ordinateur

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Panneau de Skype Entreprise Server, voir Installer et ouvrir les [outils d’administration.](../../management-tools/install-and-open-administrative-tools.md)
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.
4. Dans la page État, recherchez dans la liste l’ordinateur qui exécute les services pour lesquels vous souhaitez empêcher toute nouvelle session, puis cliquez sur cet ordinateur.
5. Cliquez sur **Action**.
6. Cliquez sur **Empêcher de nouvelles sessions pour tous les services**.

### <a name="prevent-new-sessions-for-a-specific-service"></a>Empêcher de nouvelles sessions pour un service spécifique

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Panneau de Skype Entreprise Server, voir Installer et ouvrir les [outils d’administration.](../../management-tools/install-and-open-administrative-tools.md)
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.
4. Cliquez sur **Propriétés**.
5. Triez la liste de services, si nécessaire, et cliquez sur le service pour lequel vous souhaitez empêcher toute nouvelle session.
6. Cliquez sur **Action**.
7. Cliquez sur **Empêcher de nouvelles sessions pour le service**.
8. Cliquez sur **Fermer**.