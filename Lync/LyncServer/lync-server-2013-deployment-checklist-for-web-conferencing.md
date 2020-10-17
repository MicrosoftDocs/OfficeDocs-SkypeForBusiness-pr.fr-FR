---
title: Liste de vérification du déploiement de Lync Server 2013 pour les conférences Web
description: Liste de vérification du déploiement de Lync Server 2013 pour les conférences Web.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6194cb71af268a45dc5c142c1814d8c1ef15c09e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562180"
---
# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a><span data-ttu-id="7f602-103">Liste de vérification du déploiement pour la conférence Web dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f602-103">Deployment checklist for web conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f602-104">_**Dernière modification de la rubrique :** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="7f602-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="7f602-105">Comme avec le déploiement de vos autres composants Lync Server 2013, le déploiement de la conférence Web nécessite que vous utilisiez le générateur de topologie pour créer et publier une topologie qui incorpore la Conférence.</span><span class="sxs-lookup"><span data-stu-id="7f602-105">As with deployment of your other Lync Server 2013 components, deployment of web conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="7f602-106">Séquence de déploiement</span><span class="sxs-lookup"><span data-stu-id="7f602-106">Deployment Sequence</span></span>

<span data-ttu-id="7f602-107">Vous pouvez déployer la Conférence en même temps que vous déployez votre topologie initiale ou après avoir déployé au moins un pool frontal ou un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7f602-107">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="7f602-108">Processus de déploiement de la conférence</span><span class="sxs-lookup"><span data-stu-id="7f602-108">Conferencing Deployment Process</span></span>

<span data-ttu-id="7f602-109">Le tableau suivant décrit les étapes nécessaires pour déployer la conférence dans une topologie existante.</span><span class="sxs-lookup"><span data-stu-id="7f602-109">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f602-110">Phase</span><span class="sxs-lookup"><span data-stu-id="7f602-110">Phase</span></span></th>
<th><span data-ttu-id="7f602-111">Étapes</span><span class="sxs-lookup"><span data-stu-id="7f602-111">Steps</span></span></th>
<th><span data-ttu-id="7f602-112">Rôles et appartenance aux groupes</span><span class="sxs-lookup"><span data-stu-id="7f602-112">Roles and group memberships</span></span></th>
<th><span data-ttu-id="7f602-113">Documentation</span><span class="sxs-lookup"><span data-stu-id="7f602-113">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f602-114"><strong>Installer le matériel et les logiciels prérequis</strong></span><span class="sxs-lookup"><span data-stu-id="7f602-114"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="7f602-115">La Conférence s’exécute sur les serveurs frontaux d’un pool frontal et de serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7f602-115">Conferencing runs on Front End Servers in a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="7f602-116">Aucune configuration matérielle ou logicielle supplémentaire n’est requise en dehors de celle nécessaire à l’installation de ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="7f602-116">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7f602-117">Lync Server 2013 utilise Office Web Apps et Office Web Apps Server pour gérer le partage et le rendu des présentations PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="7f602-117">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="7f602-118">Pour plus d’informations sur l’installation et la configuration d’Office Web Apps Server, voir Configuration de l' <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">intégration à Office Web Apps Server et Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7f602-118">For information about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="7f602-119">Utilisateur du domaine qui est membre du groupe Administrateurs local</span><span class="sxs-lookup"><span data-stu-id="7f602-119">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="7f602-120"><a href="lync-server-2013-supported-hardware.md">Matériel pris en charge pour Lync Server 2013</a> dans la documentation de prise en charge</span><span class="sxs-lookup"><span data-stu-id="7f602-120"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="7f602-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Prise en charge du logiciel et de l’infrastructure serveur dans Lync Server 2013</a> dans la documentation de prise en charge</span><span class="sxs-lookup"><span data-stu-id="7f602-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="7f602-122"><a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="7f602-122"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="7f602-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Configuration technique requise pour l’archivage dans Lync Server 2013</a> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="7f602-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f602-124"><strong>Créer la topologie interne appropriée pour prendre en charge la conférence</strong></span><span class="sxs-lookup"><span data-stu-id="7f602-124"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="7f602-125">Exécutez le générateur de topologie pour ajouter la Conférence à la topologie, puis publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="7f602-125">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="7f602-126">Pour définir une topologie, un compte membre du groupe Utilisateurs local</span><span class="sxs-lookup"><span data-stu-id="7f602-126">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="7f602-127">Pour publier la topologie, un compte membre du groupe administrateurs du domaine et du groupe RTCUniversalServerAdmins et qui dispose des autorisations de contrôle total (lecture/écriture/modification) sur le partage de fichiers à utiliser pour le magasin de fichiers Lync Server 2013 (afin que le générateur de topologies puisse configurer les DACL requises)</span><span class="sxs-lookup"><span data-stu-id="7f602-127">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="7f602-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Définissez et configurez une topologie dans le générateur de topologies pour Lync Server 2013</a> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="7f602-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f602-129"><strong>Configurer la prise en charge et les stratégies de conférence</strong></span><span class="sxs-lookup"><span data-stu-id="7f602-129"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="7f602-130">Utilisez le panneau de configuration Lync Server 2013 ou Lync Server Management Shell pour configurer les paramètres de conférence.</span><span class="sxs-lookup"><span data-stu-id="7f602-130">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="7f602-131">Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affectez des utilisateurs au rôle [] ou CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="7f602-131">RTCUniversalServerAdmins group ( Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="7f602-132"><a href="lync-server-2013-conferencing-policies.md">Stratégies de conférence dans Lync Server 2013</a> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="7f602-132"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7f602-133">Lync Server 2013 inclut désormais le paramètre **MaxUploadFileSizeMb** , qui limite la taille des fichiers pouvant être chargés pendant une réunion.</span><span class="sxs-lookup"><span data-stu-id="7f602-133">Lync Server 2013 now includes the **MaxUploadFileSizeMb** setting, which limits the size of files that can be uploaded during a meeting.</span></span> <span data-ttu-id="7f602-134">La valeur par défaut de ce paramètre est de 500 Mo.</span><span class="sxs-lookup"><span data-stu-id="7f602-134">The default value for this setting is 500 MB.</span></span> <span data-ttu-id="7f602-135">Vous pouvez ajuster **MaxUploadFileSizeMb** à l’aide de la cmdlet **Set-CsConferencingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="7f602-135">You can adjust **MaxUploadFileSizeMb** using the **Set-CsConferencingConfiguration** cmdlet.</span></span>

<span data-ttu-id="7f602-136">**MaxUploadFileSizeMb** ne limite pas le paramètre de téléchargement de fichiers pour Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="7f602-136">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="7f602-137">La limite de téléchargement de taille de fichier pour Lync Web App est définie sur environ 30 Mo et est contrôlée par le fichier IIS web.config:/DataCollabWeb/Int \[ ext \] /handler/web.config. Pour configurer la limite de chargement de taille de fichier pour Lync Web App, mettez à jour `maxRequestLength` et `maxAllowedContentLength` dans le fichier web.config, comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7f602-137">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

<span data-ttu-id="7f602-138">Vous devez mettre à jour le fichier web.config pour chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="7f602-138">You must update the web.config file for each Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

