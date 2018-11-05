---
title: 'Lync Server 2013 : Gestion des annonces lors de la récupération d’urgence'
TOCTitle: Gestion des annonces lors de la récupération d’urgence
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49891525
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion des annonces lors de la récupération d’urgence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-23_

Lync Server 2013 prend en charge les annonces pour les appels passés vers des numéros non attribués lors d’une panne. La restauration de la fonctionnalité d’annonces en cas de panne est facultative. Si vous choisissez cette option, vous devez recréer la configuration de vos annonces dans le pool de sauvegarde. Cette section décrit les étapes à effectuer pour pouvoir restaurer les annonces dans le cadre d’une récupération d’urgence.

Cette section concerne les plages de numéros non attribués qui utilisent l’application d’annonce. Elle ne s’applique pas aux plages de numéros non attribués du standard automatique de la messagerie unifiée Exchange.

## Avant une panne

Indépendamment de votre choix d’utiliser ou non les annonces lors des pannes, vous devez sauvegarder séparément tous les fichiers audio personnalisés que vous avez configurés pour l’application d’annonce. Les annonces personnalisées n’étant pas sauvegardées pendant le processus de récupération d’urgence de Lync Server, si vous ne créez pas de sauvegardes distinctes des fichiers, ces derniers seront perdus s’ils sont endommagés ou supprimés lors de leur téléchargement vers le serveur ou le pool.

Si vous ne disposez pas de copies de sauvegarde des fichiers audio personnalisés et que les fichiers audio d’origine ne sont plus disponibles, vous pouvez utiliser les fichiers audio que vous avez configurés pour une application d’annonce, qui se trouvent dans le magasin de fichiers du serveur ou du pool où vous avez initialement importé les fichiers. Vous pouvez copier tous les fichiers audio configurés pour l’application d’annonce stockés dans le magasin de fichiers.

**Pour copier les fichiers audio du magasin de fichiers**

1.  À partir de la ligne de commande, exécutez la commande suivante :
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    Exemple :
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    Où X-ApplicationServer-X désigne l’ID de service du serveur d’applications du pool (par exemple, « 1-ApplicationServer-1 »).


## Lors d’une panne

Pour utiliser l’application d’annonce lors d’une panne, vous devez recréer la configuration des annonces dans le pool de sauvegarde en suivant les étapes décrites dans cette section.

> [!NOTE]  
> Nous vous recommandons d’effectuer ces étapes après le basculement vers le pool de sauvegarde. En effet, dès que vous avez terminé l’étape 2, le pool de sauvegarde devient propriétaire des plages de numéros non attribués.

> [!NOTE]  
> Ces étapes ne sont pas requises pour les plages de numéros qui utilisent un numéro de téléphone du standard automatique de la messagerie unifiée Exchange.

**Pour recréer la configuration des annonces dans le pool de sauvegarde**

1.  Recréez dans le pool de sauvegarde les annonces initialement déployées dans le pool principal en procédant comme suit :
    
    1.  Importez les fichiers audio du pool principal dans le pool de sauvegarde en exécutant l’applet de commande **Import-CsAnnouncementFile** et en spécifiant le pool de sauvegarde dans le paramètre Parent.
    
    2.  Recréez chaque annonce en exécutant l’applet de commande **New-CsAnnouncement** et en spécifiant le pool de sauvegarde dans le paramètre Parent.
    
    > [!NOTE]  
    > Pour plus d’informations sur l’utilisation de ces paramètres pour créer des annonces dans le pool de sauvegarde, reportez-vous à <a href="lync-server-2013-create-an-announcement.md">Création d’une annonce dans Lync Server 2013</a>.

2.  Lorsque vous avez fini de recréer toutes les annonces dans le pool de sauvegarde, redirigez toutes les plages de numéros non attribués associées aux annonces du pool principal vers les nouvelles annonces du pool de sauvegarde.
    
    Pour chaque plage de numéros non attribués associée à une annonce du pool principal, exécutez la commande suivante :
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

## Après la panne

Lorsque le pool principal est redevenu disponible, vous devez rediriger vers ce pool toutes les plages de numéros non attribués que vous avez modifiées lors de la panne.

> [!NOTE]  
> Ces étapes ne sont pas requises pour les plages de numéros qui utilisent un numéro de téléphone du standard automatique de la messagerie unifiée Exchange.

**Pour restaurer les annonces dans le pool principal**

1.  Si vous avez dû recréer le pool principal lors de la récupération d’urgence, vous devez maintenant restaurer les annonces dans ce pool en important les fichiers audio et en recréant les annonces. La procédure est la même que celle utilisée pour recréer les annonces dans le pool de sauvegarde, sauf que vous devez spécifier le pool principal dans le paramètre Parent au lieu du pool de sauvegarde. Pour plus d’informations, reportez-vous à la section « Lors d’une panne », plus haut dans cette rubrique.

2.  Pour chaque plage de numéros non attribués ayant été modifiée lors de la panne, exécutez la commande suivante :
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  Si vous le souhaitez, vous pouvez supprimer les annonces que vous avez recréées dans le pool de sauvegarde. Pour obtenir la liste des annonces du pool de sauvegarde de l’application d’annonce, à partir de la ligne de commande, exécutez la commande suivante :
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    Exemple :
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    Dans la liste affichée, recherchez les annonces que vous voulez supprimer et copiez leur GUID respectif. Pour chaque annonce à supprimer, exécutez la commande suivante :
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    Exemple :
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


