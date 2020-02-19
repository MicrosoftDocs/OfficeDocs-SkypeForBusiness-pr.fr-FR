---
title: 'Lync Server 2013 : configuration requise pour les conférences Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b75663f1e5bc51136ac0a2254944541716ad6f74
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Configuration requise pour la conférence Web dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-30_

Si vous avez choisi d’activer la conférence Web, vous devez planifier les éléments suivants :

  - <span></span>  
    Accès au magasin de fichiers, utilisé pour le stockage du contenu de conférence Web.

  - <span></span>  
    Intégration à Office Web Apps Server, nécessaire pour partager des fichiers PowerPoint pendant une conférence.

<div>

## <a name="file-store"></a>magasin de fichiers

Le service de conférence Web Lync Server 2013 stocke le contenu partagé pendant les réunions dans le magasin de fichiers. Dans le cadre du déploiement, vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition ou le pool frontal Enterprise Edition. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou spécifier un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers.Pour plus d’informations, consultez la rubrique générateur de topologies : définir le magasin de fichiers pour le serveur frontal. Le service de conférence Web chiffre le contenu avant de stocker le contenu dans le magasin de fichiers.

Lync Server 2013 prend en charge l’utilisation des partages de fichiers sur le stockage DAS (direct Attached Storage) ou un réseau de zone de stockage (SAN), y compris sur les systèmes de fichiers distribués (DFS) et sur un système RAID (Redundant Array of Independent Disks) pour les magasins de fichiers. Une fois que l’Assistant Déploiement Lync Server a défini l’emplacement du partage de fichiers, Lync Server crée une structure de dossiers dans le partage de fichiers semblable à ce qui suit :

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - )
    
      - Collabmetadata qui
    
      - DataConf

Le service de conférence Web stocke ensuite du contenu tel que des diapositives PowerPoint, des tableaux blancs, des sondages et des pièces jointes dans les dossiers) et Collabmetadata qui, situés dans le dossier WebServices.

L’administrateur doit définir des autorisations sur le partage de fichiers afin que les groupes RTC aient le droit d’accès en lecture et en écriture nécessaire.

<div>


> [!WARNING]  
> Si vous rencontrez des erreurs avec les autorisations, ouvrez le générateur de topologie, téléchargez et republiez la topologie existante. La publication de la topologie permet de vérifier les autorisations de partage de fichiers et de les réinitialiser si nécessaire.



</div>

Vous pouvez utiliser les paramètres suivants pour gérer le mode de stockage du contenu pour une réunion :

  - **ContentGracePeriod**, situé dans [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), définit la durée pendant laquelle le contenu de conférence Web reste sur le serveur après la fin de la réunion.

  - **MaxContentStorageMb**, situé dans [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), définit la quantité maximale d’espace de fichiers autorisée pour le stockage du contenu pendant une seule réunion.

**MaxUploadFileSizeMb** ne limite pas le paramètre de téléchargement de fichiers pour Lync Web App. La limite de téléchargement de taille de fichier pour Lync Web App est définie sur environ 30 Mo et est contrôlée par le fichier Web.\[config\]IIS:/DataCollabWeb/int ext/Handler/Web.config. Pour configurer la limite de chargement de taille de fichier pour Lync Web `maxRequestLength` App `maxAllowedContentLength` , mettez à jour et dans le fichier Web. config, comme indiqué ci-dessous.

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

Vous devez mettre à jour le fichier Web. config pour chaque serveur frontal.

</div>

<div>

## <a name="office-web-apps-server"></a>Office Web Apps Server

Pour pouvoir utiliser ces nouvelles fonctionnalités, les administrateurs doivent installer Office Web Apps Server et configurer Lync Server 2013 pour communiquer avec Office Web Apps Server. Cette documentation fournit des informations sur la configuration de Lync Server 2013 pour qu’il fonctionne avec Office Web Apps Server. Cette documentation ne fournit pas d’informations sur l’installation d’Office Web Apps Server. Pour plus d’informations sur l’installation, voir le site Web de <https://go.microsoft.com/fwlink/p/?linkid=257525>déploiement de Microsoft Office Web Apps à l’adresse. Ce guide contient des informations préalables sur les éléments prérequis pour Office Web Apps Server. Notez qu’Office Web Apps Server doit être installé sur un ordinateur autonome qui n’exécute pas Lync Server, SQL Server ou toute autre application serveur. (Aucune version d’Office ne doit être installée sur cet ordinateur.) Tout ordinateur utilisé pour exécuter Office Web Apps Server doit également disposer d’un ensemble spécifique de logiciels installés (y compris .NET Framework 4,5 et Windows PowerShell 3,0). Ces conditions requises, ainsi que des informations sur la configuration des certificats et des services Internet (IIS), sont décrites en détail dans le site Web de déploiement <https://go.microsoft.com/fwlink/p/?linkid=257525>de Microsoft Office Web Apps à l’adresse.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Vue d’ensemble de la conférence Web dans Lync Server 2013](lync-server-2013-web-conferencing-overview.md)  
[Liste de vérification du déploiement pour la conférence Web dans Lync Server 2013](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

