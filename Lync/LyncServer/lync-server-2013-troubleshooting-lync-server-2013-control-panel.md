---
title: Dépannage du Panneau de configuration Lync Server 2013
TOCTitle: Dépannage du Panneau de configuration Lync Server 2013
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg195689(v=OCS.15)
ms:contentKeyID: 49297224
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Dépannage du Panneau de configuration Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette rubrique fournit des informations et des procédures susceptibles de vous aider à dépanner l’accès au Panneau de configuration Lync Server 2013.

## Configuration requise du navigateur Internet

Le Panneau de configuration Lync Server nécessite que le plug-in de navigateur Microsoft Silverlight, version 4.0.50524.0 ou ultérieure, soit installé. Si Silverlight n’est pas installé ou si une version antérieure est installée, suivez les instructions du message pour installer la version requise.

> [!NOTE]  
> D’autres spécifications logicielles concernant le Panneau de configuration Lync Server dépendent du système d’exploitation sur lequel le Panneau de configuration Lync Server et tous les outils d’administration Lync Server 2013 peuvent être installés. Pour plus d’informations, voir <a href="lync-server-2013-server-and-tools-operating-system-support.md">Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013</a> dans la documentation de prise en charge.

Si votre navigateur Internet bloque l’installation de Silverlight pour des raisons de sécurité, ajoutez l’URL (Uniform Resource Locator) qui ouvre le Panneau de configuration Lync Server à la liste des sites approuvés. Dans les paramètres de sécurité d’Internet Explorer, vérifiez que **Exécuter les contrôles ActiveX et les plugins** est défini comme **Activé**. Pour plus d’informations, voir [http://go.microsoft.com/fwlink/?linkid=214060\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=214060%26clcid=0x40c). De plus, vérifiez que le navigateur est configuré pour utiliser SSL 3.0.

Si le navigateur Internet est configuré de sorte d’utiliser un serveur proxy, vérifiez qu’il est configuré pour contourner le serveur proxy pour les sites qui sont automatiquement détectés comme des sites internes. Vous pouvez aussi ajouter l’adresse à la liste d’exception du navigateur dans les paramètres de configuration du serveur proxy.

## Spécifications des certificats et enregistrements DNS pour l’URL d’accès administratif

Si vous avez configuré une simple URL pour accéder au Panneau de configuration Lync Server, vérifiez que vous avez également configuré le certificat et l’enregistrement de ressource de l’hôte (A) DNS (Domain Name System) nécessaires pour utiliser cette URL d’accès administratif. Si vous changez l’URL de base à un moment donné, vérifiez que ce changement est répercuté dans le certificat et l’enregistrement DNS appropriés et que vous exécutez *Enable-CsComputer* sur chaque directeur et chaque serveur frontal pour enregistrer la modification. Pour plus d’informations, voir les rubriques suivantes dans la documentation de planification :

  - [Planification des URL simples dans Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

  - [Enregistrements DNS requis pour les URL simples dans Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Exigences de certificat pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

Pour obtenir des procédures pas à pas de configuration de l’URL d’accès administratif, voir [Modification ou configuration des URL simples dans Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) dans la documentation de déploiement.

> [!NOTE]  
> Si vous avez plusieurs cartes réseau sur le serveur web, vous devez configurer manuellement le DNS pour chaque carte réseau pour que la résolution DNS fonctionne correctement.

## Exigences relatives aux services Internet (IIS)

Le Panneau de configuration Lync Server est l’un des composants de Lync Server 2013 qui nécessite les services Internet (IIS). Vérifiez en particulier que les fonctionnalités de redirection HTTP et d’authentification Windows sont activées, et que le service de publication web (W3SVC) est exécuté.

## Dépendance du service de publication World Wide Web (Service Windows)

Quand le service de publication web est arrêté, vous ne pouvez pas accéder au Panneau de configuration Lync Server. Vous pouvez redémarrer le service en utilisant la console MMC (Microsoft Management Console) des services Windows.

**Pour démarrer le service de publication World Wide Web**

1.  Connectez-vous à l’ordinateur où le service de publication World Wide Web est installé dans le cadre des services Internet (IIS).

2.  Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **Services**.

3.  Cliquez avec le bouton droit sur le **Service de publication World Wide Web**, puis cliquez sur **Démarrer**.

## Mode Pool d’applications

Configurez IIS de sorte que le pool d’applications CsManagementAppPool utilise le compte Service réseau pour son identité de modèle de processus.

## Droits et autorisations de l’utilisateur

Vous devez vous connecter au Panneau de configuration Lync Server via un compte de domaine qui est membre du groupe CsAdministrator ou via un compte auquel vous avez délégué les droits et les autorisations de l’utilisateur. Vous ne pouvez pas vous connecter au Panneau de configuration Lync Server à l’aide d’un compte d’ordinateur local. Pour plus d’informations sur la délégation des tâches d’administration via le contrôle d’accès en fonction du rôle (RBAC), voir [Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) dans la documentation de planification.

Si vous utilisez une simple URL pour accéder au Panneau de configuration Lync Server, vérifiez que les serveurs web sont ajoutés aux groupes RTCUniversalServerAdmins et RTCUniversalUserAdmins.

## Voir aussi

#### Concepts

[Outils d’administration de Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)

