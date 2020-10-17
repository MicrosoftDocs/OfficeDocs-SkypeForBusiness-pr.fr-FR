---
title: Liste de vérification du déploiement de Lync Server 2013 pour les conférences A/V
description: Liste de vérification du déploiement de Lync Server 2013 pour les conférences A/V.
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
ms.openlocfilehash: d9a4584172ed4c01eb163ea51aa4f62c2ce75185
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557770"
---
# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="e09cc-103">Liste de vérification du déploiement pour les conférences A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e09cc-103">Deployment checklist for A/V conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e09cc-104">_**Dernière modification de la rubrique :** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="e09cc-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="e09cc-105">Comme avec le déploiement de vos autres composants Lync Server 2013, le déploiement d’une conférence A/V nécessite que vous utilisiez le générateur de topologie pour créer et publier une topologie qui incorpore la Conférence.</span><span class="sxs-lookup"><span data-stu-id="e09cc-105">As with deployment of your other Lync Server 2013 components, deployment of A/V conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="e09cc-106">Séquence de déploiement</span><span class="sxs-lookup"><span data-stu-id="e09cc-106">Deployment Sequence</span></span>

<span data-ttu-id="e09cc-107">Vous pouvez déployer la Conférence en même temps que vous déployez votre topologie initiale ou après avoir déployé au moins un pool frontal ou un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e09cc-107">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="e09cc-108">Processus de déploiement de la conférence</span><span class="sxs-lookup"><span data-stu-id="e09cc-108">Conferencing Deployment Process</span></span>

<span data-ttu-id="e09cc-109">Le tableau suivant décrit les étapes nécessaires pour déployer la conférence dans une topologie existante.</span><span class="sxs-lookup"><span data-stu-id="e09cc-109">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e09cc-110">Phase</span><span class="sxs-lookup"><span data-stu-id="e09cc-110">Phase</span></span></th>
<th><span data-ttu-id="e09cc-111">Étapes</span><span class="sxs-lookup"><span data-stu-id="e09cc-111">Steps</span></span></th>
<th><span data-ttu-id="e09cc-112">Rôles et appartenance aux groupes</span><span class="sxs-lookup"><span data-stu-id="e09cc-112">Roles and group memberships</span></span></th>
<th><span data-ttu-id="e09cc-113">Documentation</span><span class="sxs-lookup"><span data-stu-id="e09cc-113">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e09cc-114"><strong>Installer le matériel et les logiciels prérequis</strong></span><span class="sxs-lookup"><span data-stu-id="e09cc-114"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="e09cc-115">La Conférence s’exécute sur les serveurs frontaux d’un pool frontal et de serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e09cc-115">Conferencing runs on Front End Servers of a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="e09cc-116">Aucune configuration matérielle ou logicielle supplémentaire n’est requise en dehors de celle nécessaire à l’installation de ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="e09cc-116">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e09cc-117">Lync Server 2013 utilise Office Web Apps et Office Web Apps Server pour gérer le partage et le rendu des présentations PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="e09cc-117">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="e09cc-118">Pour plus d’informations sur l’installation et la configuration d’Office Web Apps Server, voir Configuration de l' <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">intégration à Office Web Apps Server et Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e09cc-118">For details about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="e09cc-119">Utilisateur du domaine qui est membre du groupe Administrateurs local</span><span class="sxs-lookup"><span data-stu-id="e09cc-119">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="e09cc-120"><a href="lync-server-2013-supported-hardware.md">Matériel pris en charge pour Lync Server 2013</a> dans la documentation de prise en charge</span><span class="sxs-lookup"><span data-stu-id="e09cc-120"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="e09cc-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Prise en charge du logiciel et de l’infrastructure serveur dans Lync Server 2013</a> dans la documentation de prise en charge</span><span class="sxs-lookup"><span data-stu-id="e09cc-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="e09cc-122"><a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="e09cc-122"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="e09cc-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Configuration technique requise pour l’archivage dans Lync Server 2013</a> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="e09cc-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e09cc-124"><strong>Créer la topologie interne appropriée pour prendre en charge la conférence</strong></span><span class="sxs-lookup"><span data-stu-id="e09cc-124"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="e09cc-125">Exécutez le générateur de topologie pour ajouter la Conférence à la topologie, puis publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="e09cc-125">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="e09cc-126">Pour définir une topologie, un compte membre du groupe Utilisateurs local</span><span class="sxs-lookup"><span data-stu-id="e09cc-126">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="e09cc-127">Pour publier la topologie, un compte membre du groupe administrateurs du domaine et du groupe RTCUniversalServerAdmins et qui dispose des autorisations de contrôle total (lecture/écriture/modification) sur le partage de fichiers à utiliser pour le magasin de fichiers Lync Server 2013 (afin que le générateur de topologies puisse configurer les DACL requises)</span><span class="sxs-lookup"><span data-stu-id="e09cc-127">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="e09cc-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Définissez et configurez une topologie dans le générateur de topologies pour Lync Server 2013</a> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="e09cc-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e09cc-129"><strong>Configurer la prise en charge et les stratégies de conférence</strong></span><span class="sxs-lookup"><span data-stu-id="e09cc-129"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="e09cc-130">Utilisez le panneau de configuration Lync Server 2013 ou Lync Server Management Shell pour configurer les paramètres de conférence.</span><span class="sxs-lookup"><span data-stu-id="e09cc-130">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="e09cc-131">Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affectez des utilisateurs au rôle [] ou CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="e09cc-131">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="e09cc-132"><a href="lync-server-2013-conferencing-policies.md">Stratégies de conférence dans Lync Server 2013</a> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="e09cc-132"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e09cc-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e09cc-133">See Also</span></span>


[<span data-ttu-id="e09cc-134">Vue d’ensemble des conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e09cc-134">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)  
[<span data-ttu-id="e09cc-135">Définition de la configuration requise pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e09cc-135">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

