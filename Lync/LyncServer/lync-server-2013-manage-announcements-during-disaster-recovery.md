---
title: 'Lync Server 2013 : Gestion des annonces lors de la récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65627e68b31e23908e9fd5258a69862f7ea15b79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a>Gestion des annonces lors de la récupération d’urgence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Lync Server 2013 prend en charge les annonces pour les appels vers des numéros non attribués lors des pannes. La restauration de la fonctionnalité d’annonce pendant une interruption est facultative. Si vous choisissez de restaurer les annonces lors d’une panne, vous devez recréer votre configuration d’annonce dans le pool de sauvegarde. Cette section décrit ce que vous devez faire si vous choisissez de restaurer les annonces lors de la récupération d’urgence.

Cette section s’applique aux plages de nombres non affectées qui utilisent l’application annonce. Cette section ne s’applique pas aux plages de nombres non affectées qui utilisent le standard automatique de messagerie unifiée (MU) Exchange.

<div>

## <a name="before-an-outage"></a>Avant une panne

Que vous choisissiez d’utiliser les annonces au cours d’une période d’indisponibilité, vous devez effectuer des copies de sauvegarde distinctes de tous les fichiers audio personnalisés que vous avez configurés pour l’application d’annonce. Les annonces personnalisées ne sont pas sauvegardées dans le cadre du processus de reprise après sinistre de Lync Server. Si vous n’effectuez pas de sauvegardes distinctes des fichiers et que les fichiers que vous avez téléchargés sur le serveur ou le pool sont endommagés, endommagés ou effacés, ils sont perdus.

Si vous n’avez pas de copies de sauvegarde des fichiers audio personnalisés et que les fichiers audio d’origine ne sont plus disponibles, vous pouvez trouver les fichiers audio que vous avez configurés pour une application d’annonce dans le magasin de fichiers du serveur ou du pool dans lequel vous avez fichiers importés. Vous pouvez copier tous les fichiers audio que vous avez configurés pour l’application annonce à partir du magasin de fichiers.

**Pour copier des fichiers audio à partir du magasin de fichiers**

1.  Dans la ligne de commande, exécutez la commande suivante :
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    Exemple :
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    Où X-ApplicationServer-X fait référence à l’ID de service du serveur d’applications du pool (par exemple, 1-ApplicationServer-1 ")


</div>

<div>

## <a name="during-an-outage"></a>Pendant une période d’interruption

Pour utiliser l’application d’annonce au cours d’une période d’inactivité, vous devez recréer la configuration de l’annonce dans le pool de sauvegarde en effectuant les étapes décrites dans cette section.

<div>


> [!NOTE]  
> Nous vous recommandons d’effectuer ces tâches après le basculement vers le pool de sauvegarde, car dès que vous effectuez l’étape 2, le pool de sauvegarde prend la propriété des plages de numéros non attribués.



</div>

<div>


> [!NOTE]  
> Ces étapes ne sont pas requises pour les plages de nombres qui utilisent un numéro de téléphone de standard automatique de messagerie unifiée Exchange.



</div>

**Pour recréer la configuration d’annonce dans le pool de sauvegarde**

1.  Recréez les annonces que vous avez déployées dans le pool principal du pool de sauvegarde en procédant comme suit:
    
    1.  Importez les fichiers audio utilisés dans le pool principal vers le pool de sauvegarde en utilisant l’applet de passe **Import-CsAnnouncementFile** et en spécifiant le pool de sauvegarde du paramètre parent.
    
    2.  Recréez toutes les annonces à l’aide de l’applet **de nouvelle-CsAnnouncement** et en spécifiant le pool de sauvegarde pour le paramètre parent.
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur l’utilisation de ces paramètres pour créer des annonces dans le pool de sauvegardes, voir <A href="lync-server-2013-create-an-announcement.md">créer une annonce dans Lync Server 2013</A>.

    
    </div>

2.  Une fois toutes les annonces recréées dans le pool de sauvegardes, redirigez toutes les plages de nombres non affectées qui utilisent les annonces du pool principal vers les annonces recréées dans le pool de sauvegarde.
    
    Pour chaque plage de numéros non affecté qui utilise une annonce de la liste principale, exécutez la commande suivante:
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a>Après la panne

Lorsque le pool principal devient disponible, vous devez rediriger les plages de numéros non affectées qui ont été modifiées pour revenir au pool principal.

<div>


> [!NOTE]  
> Ces étapes ne sont pas requises pour les plages de nombres qui utilisent un numéro de téléphone de standard automatique de messagerie unifiée Exchange.



</div>

**Pour restaurer les annonces dans le pool principal**

1.  Si vous deviez reconstruire le pool principal lors de la récupération, vous devez recréer les annonces dans le pool principal en important les fichiers audio et en créant des annonces, comme vous le feriez dans le pool de sauvegarde, à l’exception de la liste principale du parent. paramètre. Pour plus d’informations, consultez la section «au cours d’une interruption» plus haut dans cette rubrique.

2.  Pour chaque plage de nombres non affectée que vous avez modifiée pour l’interruption, exécutez la commande suivante:
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  Vous pouvez également supprimer les annonces que vous avez recréées dans le pool de sauvegarde. Obtenez la liste des annonces de l’application d’annonce de pool de sauvegarde. Dans la ligne de commande, exécutez la commande suivante :
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    Exemple :
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    Dans la liste résultante, recherchez les annonces que vous voulez supprimer et copiez les GUID. Pour chaque annonce que vous voulez supprimer, exécutez:
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    Par exemple :
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

