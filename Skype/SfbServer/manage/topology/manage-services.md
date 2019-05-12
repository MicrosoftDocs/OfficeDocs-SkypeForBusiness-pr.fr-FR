---
title: Gérer les services dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Découvrez comment afficher l’état, démarrer et arrêter les services et empêcher des sessions de services.
ms.openlocfilehash: 78d8b2a16204585a0ff403867617ff709666c4f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911965"
---
# <a name="manage-services-in-skype-for-business-server"></a>Gérer les services dans Skype pour Business Server

Vous pouvez utiliser la Skype pour Business Server Control Panel pour afficher une liste de tous les ordinateurs qui exécutent Skype pour Business Server dans votre topologie, afficher l’état des services, démarrer ou arrêter les services et empêcher les sessions de services.

- [Afficher la liste des ordinateurs qui exécutent Skype pour Business Server](#view-a-list-of-computers-running-skype-for-business-server)
- [Afficher l’état des services s’exécutant sur un ordinateur dans Skype pour les entreprises](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [Démarrer ou arrêter Skype pour les services](#start-or-stop-skype-for-business-services)
- [Empêcher l’exécution de sessions de services](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>Afficher la liste des ordinateurs qui exécutent Skype pour Business Server

Utilisez le Skype pour le panneau de configuration serveur Business pour afficher une liste de tous les ordinateurs qui exécutent Skype pour les entreprises dans votre topologie et voir le statut de service de chacun d’eux. Vous pouvez trier la liste par ordinateur, pool ou site. 

1. À partir d’un compte d’utilisateur qui est affecté à un des rôles d’administration prédéfinis Skype pour Business Server, ouvrez une session n’importe quel ordinateur dans votre déploiement interne. Pour plus d’informations, voir [contrôle d’accès basé sur un rôle (RBAC) pour Skype pour Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Skype pour le panneau de configuration serveur Business, voir [installer et ouvrir Outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**. 
4. Dans la page d’état, effectuez l’une des opérations suivantes selon vos besoins :
    - Triez la liste en cliquant sur **l’ordinateur**, un **Pool**ou un en-tête de colonne de **Site** , puis cliquez sur la flèche vers le haut ou la flèche vers le bas.
    - Cliquez sur **Actualiser** pour afficher la liste la plus récente.
    - Recherche d’un ordinateur spécifique en tapant le nom d’ordinateur dans le champ de recherche.
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>Afficher l’état des services s’exécutant sur un ordinateur dans Skype pour les entreprises

Utilisez le Skype pour Business Server Control Panel pour afficher tous les services qui sont exécutent sur un ordinateur donné de votre Skype pour la topologie du serveur d’entreprise et voir le statut de chaque service.

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Skype pour le panneau de configuration serveur Business, voir [installer et ouvrir Outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Dans la barre de navigation de gauche, cliquez sur **la topologie**.
4. Dans la page statut, triez ou recherchez dans la liste, selon les besoins, pour rechercher l’ordinateur que qui vous intéresse, puis cliquez sur le nom de l’ordinateur.
5. Effectuez l’une des options suivantes :
    - Pour afficher le dernier statut des services qui s’exécutent sur l’ordinateur, cliquez sur **obtenir l’état du service**.
    - Pour afficher la liste des services spécifiques en cours d’exécution sur l’ordinateur et le statut de chaque service, cliquez sur **Propriétés**, puis cliquez sur **Fermer** pour revenir à la liste.

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Affichage de l’état du service à l’aide des applets de commande Windows PowerShell

Vous pouvez également afficher l’état de service à l’aide de Windows PowerShell et l’applet de commande Get-CsWindowsService. Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell. Pour plus d’informations, voir [Skype pour Business Server Management Shell](../management-shell.md).

**Pour afficher l’état du service**

Pour afficher l’état du service sur un ordinateur, tapez une commande semblable à ce qui suit dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :

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

Pour plus d’informations, voir [Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService).

## <a name="start-or-stop-skype-for-business-services"></a>Démarrer ou arrêter Skype pour les services

Utilisez le Skype pour Business Server Control Panel pour démarrer ou arrêter tous les Skype pour les services Business Server s’exécutant sur un ordinateur spécifique ou pour démarrer ou arrêter un service spécifique.

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>Démarrer ou arrêter tous les Skype pour les services Business Server sur un ordinateur

1. À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server . Vous pouvez déterminer si vous avez reçu le CsServerAdministrator ou le rôle CsAdministrator RBAC en exécutant une commande semblable à ce qui suit :

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Skype pour le panneau de configuration serveur Business, voir [installer et ouvrir Outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**. 
4. Sur la page État, tri ou de recherche par le biais de la liste pour trouver l’ordinateur qui exécute les services que vous souhaitez démarrer ou arrêter, puis cliquez dessus.
5. Cliquez sur **Action**.
6. Cliquez sur **Démarrer tous les services** ou **Arrêter tous les services**.

### <a name="start-or-stop-a-specific-service"></a>Démarrer ou arrêter un service spécifique

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Skype pour le panneau de configuration serveur Business, voir [installer et ouvrir Outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**. 
4. Sur la page État, tri ou de recherche par le biais de la liste selon vos besoins pour rechercher l’ordinateur qui exécute le service que vous souhaitez démarrer ou arrêter, puis cliquez dessus.
5. Cliquez sur **Propriétés**.
6. Triez la liste des services, si nécessaire, cliquez sur le service que vous souhaitez démarrer ou arrêter.
7. Cliquez sur **Action**.
8. Cliquez sur **Démarrer le service** ou **Arrêter le service**.
9. Cliquez sur **Fermer**.


## <a name="prevent-sessions-for-services"></a>Empêcher l’exécution de sessions de services

Utilisez le Skype pour Business le panneau de configuration afin d’empêcher de nouvelles sessions pour tous les Skype pour les services Business Server s’exécutant sur un ordinateur spécifique ou de nouvelles sessions pour un service spécifique.

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>Empêcher de nouvelles sessions pour tous les Skype pour les services Business Server sur un ordinateur

1. À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Skype pour le panneau de configuration serveur Business, voir [installer et ouvrir Outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Dans la barre de navigation de gauche, cliquez sur **topologie** , puis cliquez sur **état**.
4. Sur la page État du tri ou recherche par le biais de la liste en tant que nécessaire pour trouver l’ordinateur qui exécute les services pour laquelle vous souhaitez empêcher de nouvelles sessions, puis cliquez dessus.
5. Cliquez sur **Action**.
6. Cliquez sur **empêcher de nouvelles sessions pour tous les services**.

### <a name="prevent-new-sessions-for-a-specific-service"></a>Nouvelles sessions d’un service spécifique

1. À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le Skype pour le panneau de configuration serveur Business, voir [installer et ouvrir Outils d’administration](../../management-tools/install-and-open-administrative-tools.md).
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**. 
4. Cliquez sur **Propriétés**.
5. Triez la liste des services, si nécessaire, cliquez sur le service pour lequel vous voulez empêcher de nouvelles sessions.
6. Cliquez sur **Action**.
7. Cliquez sur **empêcher de nouvelles sessions de service**.
8. Cliquez sur **Fermer**.
