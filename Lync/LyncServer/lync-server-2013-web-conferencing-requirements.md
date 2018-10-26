---
title: Configuration requise pour les fonctions de conférence web
TOCTitle: Configuration requise pour les fonctions de conférence web
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49296319
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise pour les fonctions de conférence web

 

_**Dernière rubrique modifiée :** 2016-12-08_

Si vous avez choisi d’activer les conférences web, vous devez planifier les points suivants :

  -   
    l’accès au magasin de fichiers, qui permet de stocker le contenu des conférences web ;

  -   
    l’intégration à Office Web Apps Server, qui est nécessaire afin de partager des fichiers PowerPoint lors d’une conférence.

## Magasin de fichiers

Le service de conférence web Lync Server 2013 stocke le contenu partagé au cours des réunions dans le magasin de fichiers. Dans le cadre d’un déploiement, vous devez spécifier le partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition ou le pool de serveurs frontauxEnterprise Edition. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou spécifier un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers. Pour plus d’informations, voir Générateur de topologie : définir le magasin de fichiers du serveur frontal. Le service de conférence web chiffre le contenu avant de le stocker dans le magasin de fichiers.

Lync Server 2013 prend en charge l’utilisation des partages de fichiers sur un stockage DAS (Direct Attached Storage) ou un réseau de stockage SAN (Storage Area Network), y compris un système de fichiers distribués (DFS) et sur une solution RAID (Redundant Array Of Independent Disks) pour les magasins de fichiers. Une fois que l’Assistant Déploiement de Lync Server a défini l’emplacement du partage de fichiers, Lync Server crée une structure de dossiers au sein du partage de fichiers qui ressemble à ceci :

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - DataConf

Le service de conférence web stocke ensuite le contenu (diapositives PowerPoint, tableaux blancs, sondages et pièces jointes) dans les dossiers CollabContent et CollabMetadata qui se trouvent dans le dossier WebServices.

L’administrateur doit définir des autorisations sur le partage de fichiers de façon à ce que les groupes RTC disposent de l’accès nécessaire en lecture et en écriture.

> [!WARNING]  
> Si vous rencontrez des erreurs avec les autorisations, ouvrez le Générateur de topologie, téléchargez et republiez la topologie existante. La publication de la topologie permet de vérifier les autorisations du partage de fichiers et de les redéfinir si besoin est.

Vous pouvez utiliser les paramètres suivants pour gérer le mode de stockage du contenu d’une réunion :

  - **ContentGracePeriod**, situé dans [Set-CsConferencingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingConfiguration), définit la durée pendant laquelle le contenu des conférences web reste disponible sur le serveur après la fin de la réunion.

  - **MaxContentStorageMb**, situé dans [Set-CsConferencingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingConfiguration), définit l’espace de fichiers maximal autorisé pour le stockage de contenu au cours d’une seule réunion.

**MaxUploadFileSizeMb** ne limite pas le paramètre de téléchargement de fichier pour Lync Web App. La taille limite de téléchargement de fichier pour Lync Web App est définie à environ 30 Mo et est contrôlée par le fichier web.config IIS : /DataCollabWeb/Int\[Ext\]/Handler/web.config. Pour configurer la taille limite de téléchargement de fichier pour Lync Web App, mettez à jour `maxRequestLength` et `maxAllowedContentLength` dans le fichier web.config, comme indiqué ci-dessous.

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by Lync Web App client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for Lync Web App upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

Vous devez mettre à jour le fichier web.config pour chaque serveur frontal.

## Office Web Apps Server

Afin d’utiliser ces nouvelles fonctionnalités, les administrateurs doivent installer Office Web Apps Server et configurer Lync Server 2013 de façon à communiquer avec Office Web Apps Server. Cette documentation fournit des informations sur la configuration de Lync Server 2013 pour qu’il fonctionne avec Office Web Apps Server. Ce que cette documentation ne fournit pas, ce sont des informations sur l’installation de Office Web Apps Server. Pour en savoir plus sur l’installation, voir le site web Déploiement de Microsoft Office Web Apps sur <http://go.microsoft.com/fwlink/?linkid=257525>. Ce guide inclut des informations préalables complètes concernant Office Web Apps Server. Notez que Office Web Apps Server doit être installé sur un ordinateur autonome qui n’exécute pas Lync Server, SQL Server ou toute autre application serveur. (Aucune version d’Office ne doit être installée sur cet ordinateur.) Sur les ordinateurs utilisés pour exécuter Office Web Apps Server, un ensemble spécifique de logiciels doit par ailleurs être installé (notamment .NET Framework 4.5 et Windows PowerShell 3.0). Ces conditions préalables, ainsi que les informations concernant la configuration des certificats et des services Internet (IIS), sont expliquées en détail sur le site web Déploiement de Microsoft Office Web Apps sur <http://go.microsoft.com/fwlink/?linkid=257525>.

## Voir aussi

#### Concepts

[Vue d’ensemble des conférences web dans Lync Server 2013](lync-server-2013-web-conferencing-overview.md)  
[Liste de vérification du déploiement pour la conférence web dans Lync Server 2013](lync-server-2013-deployment-checklist-for-web-conferencing.md)

