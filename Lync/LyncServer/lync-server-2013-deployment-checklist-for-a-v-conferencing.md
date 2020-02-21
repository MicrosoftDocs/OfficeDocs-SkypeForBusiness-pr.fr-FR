---
title: Liste de vérification du déploiement de Lync Server 2013 pour les conférences A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70761edccdf47ef204e9d38b118478abb6e3824f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="c4e0c-102">Liste de vérification du déploiement pour les conférences A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4e0c-102">Deployment checklist for A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4e0c-103">_**Dernière modification de la rubrique :** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="c4e0c-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="c4e0c-104">Comme avec le déploiement de vos autres composants Lync Server 2013, le déploiement d’une conférence A/V nécessite que vous utilisiez le générateur de topologie pour créer et publier une topologie qui incorpore la Conférence.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-104">As with deployment of your other Lync Server 2013 components, deployment of A/V conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="c4e0c-105">Séquence de déploiement</span><span class="sxs-lookup"><span data-stu-id="c4e0c-105">Deployment Sequence</span></span>

<span data-ttu-id="c4e0c-106">Vous pouvez déployer la Conférence en même temps que vous déployez votre topologie initiale ou après avoir déployé au moins un pool frontal ou un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="c4e0c-107">Processus de déploiement de la conférence</span><span class="sxs-lookup"><span data-stu-id="c4e0c-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="c4e0c-108">Le tableau suivant décrit les étapes nécessaires pour déployer la conférence dans une topologie existante.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4e0c-109">Phase</span><span class="sxs-lookup"><span data-stu-id="c4e0c-109">Phase</span></span></th>
<th><span data-ttu-id="c4e0c-110">Étapes</span><span class="sxs-lookup"><span data-stu-id="c4e0c-110">Steps</span></span></th>
<th><span data-ttu-id="c4e0c-111">Rôles et appartenance aux groupes</span><span class="sxs-lookup"><span data-stu-id="c4e0c-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="c4e0c-112">Documentation</span><span class="sxs-lookup"><span data-stu-id="c4e0c-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4e0c-113"><strong>Installer le matériel et les logiciels prérequis</strong></span><span class="sxs-lookup"><span data-stu-id="c4e0c-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e0c-114">La Conférence s’exécute sur les serveurs frontaux d’un pool frontal et de serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-114">Conferencing runs on Front End Servers of a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="c4e0c-115">Aucune configuration matérielle ou logicielle supplémentaire n’est requise en dehors de celle nécessaire à l’installation de ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c4e0c-116">Lync Server 2013 utilise Office Web Apps et Office Web Apps Server pour gérer le partage et le rendu des présentations PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="c4e0c-117">Pour plus d’informations sur l’installation et la configuration d’Office Web Apps Server, voir Configuration de l' <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">intégration à Office Web Apps Server et Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-117">For details about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="c4e0c-118">Utilisateur du domaine qui est membre du groupe Administrateurs local</span><span class="sxs-lookup"><span data-stu-id="c4e0c-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="c4e0c-119"><a href="lync-server-2013-supported-hardware.md">Matériel pris en charge pour Lync Server 2013</a> dans la documentation de prise en charge</span><span class="sxs-lookup"><span data-stu-id="c4e0c-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="c4e0c-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Prise en charge du logiciel et de l’infrastructure serveur dans Lync Server 2013</a> dans la documentation de prise en charge</span><span class="sxs-lookup"><span data-stu-id="c4e0c-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="c4e0c-121"><a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="c4e0c-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Configuration technique requise pour l’archivage dans Lync Server 2013</a> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4e0c-123"><strong>Créer la topologie interne appropriée pour prendre en charge la conférence</strong></span><span class="sxs-lookup"><span data-stu-id="c4e0c-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e0c-124">Exécutez le générateur de topologie pour ajouter la Conférence à la topologie, puis publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="c4e0c-125">Pour définir une topologie, un compte membre du groupe Utilisateurs local</span><span class="sxs-lookup"><span data-stu-id="c4e0c-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="c4e0c-126">Pour publier la topologie, un compte membre du groupe administrateurs du domaine et du groupe RTCUniversalServerAdmins et qui dispose des autorisations de contrôle total (lecture/écriture/modification) sur le partage de fichiers à utiliser pour le magasin de fichiers Lync Server 2013 (afin que le générateur de topologies puisse configurer les DACL requises)</span><span class="sxs-lookup"><span data-stu-id="c4e0c-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="c4e0c-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Définissez et configurez une topologie dans le générateur de topologies pour Lync Server 2013</a> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4e0c-128"><strong>Configurer la prise en charge et les stratégies de conférence</strong></span><span class="sxs-lookup"><span data-stu-id="c4e0c-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="c4e0c-129">Utilisez le panneau de configuration Lync Server 2013 ou Lync Server Management Shell pour configurer les paramètres de conférence.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="c4e0c-130">Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affectez des utilisateurs au rôle [] ou CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="c4e0c-130">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="c4e0c-131"><a href="lync-server-2013-conferencing-policies.md">Stratégies de conférence dans Lync Server 2013</a> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="c4e0c-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c4e0c-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c4e0c-132">See Also</span></span>


[<span data-ttu-id="c4e0c-133">Vue d’ensemble des conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4e0c-133">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)  
[<span data-ttu-id="c4e0c-134">Définition de la configuration requise pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4e0c-134">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

