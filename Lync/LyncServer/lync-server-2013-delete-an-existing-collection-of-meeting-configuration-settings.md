---
title: "Suppr. d’une collection existante de paramètres de configuration de réunion"
TOCtitle: "Suppr. d’une collection existante de paramètres de configuration de réunion"
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49891446
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’une collection existante de paramètres de configuration de réunion

 

_**Dernière rubrique modifiée :** 2013-02-23_

Vous pouvez supprimer une configuration de site ou utilisateur. La configuration globale ne peut pas être supprimée. Si vous supprimez la configuration globale, ses valeurs par défaut sont automatiquement rétablies.

## Pour supprimer une configuration de réunion utilisateur ou de site

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.

4.  Dans la liste des configurations de réunion, cliquez sur la configuration de site ou de pool que vous voulez supprimer, cliquez sur Modifier, puis cliquez sur Supprimer.

## Suppression des paramètres de configuration de réunion à l’aide des applets de commande Lync Server PowerShell

Les paramètres de réunion peuvent également être supprimés à l’aide de Windows PowerShell et de l’applet de commande Remove-CsMeetingConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Suppression d’une collection spécifique de paramètres de configuration de réunion

  - Cette commande supprime les paramètres de configuration de réunion appliqués au site Redmond :
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

## Suppression de tous les paramètres de configuration de réunion appliqués au niveau du site

  - Cette commande supprime tous les paramètres de configuration de réunion appliqués au niveau du site :
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

## Suppression de tous les paramètres de configuration de réunion qui autorisent les utilisateurs anonymes par défaut

  - Et cette commande supprime tous les paramètres qui autorisent l’admission des utilisateurs anonymes par défaut :
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Remove-CsMeetingConfiguration](ttps://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsMeetingConfiguration).

