---
title: "Suppr. des paramètres de configuration d’un serveur d’inscriptions existant"
TOCtitle: "Suppr. des paramètres de configuration d’un serveur d’inscriptions existant"
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182571(v=OCS.15)
ms:contentKeyID: 49298513
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression des paramètres de configuration d’un serveur d’inscriptions existant

 

_**Dernière rubrique modifiée :** 2013-02-23_

Suivez ces étapes pour supprimer un serveur d’inscriptions.

## Pour supprimer un serveur d’inscriptions

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions**.

4.  Dans la page **Serveur d’inscriptions**, dans le champ de recherche, tapez entièrement ou partiellement le nom du serveur d’inscriptions que vous voulez supprimer.

5.  Dans la liste, cliquez sur le serveur d’inscriptions souhaité, cliquez sur **Modifier**, puis sur **Supprimer**.

6.  Cliquez sur **OK**.

## Suppression des paramètres de configuration du serveur d’inscriptions avancé à l’aide des applets de commande Lync Server Management Shell

Vous pouvez également supprimer les paramètres de configuration du serveur d’inscriptions avancé à l’aide de Lync Server Management Shell et de l’applet de commande **Remove-CsProxyConfiguration**. Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour supprimer un ensemble spécifique de paramètres de sécurité du serveur d’inscriptions avancé

  - La commande suivante supprime les paramètres de sécurité du serveur d’inscriptions avancé appliqués au serveur Edge atl-edge-011.litwareinc.com :
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

## Pour supprimer tous les paramètres de sécurité du serveur d’inscriptions avancé appliqués l’étendue Site

  - La commande suivante supprime tous les paramètres de sécurité du serveur d’inscriptions avancé appliqués au service de serveur d’inscriptions avancé :
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

## Pour supprimer tous les paramètres de sécurité du serveur d’inscriptions avancé qui permettent l’authentification NTLM

  - La commande suivante supprime tous les paramètres de sécurité du serveur d’inscriptions avancé qui permettent l’utilisation de NTLM pour l’authentification client :
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

Pour plus d’informations, voir [Remove-CsProxyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsProxyConfiguration).

