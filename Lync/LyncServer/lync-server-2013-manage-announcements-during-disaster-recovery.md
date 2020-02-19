---
title: 'Lync Server 2013 : gestion des annonces lors de la récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f7c54293205ac9246db39950e701074b12a42a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a>Gérer les annonces lors de la récupération d’urgence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Lync Server 2013 prend en charge les annonces pour les appels à des numéros non attribués pendant les pannes. La restauration de la fonctionnalité d’annonces en cas de panne est facultative. Si vous choisissez cette option, vous devez recréer la configuration de vos annonces dans le pool de sauvegarde. Cette section décrit les étapes à effectuer pour pouvoir restaurer les annonces dans le cadre d’une récupération d’urgence.

Cette section s’applique aux plages de numéros non attribués qui utilisent l’application annonce. Elle ne s’applique pas aux plages de numéros non attribués du standard automatique de la messagerie unifiée Exchange.

<div>

## <a name="before-an-outage"></a>Avant une panne

Que vous choisissiez ou non d’utiliser des annonces en cas de panne, vous devez effectuer des sauvegardes distinctes des fichiers audio personnalisés que vous avez configurés pour l’application d’annonce. Les annonces personnalisées ne sont pas sauvegardées dans le cadre du processus de récupération d’urgence de Lync Server. Si vous n’effectuez pas de sauvegardes distinctes des fichiers et que les fichiers que vous avez téléchargés sur le serveur ou le pool sont endommagés, endommagés ou effacés, les fichiers seront perdus.

Si vous n’avez pas de copie de sauvegarde des fichiers audio personnalisés et que les fichiers audio d’origine ne sont plus disponibles, vous pouvez trouver les fichiers audio que vous avez configurés pour une application d’annonce en consultant le magasin de fichiers du serveur ou du pool où vous avez initialement importation des fichiers. Vous pouvez copier tous les fichiers audio que vous avez configurés pour l’application d’annonce à partir du magasin de fichiers.

**Pour copier des fichiers audio à partir du magasin de fichiers**

1.  À partir de la ligne de commande, exécutez la commande suivante :
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    Par exemple :
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    Où X-ApplicationServer-X désigne l’ID de service du serveur d’applications du pool (par exemple, « 1-ApplicationServer-1 »).


</div>

<div>

## <a name="during-an-outage"></a>Lors d’une panne

Pour utiliser l’application d’annonce pendant une panne, vous devez recréer la configuration des annonces dans le pool de sauvegarde en exécutant les tâches décrites dans cette section.

<div>


> [!NOTE]  
> Nous vous recommandons d’effectuer ces étapes après le basculement vers le pool de sauvegarde. En effet, dès que vous avez terminé l’étape 2, le pool de sauvegarde devient propriétaire des plages de numéros non attribués.



</div>

<div>


> [!NOTE]  
> Ces étapes ne sont pas requises pour les plages de numéros qui utilisent un numéro de téléphone du standard automatique de la messagerie unifiée Exchange.



</div>

**Pour recréer la configuration des annonces dans le pool de sauvegarde**

1.  Recréez dans le pool de sauvegarde les annonces initialement déployées dans le pool principal en procédant comme suit :
    
    1.  Importez les fichiers audio du pool principal dans le pool de sauvegarde en exécutant l’applet de commande **Import-CsAnnouncementFile** et en spécifiant le pool de sauvegarde dans le paramètre Parent.
    
    2.  Recréez chaque annonce en exécutant l’applet de commande **New-CsAnnouncement** et en spécifiant le pool de sauvegarde dans le paramètre Parent.
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur l’utilisation de ces paramètres pour créer des annonces dans le pool de sauvegarde, voir <A href="lync-server-2013-create-an-announcement.md">Create an Announcement in Lync Server 2013</A>.

    
    </div>

2.  Lorsque vous avez fini de recréer toutes les annonces dans le pool de sauvegarde, redirigez toutes les plages de numéros non attribués associées aux annonces du pool principal vers les nouvelles annonces du pool de sauvegarde.
    
    Pour chaque plage de numéros non attribués associée à une annonce du pool principal, exécutez la commande suivante :
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a>Après la panne

Lorsque le pool principal est redevenu disponible, vous devez rediriger vers ce pool toutes les plages de numéros non attribués que vous avez modifiées lors de la panne.

<div>


> [!NOTE]  
> Ces étapes ne sont pas requises pour les plages de numéros qui utilisent un numéro de téléphone du standard automatique de la messagerie unifiée Exchange.



</div>

**Pour restaurer des annonces dans le pool principal**

1.  Si vous avez dû recréer le pool principal lors de la récupération d’urgence, vous devez maintenant restaurer les annonces dans ce pool en important les fichiers audio et en recréant les annonces. La procédure est la même que celle utilisée pour recréer les annonces dans le pool de sauvegarde, sauf que vous devez spécifier le pool principal dans le paramètre Parent au lieu du pool de sauvegarde. Pour plus d’informations, voir la section « Lors d’une panne », plus haut dans cette rubrique.

2.  Pour chaque plage de numéros non attribués ayant été modifiée lors de la panne, exécutez la commande suivante :
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  Si vous le souhaitez, supprimez les annonces que vous avez recréées dans le pool de sauvegarde. Obtenir la liste des annonces pour l’application d’annonce de pool de sauvegarde. À partir de la ligne de commande, exécutez la commande suivante :
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    Par exemple :
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    Dans la liste affichée, recherchez les annonces que vous voulez supprimer et copiez leur GUID respectif. Pour chaque annonce à supprimer, exécutez la commande suivante :
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    Par exemple :
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

