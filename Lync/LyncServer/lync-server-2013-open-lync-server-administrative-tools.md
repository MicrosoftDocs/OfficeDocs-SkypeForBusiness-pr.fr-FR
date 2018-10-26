---
title: Ouvrir les outils d’administration Lync Server
TOCTitle: Ouvrir les outils d’administration Lync Server
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg195741(v=OCS.15)
ms:contentKeyID: 49298018
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ouvrir les outils d’administration Lync Server

 

_**Dernière rubrique modifiée :** 2012-06-28_

Vous pouvez recourir aux procédures décrites dans cette rubrique pour ouvrir les outils d’administration et déployer, configurer ou dépanner votre topologie Lync Server 2013.

  - Assistant Déploiement

  - Générateur de topologie

  - Panneau de configuration Lync Server 2013

  - Lync Server 2013 Management Shell

## Assistant Déploiement

Procédez comme suit pour démarrer localement l’Assistant Déploiement afin d’ajouter ou de supprimer des fichiers de composants Lync Server 2013.

## Pour démarrer l’Assistant Déploiement Lync Server 2013

1.  Ouvrez une session sur l’ordinateur sur lequel l’Assistant Déploiement de Lync Server est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.

2.  Cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013** et **Assistant Déploiement Lync Server**.

## Générateur de topologie

Procédez comme suit pour ouvrir le Générateur de topologie et définir les serveurs que vous souhaitez déployer dans votre topologie Lync Server 2013.

## Pour ouvrir le Générateur de topologie Lync Server 2013 afin de concevoir la topologie

1.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.
    
    > [!NOTE]  
    > Vous pouvez définir une topologie à l’aide d’un compte membre du groupe Utilisateurs local mais pour lire, publier ou activer une topologie (phase préalable indispensable à l’installation d’un serveur Lync Server 2013, vous devez utiliser un compte membre des groupes Administrateurs du domaine et RTCUniversalServerAdmins et qui dispose des autorisations de contrôle total (à savoir lecture, écriture et modification) sur le partage de fichiers à utiliser pour le magasin de fichiers d’archivage afin que le Générateur de topologie puisse configurer la liste de contrôle d’accès discrétionnaire (DACL) requise ou un compte disposant de droits équivalents.

2.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

## Panneau de configuration Lync Server 2013

Procédez comme suit pour ouvrir le Panneau de configuration Lync Server 2013 afin de gérer la configuration des serveurs, des utilisateurs, des clients et des périphériques dans votre environnement.

> [!NOTE]  
> Vous pouvez utiliser un compte d’utilisateur affecté au rôle CsAdministrator pour réaliser n’importe quelle tâche dans Panneau de configuration Lync Server 2013. Vous pouvez aussi recourir à d’autres rôles pour vous connecter au Panneau de configuration Lync Server 2013 et réaliser des tâches d’administration spécifiques en fonction des opérations qui sont à mener. Par exemple, le rôle CSArchivingAdministrator peut vous permettre de gérer l’archivage dans le Panneau de configuration Lync Server 2013. Pour obtenir des informations sur les rôles, voir <a href="lync-server-2013-planning-for-role-based-access-control.md">Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013</a> dans la documentation de planification. Pour plus d’informations sur les rôles à utiliser pour une tâche en particulier, voir la documentation consacrée à cette dernière.

## Pour ouvrir le Panneau de configuration Lync Server 2013 depuis n’importe quel ordinateur dans le pare-feu de votre organisation

1.  À partir d’un compte d’utilisateur affecté au rôle CsAdministrator ou à un autre rôle doté des droits et des autorisations utilisateur adéquats pour la tâche à réaliser, connectez-vous à un ordinateur dans le cadre de votre déploiement interne avec une résolution d’écran minimale de 1024 x 768.
    
    > [!IMPORTANT]  
    > Si vous avez configuré une URL (Uniform Resource Locator) d’administration simple, vous pouvez accéder au Panneau de configuration Lync Server 2013 depuis un navigateur Internet exécuté sur un ordinateur connecté au pare-feu de votre organisation. Pour plus d’informations sur la configuration d’une URL d’administration simple, voir <a href="lync-server-2013-planning-for-simple-urls.md">Planification des URL simples dans Lync Server 2013</a> dans la documentation de planification et <a href="lync-server-2013-edit-or-configure-simple-urls.md">Modification ou configuration des URL simples dans Lync Server 2013</a> dans la documentation de déploiement.

2.  Ouvrez une fenêtre du navigateur, puis entrez l’URL d’administration configurée pour votre organisation.

## Pour ouvrir le Panneau de configuration Lync Server 2013 sur un ordinateur équipé de Lync Server 2013

1.  À partir d’un compte d’utilisateur membre du rôle CsAdministrator ou d’un autre rôle doté des droits et des autorisations utilisateur adéquats pour la tâche à réaliser, connectez-vous à un ordinateur sur lequel vous avez installé Lync Server 2013 ou, au minimum, les outils d’administration de Lync Server 2013. Pour configurer les paramètres, l’ordinateur doit utiliser une résolution d’écran minimale de 1024 x 768

2.  Pour démarrer le Panneau de configuration Lync Server 2013 : cliquez sur **Démarrer** et **Tous les programmes**, pointez sur **Outils d’administration**, puis sur **Microsoft Lync Server 2013**. Cliquez enfin sur **Panneau de configuration Lync Server 2013**.

## Lync Server 2013 Management Shell

Procédez comme suit pour ouvrir Lync Server 2013 Management Shell et administrer des serveurs, des utilisateurs, des clients et des périphériques dans votre environnement au moyen de la ligne de commande.

> [!NOTE]  
> Vous pouvez utiliser un compte d’utilisateur affecté au rôle CsAdministrator pour effectuer n’importe quelle tâche dans Lync Server 2013 Management Shell. Vous pouvez aussi vous servir d’autres rôles pour réaliser des tâches d’administration précises en fonction de l’opération que vous devez mener. Par exemple, le rôle CSArchivingAdministrator peut vous servir à exécuter des applets de commande inhérentes à l’administration de l’archivage. Pour plus d’informations sur les rôles, voir <a href="lync-server-2013-planning-for-role-based-access-control.md">Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013</a> dans la documentation de planification. Pour plus d’informations sur les rôles qu’il est possible d’utiliser pour l’exécution d’une applet de commande spécifique, voir la documentation consacrée à celle-ci.<br />
Vous pouvez également exécuter certaines applets de commande à l’aide d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, RTCUniversalUserAdmins ou RTCUniversalReadOnlyAdmins, selon l’applet de commande.

## Pour ouvrir Lync Server 2013 Management Shell

  - Par défaut, si vous ouvrez une fenêtre Windows PowerShell, plutôt que Lync Server 2013 Management Shell, vous ne pouvez pas exécuter les applets de commande Lync Server 2013. Pour exécuter les applets de commande Lync Server 2013 depuis Windows PowerShell, tapez ce qui suit à l’invite de commandes Windows PowerShell :
    
    `Import-Module Lync`

  - Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

## Voir aussi

#### Tâches

[Installation des outils d’administration Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)  

#### Concepts

[Outils d’administration de Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)

