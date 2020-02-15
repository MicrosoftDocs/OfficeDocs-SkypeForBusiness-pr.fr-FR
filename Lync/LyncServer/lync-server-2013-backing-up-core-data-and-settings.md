---
title: 'Lync Server 2013 : sauvegarde des données et des paramètres principaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a6614a06ea4e5370dd944940d35a690853c171b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>Sauvegarde des données et des paramètres principaux dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-04-23_

Les procédures suivantes utilisent des applets de commande Lync Server Management Shell pour créer des fichiers de sauvegarde pour les paramètres et les données des services principaux. Pour plus d’informations sur les outils utilisés dans cette section, y compris leur emplacement, reportez-vous à la rubrique [Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013 : outils et autorisations](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md). Pour plus d’informations sur la sauvegarde des données d’archivage et de surveillance, voir [sauvegarde des bases de données d’archivage et de surveillance dans Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).

<div>


> [!NOTE]  
> L’étape de cette section pour sauvegarder le magasin central de gestion inclut les paramètres et la configuration de l’archivage et de la surveillance.



</div>

Vous pouvez exécuter les applets de commande décrites dans cette section localement ou à distance.

<div>

## <a name="to-back-up-core-data-and-settings"></a>Pour sauvegarder les données et les paramètres de base

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Pour stocker les sauvegardes que vous créez dans les étapes suivantes, créez un nouveau dossier partagé et mettez à jour le chemin d’accès référencé par **$Backup** vers le nouveau dossier partagé.

3.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

4.  Sauvegardez le fichier de configuration du magasin central de gestion. Sur la ligne de commande, tapez ce qui suit :
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    Par exemple :
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > Cette étape permet d’exporter votre topologie, vos stratégies et vos paramètres de configuration Lync Server dans un fichier. Aucune autre étape n’est requise pour sauvegarder les données de topologie.

    
    </div>

5.  Copiez le fichier de configuration du magasin central de gestion sauvegardé vers\\$Backup.

6.  Sauvegardez les données du service informations d’emplacement. Sur la ligne de commande, tapez ce qui suit :
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    Par exemple :
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  Copiez le fichier de configuration du service informations d’emplacement de sauvegarde\\sur $Backup.

8.  Sauvegardez les données utilisateur sur chaque base de données principale d’un pool frontal et de tous les serveurs Standard Edition. Sur la ligne de commande, tapez ce qui suit :
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    Par exemple :
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  Copiez le fichier utilisateur sauvegardé vers $Backup\\.

10. Sur tous les pools qui exécutent l’application Response Group, sauvegardez la configuration Response Group. Procédez comme suit :
    
    1.  Sur la ligne de commande, tapez :
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        Par exemple :
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. Copiez le fichier de configuration du groupe Response Group sauvegardé\\vers $Backup.

</div>

</div>

<span> </span>

</div>

</div>

</div>

