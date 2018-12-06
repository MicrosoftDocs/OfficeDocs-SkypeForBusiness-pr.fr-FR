---
title: Désactivation d’un utilisateur pour Voix Entreprise
TOCTitle: Désactivation d’un utilisateur pour Voix Entreprise
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49891329
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Désactivation d’un utilisateur pour Voix Entreprise

 

_**Dernière rubrique modifiée :** 2012-09-21_

Procédez comme suit pour désactiver la fonctionnalité Voix Entreprise pour un compte d’utilisateur activé pour Lync Server 2013.

## Pour désactiver un compte d’utilisateur pour Voix Entreprise

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.

5.  Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez activer pour Voix Entreprise.

6.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

7.  Dans la page **Modifier l’utilisateur Lync Server**, sous **Téléphonie**, cliquez sur l’option de votre choix à l’exception de **Voix Entreprise**.
    
    > [!NOTE]  
    > Pour empêcher un utilisateur d’effectuer des appels audio ou vidéo à l’aide de Lync, sous <strong>Téléphonie</strong>, cliquez sur <strong>Audio/vidéo désactivé</strong>.

8.  Cliquez sur **Valider**.

Désormais, l’utilisateur ne peut plus utiliser la fonctionnalité Voix Entreprise.

## Voir aussi

#### Tâches

[Activation des utilisateurs pour Voix Entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  

#### Autres ressources

[Gestion de Voix Entreprise pour les utilisateurs](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Lync Server Management Shell](lync-server-2013-lync-server-management-shell.md)

