---
title: Recherche des utilisateurs Lync Server
TOCTitle: Recherche des utilisateurs Lync Server
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429701(v=OCS.15)
ms:contentKeyID: 49296939
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Recherche des utilisateurs Lync Server

 

_**Dernière rubrique modifiée :** 2014-05-14_

Vous pouvez utiliser les résultats d’une requête de recherche pour configurer les utilisateurs de Lync Server 2013. Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne.

Vous pouvez rechercher des utilisateurs à partir du Panneau de configuration Lync Server ou du composant logiciel enfichable Utilisateurs et ordinateurs Active Directory. La procédure suivante explique comment effectuer une recherche d’utilisateurs à partir du Panneau de configuration Lync Server.

> [!NOTE]  
> Dans un environnement doté d’une topologie de forêt centrale, les résultats des recherches risquent d’être erronés si vous recherchez un utilisateur en fonction de son adresse de messagerie. À la place, vous pouvez effectuer une recherche d’utilisateurs en spécifiant un préfixe d’adresse SIP, par exemple, sip:name. Vous pouvez ajouter un filtre de recherche et sélectionner une adresse SIP qui contient une partie de l’adresse de messagerie ou utiliser l’applet de commande <strong>Get-CSUser</strong>.

## Pour rechercher un ou plusieurs utilisateurs

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.

5.  (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
    1.  Cliquez sur la flèche déroulante dans le coin supérieur droit de l’écran, au-dessus de **Résultats de la recherche**, puis sur **Ajouter un filtre**.
    
    2.  Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.
    
    3.  Dans la liste déroulante **Égal à**, cliquez sur **Égal à** ou **Pas égal à**.
    
    4.  Dans la zone de texte, tapez le critère de recherche selon lequel filtrer les résultats, puis cliquez sur **Rechercher**.

6.  les résultats de la recherche apparaissent sous **Résultats de la recherche**. Sélectionnez dans la liste les utilisateurs sur lesquels vous voulez exécuter les tâches de configuration.

## Voir aussi

#### Autres ressources

[Affichage des informations sur les comptes d’utilisateurs activés pour Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[Activation et désactivation des utilisateurs pour Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

