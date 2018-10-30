---
title: Désactivation ou réactivation d’un compte d’utilisateur pour Lync Server
TOCTitle: Désactivation ou réactivation d’un compte d’utilisateur pour Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429696(v=OCS.15)
ms:contentKeyID: 49296311
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Désactivation ou réactivation d’un compte d’utilisateur pour Lync Server

 

_**Dernière rubrique modifiée :** 2016-04-04_

Vous pouvez effectuer la procédure suivante pour désactiver un compte d’utilisateur précédemment activé dans Lync Server 2013 sans perdre les paramètres de Lync Server que vous avez configurés pour le compte d’utilisateur. Étant donné que vous ne perdez pas les paramètres du compte d’utilisateur Lync Server, vous pouvez réactiver un compte d’utilisateur précédemment activé sans devoir le reconfigurer.

## Pour désactiver ou réactiver un compte d’utilisateur précédemment activé pour Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez désactiver ou réactiver, puis cliquez sur **Rechercher**.

5.  Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez désactiver ou réactiver.

6.  Dans le menu **Action**, effectuez l’une des opérations suivantes :
    
      - Pour désactiver temporairement le compte d’utilisateur pour Lync Server 2013, cliquez sur **Désactiver temporairement pour Lync Server**.
    
      - Pour activer le compte d’utilisateur pour Lync Server 2013, cliquez sur **Réactiver pour Lync Server**.

## Désactivation et réactivation d’un compte d’utilisateur à l’aide des applets de commande Windows PowerShell

Les comptes d’utilisateurs peuvent également être temporairement désactivés, puis réactivés ultérieurement, à l’aide de l’applet de commande **Set-CsUser**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Désactivation d’un compte d’utilisateur

  - Pour désactiver temporairement un compte d’utilisateur, définissez la valeur de la propriété Enabled sur False ($False). Par exemple :
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

## Réactivation d’un compte d’utilisateur

  - Pour réactiver un compte d’utilisateur désactivé, définissez la valeur de la propriété Enabled sur True ($True). Par exemple :
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUser).

## Voir aussi

#### Tâches

[Ajout et activation d’un compte d’utilisateur pour Lync Server](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  

#### Autres ressources

[Activation et désactivation des utilisateurs pour Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

