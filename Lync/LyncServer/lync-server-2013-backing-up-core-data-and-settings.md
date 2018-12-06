---
title: Sauvegarde des données principales et des paramètres
TOCTitle: Sauvegarde des données principales et des paramètres
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202170(v=OCS.15)
ms:contentKeyID: 53095380
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sauvegarde des données principales et des paramètres

 

_**Dernière rubrique modifiée :** 2014-04-23_

Les procédures suivantes utilisent les applets de commande Lync Server Management Shell pour créer des fichiers de sauvegarde pour les paramètres et les données des services principaux. Pour plus d’informations sur les outils utilisés dans cette section, notamment leur emplacement, voir [Spécifications de sauvegarde et de restauration : outils et autorisations](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md). Pour plus d’informations sur la sauvegarde des données d’archivage et de surveillance, voir [Sauvegarde de bases de données d’archivage et de surveillance](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).

> [!NOTE]  
> L’étape figurant dans cette section est destinée à sauvegarder le magasin central de gestion et inclut les paramètres et la configuration d’archivage et de surveillance.

Vous pouvez exécuter les applets de commande décrites dans cette section en local ou à distance.

## Pour sauvegarder les données principales et les paramètres

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins, ouvrez une session sur tout ordinateur de votre déploiement interne.

2.  Pour stocker les sauvegardes que vous créez dans les étapes suivantes, créez un nouveau dossier partagé et mettez à jour le chemin référencé par **$Backup** vers le nouveau dossier partagé.

3.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

4.  Sauvegardez le fichier de configuration du magasin central de gestion. Sur la ligne de commande, tapez ce qui suit :
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    Par exemple :
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    > [!NOTE]  
    > Cette étape exporte votre topologie, vos stratégies et vos paramètres de configuration Lync Server vers un fichier. Aucune autre étape n’est requise pour sauvegarder les données de la topologie.

5.  Copiez le fichier de configuration du magasin central de gestion sauvegardé vers $Backup\\.

6.  Sauvegardez les données du service Informations d’emplacement. Sur la ligne de commande, tapez ce qui suit :
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    Par exemple :
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  Copiez le fichier de configuration du service Informations d’emplacement sauvegardé vers $Backup\\.

8.  Sauvegardez les données utilisateur sur chaque base de données principale d’un pool de serveurs frontaux et chaque serveur Standard Edition. Sur la ligne de commande, tapez ce qui suit :
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    Par exemple :
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  Copiez le fichier utilisateur sauvegardé vers $Backup\\.

10. Sur chaque pool qui exécute l’application Response Group, sauvegardez la configuration Response Group. Procédez comme suit :
    
    1.  Sur la ligne de commande, tapez :
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        Par exemple :
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. Copiez le fichier de configuration Response Group sauvegardé vers $Backup\\.

