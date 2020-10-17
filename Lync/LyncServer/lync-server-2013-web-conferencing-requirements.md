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
ms.openlocfilehash: 404ce93e841bbbefd62498a1dbb3da664eb927ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518251"
---
# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="558ad-102">Configuration requise pour la conférence Web dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="558ad-102">Web conferencing requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="558ad-103">_**Dernière modification de la rubrique :** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="558ad-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="558ad-104">Si vous avez choisi d’activer la conférence Web, vous devez planifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="558ad-104">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="558ad-105">Accès au magasin de fichiers, utilisé pour le stockage du contenu de conférence Web.</span><span class="sxs-lookup"><span data-stu-id="558ad-105">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="558ad-106">Intégration à Office Web Apps Server, nécessaire pour partager des fichiers PowerPoint pendant une conférence.</span><span class="sxs-lookup"><span data-stu-id="558ad-106">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="558ad-107">magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="558ad-107">File Store</span></span>

<span data-ttu-id="558ad-108">Le service de conférence Web Lync Server 2013 stocke le contenu partagé pendant les réunions dans le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="558ad-108">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="558ad-109">Dans le cadre du déploiement, vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition ou le pool frontal Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="558ad-109">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="558ad-110">Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou spécifier un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="558ad-110">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="558ad-111">Pour plus d’informations, consultez la rubrique générateur de topologies : définir le magasin de fichiers pour le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="558ad-111">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="558ad-112">Le service de conférence Web chiffre le contenu avant de stocker le contenu dans le magasin de fichiers.</span><span class="sxs-lookup"><span data-stu-id="558ad-112">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="558ad-113">Lync Server 2013 prend en charge l’utilisation des partages de fichiers sur le stockage DAS (direct Attached Storage) ou un réseau de zone de stockage (SAN), y compris sur les systèmes de fichiers distribués (DFS) et sur un système RAID (Redundant Array of Independent Disks) pour les magasins de fichiers.</span><span class="sxs-lookup"><span data-stu-id="558ad-113">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="558ad-114">Une fois que l’Assistant Déploiement Lync Server a défini l’emplacement du partage de fichiers, Lync Server crée une structure de dossiers dans le partage de fichiers semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="558ad-114">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="558ad-115">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="558ad-115">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="558ad-116">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="558ad-116">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="558ad-117">1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="558ad-117">1-WebServices-1</span></span>
    
      - <span data-ttu-id="558ad-118">)</span><span class="sxs-lookup"><span data-stu-id="558ad-118">CollabContent</span></span>
    
      - <span data-ttu-id="558ad-119">Collabmetadata qui</span><span class="sxs-lookup"><span data-stu-id="558ad-119">CollabMetadata</span></span>
    
      - <span data-ttu-id="558ad-120">DataConf</span><span class="sxs-lookup"><span data-stu-id="558ad-120">DataConf</span></span>

<span data-ttu-id="558ad-121">Le service de conférence Web stocke ensuite du contenu tel que des diapositives PowerPoint, des tableaux blancs, des sondages et des pièces jointes dans les dossiers) et Collabmetadata qui, situés dans le dossier WebServices.</span><span class="sxs-lookup"><span data-stu-id="558ad-121">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="558ad-122">L’administrateur doit définir des autorisations sur le partage de fichiers afin que les groupes RTC aient le droit d’accès en lecture et en écriture nécessaire.</span><span class="sxs-lookup"><span data-stu-id="558ad-122">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="558ad-123">Si vous rencontrez des erreurs avec les autorisations, ouvrez le générateur de topologie, téléchargez et republiez la topologie existante.</span><span class="sxs-lookup"><span data-stu-id="558ad-123">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology.</span></span> <span data-ttu-id="558ad-124">La publication de la topologie permet de vérifier les autorisations de partage de fichiers et de les réinitialiser si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="558ad-124">Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="558ad-125">Vous pouvez utiliser les paramètres suivants pour gérer le mode de stockage du contenu pour une réunion :</span><span class="sxs-lookup"><span data-stu-id="558ad-125">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="558ad-126">**ContentGracePeriod**, situé dans [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), définit la durée pendant laquelle le contenu de conférence Web reste sur le serveur après la fin de la réunion.</span><span class="sxs-lookup"><span data-stu-id="558ad-126">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="558ad-127">**MaxContentStorageMb**, situé dans [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), définit la quantité maximale d’espace de fichiers autorisée pour le stockage du contenu pendant une seule réunion.</span><span class="sxs-lookup"><span data-stu-id="558ad-127">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="558ad-128">**MaxUploadFileSizeMb** ne limite pas le paramètre de téléchargement de fichiers pour Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="558ad-128">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="558ad-129">La limite de téléchargement de taille de fichier pour Lync Web App est définie sur environ 30 Mo et est contrôlée par le fichier IIS web.config:/DataCollabWeb/Int \[ ext \] /handler/web.config. Pour configurer la limite de chargement de taille de fichier pour Lync Web App, mettez à jour `maxRequestLength` et `maxAllowedContentLength` dans le fichier web.config, comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="558ad-129">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

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

<span data-ttu-id="558ad-130">Vous devez mettre à jour le fichier web.config pour chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="558ad-130">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="558ad-131">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="558ad-131">Office Web Apps Server</span></span>

<span data-ttu-id="558ad-132">Pour pouvoir utiliser ces nouvelles fonctionnalités, les administrateurs doivent installer Office Web Apps Server et configurer Lync Server 2013 pour communiquer avec Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="558ad-132">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="558ad-133">Cette documentation fournit des informations sur la configuration de Lync Server 2013 pour qu’il fonctionne avec Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="558ad-133">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="558ad-134">Cette documentation ne fournit pas d’informations sur l’installation d’Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="558ad-134">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="558ad-135">Pour plus d’informations sur l’installation, voir le site Web de déploiement de Microsoft Office Web Apps à l’adresse <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="558ad-135">For installation details, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="558ad-136">Ce guide contient des informations préalables sur les éléments prérequis pour Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="558ad-136">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="558ad-137">Notez qu’Office Web Apps Server doit être installé sur un ordinateur autonome qui n’exécute pas Lync Server, SQL Server ou toute autre application serveur.</span><span class="sxs-lookup"><span data-stu-id="558ad-137">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="558ad-138">(Aucune version d’Office ne doit être installée sur cet ordinateur.) Tout ordinateur utilisé pour exécuter Office Web Apps Server doit également disposer d’un ensemble spécifique de logiciels installés (y compris .NET Framework 4,5 et Windows PowerShell 3,0).</span><span class="sxs-lookup"><span data-stu-id="558ad-138">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="558ad-139">Ces conditions requises, ainsi que des informations sur la configuration des certificats et des services Internet (IIS), sont décrites en détail dans le site Web de déploiement de Microsoft Office Web Apps à l’adresse <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="558ad-139">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="558ad-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="558ad-140">See Also</span></span>


[<span data-ttu-id="558ad-141">Vue d’ensemble de la conférence Web dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="558ad-141">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="558ad-142">Liste de vérification du déploiement pour la conférence Web dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="558ad-142">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

