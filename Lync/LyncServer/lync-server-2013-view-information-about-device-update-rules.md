---
title: Afficher des informations sur les règles de mise à jour des périphériques
TOCTitle: Afficher des informations sur les règles de mise à jour des périphériques
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994077(v=OCS.15)
ms:contentKeyID: 53095537
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Afficher des informations sur les règles de mise à jour des périphériques

 

_**Dernière rubrique modifiée :** 2013-02-23_

Vous pouvez afficher des détails sur les règles de mise à jour des périphériques qui ont été importées, notamment le type, le modèle et la marque des périphériques auxquels s’applique la mise à jour, la version et le type de mise à jour, ainsi que les paramètres régionaux et le pool de mise à jour. Ces informations sont disponibles pour toutes les règles de mise à jour des périphériques importées : celles qui sont en attente d’approbation, déployées (approuvées), rappelées (restaurées) et celles que vous avez décidé de ne pas utiliser (réinitialisées). Vous pouvez accéder à ces informations à partir du Panneau de configuration Lync Server ou du Windows PowerShell.

> [!NOTE]  
> Pour plus d’informations sur la façon d’importer, approuver, réinitialiser, restaurer et supprimer des règles, voir les rubriques mentionnées dans l’article <a href="lync-server-2013-device-update-rules.md">Règles de mise à jour des périphériques dans Lync Server 2013</a>.

## Pour afficher les règles de mise à jour des périphériques à l’aide du Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Mise à jour du périphérique**. Les règles importées sont répertoriées dans la page **Mise à jour du périphérique**.

## Affichage de règles de mise à jour des périphériques à l’aide d’applets de commande Windows PowerShell

Vous pouvez également afficher des informations détaillées sur toutes vos règles de mise à jour des périphériques à l’aide de Windows PowerShell et de l’applet de commande **Get-CsDeviceUpdateRule**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell.

> [!NOTE]  
> Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>.

## Pour afficher toutes vos règles de mise à jour des périphériques

  - La commande suivante renvoie des informations relatives à toutes les règles de mise à jour des périphériques configurées pour une utilisation dans votre organisation :
    
        Get-CsDeviceUpdateRule
    
    Cette commande renvoie des informations semblables aux suivantes pour chacune de vos règles de mise à jour des périphériques :
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

## Pour afficher toutes les règles de mise à jour des périphériques sur un serveur spécifique

  - Pour afficher les règles de mise à jour des périphériques sur un ordinateur spécifique, utilisez le paramètre Filter suivi de l’identité de serveur et du caractère générique (\*). Par exemple :
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDeviceUpdateRule).

