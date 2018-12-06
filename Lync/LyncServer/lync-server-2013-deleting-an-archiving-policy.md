---
title: Suppression d’une stratégie d’archivage
TOCTitle: Suppression d’une stratégie d’archivage
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520989(v=OCS.15)
ms:contentKeyID: 49297079
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’une stratégie d’archivage

 

_**Dernière rubrique modifiée :** 2013-02-23_

Vous pouvez supprimer une stratégie utilisateur ou une stratégie de site. La stratégie globale ne peut pas être supprimée. Si vous tentez de supprimer la stratégie globale, Lync Server 2013 réinitialise automatiquement les valeurs par défaut de la stratégie.

> [!NOTE]  
> Si vous avez activé l’intégration d’Microsoft Exchange pour votre déploiement, les stratégies d’Exchange déterminent l’activation de l’archivage pour les utilisateurs qui sont hébergés sur Exchange 2013 et dont les boîtes aux lettres sont placées en archive permanente. Pour plus d’informations, voir <a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies pour l’archivage lors de l’utilisation de l’intégration Exchange Server</a> dans la documentation de déploiement.

## Pour supprimer une stratégie d’utilisateur ou de site pour archivage

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie de l’archivage**.

4.  Dans la liste des stratégies d’archivage, cliquez sur la stratégie utilisateur ou la stratégie de site que vous souhaitez supprimer, cliquez sur **Modifier**, puis sur **Supprimer**.

5.  Cliquez sur **Valider**.

## Suppression de stratégies d’archivage à l’aide des applets de commande Lync Server Management Shell

Vous pouvez également supprimer des stratégies d’archivage à l’aide de Windows PowerShell et de l’applet de commande **Remove-CsArchivingPolicy**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Suppression d’une stratégie d’archivage spécifique

  - À titre d’exemple, **Remove-CsArchivingPolicy** permet de supprimer la stratégie avec la propriété Identity site:Redmond. Notez que lorsqu’une stratégie configurée au niveau de l’étendue Site est supprimée, les utilisateurs précédemment gérés par cette stratégie utiliseront automatiquement à la place la stratégie d’archivage globale. La commande suivante permet de supprimer l’archivage appliqué au site Redmond :
    
        Remove-CsArchivingPolicy -Identity site:Redmond

## Suppression de toutes les stratégies d’archivage appliquées au niveau de l’étendue Utilisateur

  - Cette commande permet de supprimer toutes les stratégies d’archivage appliquées au niveau de l’étendue Utilisateur :
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

## Suppression de toutes les stratégies d’archivage qui désactivent l’archivage interne

  - Cette commande permet de supprimer toutes les stratégies d’archivage où l’archivage interne a été désactivé :
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Remove-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsArchivingPolicy).

## Voir aussi

#### Autres ressources

[Gestion de l'archivage des communications internes et externes dans Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

