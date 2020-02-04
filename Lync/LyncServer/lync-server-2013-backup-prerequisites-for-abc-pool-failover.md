---
title: 'Lync Server 2013 : prérequis de sauvegarde pour le basculement de pool ABC'
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
ms.openlocfilehash: 37a6b5694d8eaa9467fafa8923bb97423fd6e33f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Conditions préalables à la sauvegarde du basculement de pool ABC dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-26_

Pour tirer le meilleur parti de l’utilisation de la procédure de basculement de pool ABC, vous devez effectuer certaines sauvegardes avant le désastre et le basculement.

  - Lorsque vous utilisez l’applet de cmdlet **Export-CsLISConfiguration** , vous devez régulièrement sauvegarder les données de configuration de l’emplacement de la base de données de la liste.
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - Vous devez régulièrement sauvegarder les données de configuration du groupe de réponses dans le pool A à l’aide de l’applet de passe **Export-CsRgsConfiguration** .
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    En règle générale, il est recommandé d’effectuer des sauvegardes journalières, mais si vous avez un volume élevé de modifications, vous souhaiterez peut-être planifier des sauvegardes plus fréquentes. La quantité d’informations que vous pouvez perdre en cas de sinistre dépend de la fréquence de vos sauvegardes, ainsi que de la fréquence et du volume des modifications.
    
    L’application de groupe de réponse ne peut stocker qu’un ensemble de paramètres au niveau de l’application par liste. Pour accéder à ces paramètres, vous pouvez utiliser les applets **de applet Get-CsRgsConfiguration** . Les paramètres incluent la configuration par défaut de Music-Hold en attente, le fichier audio de musique par défaut, la période de grâce à la sonnerie de l’agent et la configuration du contexte d’appel. Ces paramètres peuvent être transférés d’un pool à un autre par le biais de l’applet de commande **Import-CsRgsConfiguration** à l’aide du paramètre **ReplaceExistingSettings** , mais cette opération remplacera tout paramètre au niveau de l’application dans le pool de destination.
    
    <div>
    

    > [!TIP]  
    > Dans un autre emplacement, conservez une copie de sauvegarde de tous les fichiers audio d’origine que vous avez utilisés pour configurer l’application Response Group (c’est-à-dire tout enregistrement ou fichier de musique en attente).

    
    </div>
    
    Si vous avez des fichiers personnalisés de musique en attente qui ont été téléchargés pour le parc d’appels dans une liste, vous devez conserver une copie de celles-ci dans un autre emplacement. Ces fichiers ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence de Lync Server 2013 et sont perdus si les fichiers téléchargés sur le pool sont endommagés, endommagés ou supprimés.
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > L’application de parc d’appels ne peut stocker qu’un seul ensemble de paramètres et un fichier audio en attente personnalisé par liste. Pour accéder à ces paramètres, vous pouvez utiliser l’applet de passe <STRONG>Get-CsCpsConfiguration</STRONG> . Dans la mesure où le mécanisme de reprise après sinistre pour le stationnement d’appels repose sur l’application de parc d’appels du pool de sauvegarde, les paramètres du pool principal ne sont pas sauvegardés ou conservés en cas de sinistre. Si le pool principal est perdu, ces paramètres ne peuvent pas être récupérés, et lorsqu’un nouveau pool est déployé pour remplacer le pool principal, les paramètres du parc d’appels et tout fichier audio de musique personnalisé doit être reconfiguré.

    
    </div>

  - Si vous configurez des annonces dans le cadre de la fonctionnalité de voix numérique non affectées, nous vous recommandons de conserver dans un autre emplacement une copie de tout fichier audio d’origine utilisé lors de la configuration initiale. Si ce n’est pas le cas, vous pouvez obtenir une copie des fichiers audio configurés dans le magasin de fichiers du serveur ou du pool dans lequel les fichiers audio ont été importés. Ces fichiers ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence de Lync Server 2013 et sont perdus si les fichiers téléchargés sur le pool sont endommagés, endommagés ou supprimés. Pour copier tous les fichiers audio utilisés pour configurer la fonctionnalité vocale numérique non affectée à partir du magasin de fichiers d’un serveur ou d’un pool, utilisez :
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - Si vous avez surveillé et archivé des bases de données dans un pool, vous devez utiliser les outils de gestion SQL Server pour les sauvegarder. Dans la procédure de basculement ABC, les bases de données de surveillance et d’archivage ne sont pas conservées si celles-ci sont colocalisées dans le pool A, car elles ne sont pas sauvegardées via le service de sauvegarde de Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

