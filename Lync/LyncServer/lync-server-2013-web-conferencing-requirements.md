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
ms.openlocfilehash: 186f597c4328c8cee5085e7e599228b60c300a96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Configuration requise pour les conférences Web dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-30_

Si vous avez choisi d’activer les conférences web, vous devez planifier les points suivants :

  - <span></span>  
    Accès au magasin de fichiers permettant de stocker le contenu des conférences web

  - <span></span>  
    Intégration au serveur Office Web Apps Server nécessaire au partage de fichiers PowerPoint lors d’une conférence

<div>

## <a name="file-store"></a>Magasin de fichiers

Le service de conférence Web Lync Server 2013 stocke le contenu partagé pendant les réunions du magasin de fichiers. Dans le cadre du déploiement, vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour le pool frontal Standard Edition Server ou Enterprise Edition. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou spécifier un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel le partage de fichiers doit se trouver et un nom de dossier pour le nouveau partage de fichiers.Pour plus d’informations, reportez-vous à la rubrique générateur de topologies-définir le magasin de fichiers au premier plan. Le service de conférence web chiffre le contenu avant de le stocker dans le magasin de fichiers.

Lync Server 2013 prend en charge l’utilisation des partages de fichiers sur le stockage en attachement direct (DAS) ou sur un réseau de stockage (réseau de stockage), y compris le système de fichiers DFS et sur un réseau redondant de disques indépendants pour les magasins de fichiers. Lorsque l’Assistant Déploiement de Lync Server a défini l’emplacement du partage de fichiers, Lync Server crée une structure de dossiers dans le partage de fichier similaire à ce qui suit :

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - DataConf

Le service de conférence web stocke ensuite le contenu (diapositives PowerPoint, tableaux blancs, sondages et pièces jointes) dans les dossiers CollabContent et CollabMetadata qui se trouvent dans le dossier WebServices.

L’administrateur doit définir des autorisations sur le partage de fichiers de sorte que les groupes RTC aient accès en lecture et en écriture nécessaires.

<div>


> [!WARNING]  
> Si vous rencontrez des erreurs avec les autorisations, ouvrez le générateur de topologies, téléchargez et republiez la topologie existante. La publication de la topologie vérifie les autorisations de partage de fichier et les réinitialise si nécessaire.



</div>

Vous pouvez utiliser les paramètres suivants pour gérer la façon dont le contenu est stocké pour une réunion :

  - **ContentGracePeriod**, qui se trouve dans [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), définit la durée de conservation du contenu de conférences Web sur le serveur une fois la réunion terminée.

  - **MaxContentStorageMb**, situé dans [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), définit le volume maximal d’espace de fichier autorisé pour le stockage du contenu au cours d’une même réunion.

**MaxUploadFileSizeMb** ne limite pas le paramètre de chargement de fichier de Lync Web App. La limite de chargement de taille de fichier pour Lync Web App est définie sur environ 30 Mo et est contrôlée par le fichier Web.\[config\]IIS:/DataCollabWeb/int ext/Handler/Web.config. Pour configurer la limite de chargement de taille de fichier pour Lync Web `maxRequestLength` App `maxAllowedContentLength` , mettez à jour et dans le fichier Web. config, comme illustré ci-dessous.

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

Pour pouvoir utiliser ces nouvelles fonctionnalités, les administrateurs doivent installer Office Web Apps Server et configurer Lync Server 2013 pour communiquer avec Office Web Apps Server. Cette documentation fournit des informations sur la configuration de Lync Server 2013 pour fonctionner avec Office Web Apps Server. La documentation fournie ne fournit pas d’informations sur l’installation d’Office Web Apps Server. Pour plus d’informations sur l’installation, voir le site Web de <http://go.microsoft.com/fwlink/p/?linkid=257525>déploiement de Microsoft Office Web Apps sur. Ce guide inclut des informations complètes relatives à la configuration requise pour Office Web Apps Server. Notez qu’Office Web Apps Server doit être installé sur un ordinateur autonome qui n’exécute pas Lync Server, SQL Server ou une autre application serveur. (Vous ne devez pas avoir installé une version d’Office sur cet ordinateur.) Tout ordinateur utilisé pour exécuter Office Web Apps Server doit également disposer d’un ensemble spécifique de logiciels installés (y compris .NET Framework 4,5 et Windows PowerShell 3,0). Ces conditions, ainsi que des informations sur la configuration des certificats et d’Internet Information Services (IIS), sont décrites en détail dans le site Web de déploiement <http://go.microsoft.com/fwlink/p/?linkid=257525>de Microsoft Office Web Apps à l’adresse.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Présentation de la conférence Web dans Lync Server 2013](lync-server-2013-web-conferencing-overview.md)  
[Liste de vérification de déploiement pour les conférences Web dans Lync Server 2013](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

