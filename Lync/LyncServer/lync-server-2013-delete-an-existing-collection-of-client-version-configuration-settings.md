---
title: "Supp. une coll. existante de par. de configuration de version du client"
TOCtitle: "Supp. une coll. existante de par. de configuration de version du client"
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ898480(v=OCS.15)
ms:contentKeyID: 53095445
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supprimer une collection existante de paramètres de configuration de version du client

 

_**Dernière rubrique modifiée :** 2013-02-23_

Si vous souhaitez supprimer les paramètres de configuration du client configurés précédemment pour un site, vous pouvez le faire depuis le Panneau de configuration Lync Server 2013 ou à l’aide de Lync Server 2013 Management Shell.

## Pour supprimer les paramètres de configuration du client avec le Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration de la version du client**.

4.  Sélectionnez le site, cliquez sur **Modifier**, sur **Supprimer**, puis sur **OK**.

## Suppression des paramètres de configuration de version du client à l’aide d’applets de commande Windows PowerShell

Vous pouvez supprimer les paramètres de configuration de version du client à l’aide de l’applet de commande **Remove-CsClientVersionConfiguration**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour supprimer une collection spécifiée de paramètres de configuration de version du client

  - La commande suivante supprime les paramètres de configuration de version du client au site Redmond :
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

## Pour supprimer tous les paramètres de configuration de version du client appliqués au niveau du site

  - Cette commande supprime tous les paramètres de configuration de version du client configurés au niveau du site :
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

## Pour supprimer tous les paramètres de configuration de version du client en fonction de la valeur de la propriété DefaultAction

  - Cette commande supprime tous les paramètres de configuration de version du client pour lesquels l’action par défaut définie est « Bloquer ».
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Remove-CsClientVersionConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClientVersionConfiguration).

