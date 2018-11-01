---
title: Suppression des paramètres de configuration d’un service web existant
TOCTitle: Suppression des paramètres de configuration d’un service web existant
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182582(v=OCS.15)
ms:contentKeyID: 49298743
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression des paramètres de configuration d’un service web existant

 

_**Dernière rubrique modifiée :** 2013-02-23_

Procédez comme suit pour supprimer une stratégie de service web.

## Pour supprimer une stratégie de service web

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service web**.

4.  Dans le champ de recherche de la page **Service web**, tapez l’intégralité ou une partie du nom de la stratégie à supprimer.

5.  Dans la liste des stratégies, cliquez sur la stratégie que vous souhaitez supprimer, cliquez sur **Modifier**, puis sur **Supprimer**.

6.  Cliquez sur **OK**.

## Suppression des nouveaux paramètres de configuration des services web à l’aide des applets de commande de Lync Server Management Shell

Vous avez également la possibilité de supprimer les paramètres de configuration des services web en utilisant Lync Server Management Shell et l’applet de commande **Remove-CsWebServiceConfiguration**. Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour supprimer une collection de paramètres de configuration des services web

  - La commande suivante supprime les paramètres de sécurité des services web appliqués au site de Redmond :
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

## Pour supprimer tous les paramètres de configuration des services web appliqués à l’étendue du site

  - La commande suivante supprime tous les paramètres de sécurité des services web appliqués à l’étendue des services :
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

## Pour supprimer tous les paramètres de configuration des services web qui autorisent l’authentification des certificats

  - La commande suivante supprime tous les paramètres de sécurité des services web qui autorisent l’authentification des certificats :
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

Pour plus d’informations, voir [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsWebServiceConfiguration).

## Voir aussi

#### Autres ressources

[Configuration de la sécurité](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)

