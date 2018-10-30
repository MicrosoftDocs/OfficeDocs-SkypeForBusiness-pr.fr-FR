---
title: Suppression d’un compte d’utilisateur de Lync Server
TOCTitle: Suppression d’un compte d’utilisateur de Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49891286
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’un compte d’utilisateur de Lync Server

 

_**Dernière rubrique modifiée :** 2013-02-22_

Vous pouvez utiliser la procédure suivante pour supprimer un compte d’utilisateur précédemment ajouté dans Lync Server 2013.

> [!NOTE]  
> La suppression d’un utilisateur entraînera la perte de tous les paramètres associés au compte d’utilisateur. Si vous souhaitez plutôt désactiver temporairement un compte d’utilisateur, voir la rubrique <a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Désactivation ou réactivation d’un compte d’utilisateur pour Lync Server</a>.

## Pour supprimer un compte d’utilisateur Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.

5.  Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez supprimer.

6.  Dans le menu **Action**, sélectionnez **Supprimer de Lync Server** et une boîte de dialogue apparaît.

7.  Dans la boîte de dialogue, sélectionnez **OK** pour supprimer l’utilisateur.

## Suppression d’un compte d’utilisateur à l’aide des applets de commande PowerShell de Lync Server

Vous pouvez aussi supprimer des comptes d’utilisateur à l’aide de l’applet de commande Disable-CsUser. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Suppression d’un compte d’utilisateur

  - Pour supprimer un compte d’utilisateur, utilisez l’applet de commande Disable-CsUser. Par exemple :
    
        Disable-CsUser -Identity "Ken Myer"
    
    Une fois cette commande exécutée, il n’y a aucun moyen de réactiver le compte et ses anciens paramètres. En revanche, vous pouvez utiliser l’applet de commande Enable-CsUser pour créer un tout nouveau compte pour Ken Myer.

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Disable-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Disable-CsUser).

## Voir aussi

#### Tâches

[Désactivation ou réactivation d’un compte d’utilisateur pour Lync Server](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  

#### Autres ressources

[Activation et désactivation des utilisateurs pour Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

