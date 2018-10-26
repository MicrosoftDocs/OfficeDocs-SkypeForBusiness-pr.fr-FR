---
title: Supprimer un numéro d’accès de conférence rendez-vous
TOCTitle: Supprimer un numéro d’accès de conférence rendez-vous
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520956(v=OCS.15)
ms:contentKeyID: 49296398
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supprimer un numéro d’accès de conférence rendez-vous

 

_**Dernière rubrique modifiée :** 2013-02-23_

Suivez cette procédure pour supprimer un numéro d’accès de conférence rendez-vous.

## Pour supprimer un numéro d’accès de conférence rendez-vous

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Numéro d’accès entrant**.

4.  Dans la page, cliquez sur le numéro d’accès que vous souhaitez supprimer dans la liste, cliquez sur **Modifier**, puis sur **Supprimer**.

5.  Cliquez sur **OK**.

## Suppression des numéros d’accès de conférence rendez-vous à l’aide des applets de commande Windows PowerShell

Les numéros d’accès de conférence rendez-vous peuvent également être supprimés à l’aide de Windows PowerShell et de l’applet de commande **Remove-CsDialInConferencingAccessNumber**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Suppression d’un numéro d’accès de conférence rendez-vous spécifique

  - Cette commande permet de supprimer le numéro d’accès de conférence rendez-vous doté de l’ID sip:RedmondDialInAccess@litwareinc.com :
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

## Suppression de tous les numéros d’accès de conférence rendez-vous attribués à une région spécifique

  - Cette commande permet de supprimer tous les numéros d’accès de conférence rendez-vous associés à la région Northwest :
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

## Suppression des numéros d’accès de conférence rendez-vous en fonction de la langue principale

  - Cette commande permet de supprimer tous les numéros d’accès de conférence rendez-vous où l’italien est la langue principale :
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDialInConferencingAccessNumber).

