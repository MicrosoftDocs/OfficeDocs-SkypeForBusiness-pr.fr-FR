---
title: 'Lync Server 2013 : conditions préalables à la sauvegarde pour le basculement du pool ABC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9b609a9867b9ca0e6a01f0ced38445ae55c7367
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Conditions préalables à la sauvegarde pour le basculement du pool ABC dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-26_

Pour tirer le meilleur parti de la procédure de basculement de pool ABC, vous devez effectuer certaines sauvegardes avant le basculement et le basculement :

  - Vous devez sauvegarder régulièrement les données de configuration de LIS (location Information Service) à partir du pool A à l’aide de la cmdlet **Export-CsLISConfiguration** .
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - Vous devez sauvegarder régulièrement les données de configuration du groupe Response Group dans le pool A à l’aide de la cmdlet **Export-applet csrgsconfiguration** .
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    En règle générale, nous vous recommandons d’effectuer des sauvegardes quotidiennes, mais si le volume de vos changements est élevé, vous pouvez planifier des sauvegardes plus fréquentes. La quantité d’informations que vous pouvez perdre en cas de sinistre dépend de la fréquence de vos sauvegardes, ainsi que de la fréquence et du volume des modifications.
    
    L’application Response Group ne peut stocker qu’un seul ensemble de paramètres au niveau de l’application par pool. Ces paramètres sont accessibles via les cmdlets **Get-applet csrgsconfiguration** . Les paramètres incluent la configuration de l’attente musicale par défaut, le fichier audio de l’attente musicale par défaut, la période de grâce de l’agent de grâce et la configuration du contexte de l’appel. Ces paramètres peuvent être transférés d’un pool à un autre via l’applet de commande **Import-applet csrgsconfiguration** à l’aide du paramètre **ReplaceExistingSettings** , mais cette opération remplace tous les paramètres au niveau de l’application dans le pool de destination.
    
    <div>
    

    > [!TIP]  
    > À un emplacement distinct, conservez une copie de sauvegarde de tous les fichiers audio d’origine qui ont été utilisés pour configurer l’application Response Group (c’est-à-dire, tous les enregistrements ou les fichiers de conservation de musique).

    
    </div>
    
    Si vous avez des fichiers de mise en attente musicale personnalisés qui ont été téléchargés pour le parcage d’appel dans un pool, vous devez conserver une copie de ces fichiers dans un autre emplacement. Ces fichiers ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence de Lync Server 2013 et ils seront perdus si les fichiers chargés dans le pool sont endommagés, endommagés ou effacés.
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > L’application de parcage d’appel ne peut stocker qu’un seul ensemble de paramètres et un fichier audio de mise en attente musicale personnalisé par pool. Ces paramètres sont accessibles via la cmdlet <STRONG>Get-CsCpsConfiguration</STRONG> . Étant donné que le mécanisme de récupération d’urgence pour le parcage d’appel repose sur l’application de parcage d’appel du pool de sauvegarde, les paramètres du pool principal ne sont ni sauvegardés ni conservés en cas de sinistre. Si le pool principal est perdu, ces paramètres ne peuvent pas être récupérés et lorsqu’un nouveau pool est déployé pour remplacer le pool principal, les paramètres de parcage d’appel et tout fichier audio de l’attente musicale personnalisé doivent être reconfigurés.

    
    </div>

  - Si vous configurez des annonces dans le cadre de la fonctionnalité de voix numérique non affectée, nous vous recommandons de conserver dans un autre emplacement une copie de tous les fichiers audio d’origine utilisés lors de la configuration initiale. Si vous n’avez pas effectué cette opération, vous pouvez obtenir une copie des fichiers audio configurés dans le magasin de fichiers du serveur ou du pool vers lequel les fichiers audio ont été importés. Ces fichiers ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence de Lync Server 2013 et ils seront perdus si les fichiers chargés dans le pool sont endommagés, endommagés ou effacés. Pour copier tous les fichiers audio utilisés pour configurer la fonctionnalité de voix numérique non attribué à partir du magasin de fichiers d’un serveur ou d’un pool, utilisez :
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - Si vous avez des bases de données de surveillance et d’archivage dans un pool, vous devez utiliser les outils de gestion SQL Server pour les sauvegarder. Dans la procédure de basculement ABC, les bases de données de surveillance et d’archivage ne sont pas conservées si elles sont colocalisées dans le pool A, car ces bases de données ne sont pas sauvegardées via le service de sauvegarde Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

