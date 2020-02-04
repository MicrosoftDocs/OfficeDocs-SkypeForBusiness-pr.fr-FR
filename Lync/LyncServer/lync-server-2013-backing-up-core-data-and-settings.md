---
title: 'Lync Server 2013 : sauvegarde de données principales et de paramètres'
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
ms.openlocfilehash: 4185c02bc85077b0f68ca76d83fd48203e0e5fd9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>Sauvegarder les données principales et les paramètres dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-04-23_

Les procédures suivantes permettent d’utiliser les applets de commande Lync Server Management Shell pour créer des fichiers de sauvegarde des paramètres et des données pour les services principaux. Pour plus d’informations sur les outils utilisés dans cette section, y compris l’endroit où ils se trouvent, voir [Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013 : outils et autorisations](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md). Pour plus d’informations sur l’archivage et l’analyse des données, voir [sauvegarder des bases de données d’archivage et de surveillance dans Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).

<div>


> [!NOTE]  
> Dans cette section, vous pouvez sauvegarder le magasin central de gestion en incluant les paramètres et la configuration de l’archivage et de la surveillance.



</div>

Vous pouvez exécuter les applets de commande décrites dans cette section localement ou à distance.

<div>

## <a name="to-back-up-core-data-and-settings"></a>Pour sauvegarder les données et paramètres de base

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Pour stocker les sauvegardes que vous créez dans les étapes suivantes, créez un dossier partagé et mettez à jour le chemin d’accès référencé par **$Backup** vers le nouveau dossier partagé.

3.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

4.  Sauvegardez le fichier de configuration du magasin de gestion central. Dans la ligne de commande, tapez ce qui suit :
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    Par exemple :
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > Cette étape exporte la topologie de votre serveur Lync, les stratégies et les paramètres de configuration vers un fichier. Aucune autre étape n’est nécessaire pour sauvegarder les données de topologie.

    
    </div>

5.  Copiez le fichier de configuration de la boutique de gestion centralisée\\sauvegardé dans $Backup.

6.  Sauvegarder les données de service des informations de géolocalisation. Dans la ligne de commande, tapez ce qui suit :
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    Par exemple :
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  Copiez le fichier de configuration de service des informations de géolocalisation sur $Backup\\.

8.  Sauvegardez des données utilisateur sur chaque base de données principale d’un pool frontal et sur tous les serveurs Standard Edition Server. Dans la ligne de commande, tapez ce qui suit :
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    Par exemple :
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  Copiez le fichier utilisateur sauvegardé dans $Backup\\.

10. Dans chaque liste qui exécute l’application Response Group, sauvegardez la configuration de Response Group. Procédez comme suit :
    
    1.  Dans la ligne de commande, tapez :
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        Exemple :
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. Copiez le fichier de configuration de groupe de réponse sauvegardé\\dans $Backup.

</div>

</div>

<span> </span>

</div>

</div>

</div>

