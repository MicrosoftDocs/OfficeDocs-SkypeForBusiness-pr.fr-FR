---
title: 'Étape 8 : Mettre des pools hérités hors service'
description: 'Phase 8 : retirer les pools hérités.'
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 8: Decommission legacy pools'
ms:assetid: 1c68e5d8-fb5f-45e6-b6e3-27f5e830c966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204724(v=OCS.15)
ms:contentKeyID: 48183557
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6414fe97b54ed1b487ff722c6b02d4904443841
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563750"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="60722-103">Étape 8 : Mettre des pools hérités hors service</span><span class="sxs-lookup"><span data-stu-id="60722-103">Phase 8: Decommission legacy pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60722-104">_**Dernière modification de la rubrique :** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="60722-104">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="60722-105">La rubrique suivante fournit des instructions sur la mise à jour des entrées DNS, le transfert du serveur de gestion de contenu, la mise hors service des pools et la désactivation et la suppression de serveurs et de pools à partir d’un déploiement hérité de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="60722-105">The following topic provides guidance in updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Lync Server 2010.</span></span> <span data-ttu-id="60722-106">Certaines des procédures répertoriées dans cette section ne sont pas requises.</span><span class="sxs-lookup"><span data-stu-id="60722-106">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="60722-107">Lisez la documentation pour déterminer la procédure de mise hors service à utiliser.</span><span class="sxs-lookup"><span data-stu-id="60722-107">Read the documentation and determine which decommissioning procedure to use.</span></span>

<span data-ttu-id="60722-108">Pour une couverture exhaustive de la suppression des serveurs et des rôles serveur Lync Server 2010, ainsi qu’un guide pas à pas pour la mise en service d’un déploiement de Lync Server 2010, voir « désinstallation de Microsoft Lync Server 2010 et suppression des rôles serveur », qui peut être téléchargé à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227) .</span><span class="sxs-lookup"><span data-stu-id="60722-108">For exhaustive coverage of removing Lync Server 2010 servers and server roles, and a step-by-step guide to decommissioning a Lync Server 2010 deployment, see "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="60722-109">Pour plus d’informations sur la migration et la mise à niveau des applications Microsoft Unified Communications Managed API (UCMA), avant de mettre hors service votre environnement hérité, voir <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="60722-109">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="60722-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="60722-110">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="60722-111">Mettre à jour les enregistrements SRV DNS</span><span class="sxs-lookup"><span data-stu-id="60722-111">Update DNS SRV records</span></span>](update-dns-srv-records.md)

  - <span></span>  
    [<span data-ttu-id="60722-112">Déplacer le serveur de gestion centralisée Lync Server 2010 vers Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60722-112">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>](move-the-lync-server-2010-central-management-server-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="60722-113">Déplacement des annuaires de conférences</span><span class="sxs-lookup"><span data-stu-id="60722-113">Move Conference Directories</span></span>](move-lync-server-2010-conference-directories-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="60722-114">Supprimer l’association au serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="60722-114">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)

  - <span></span>  
    [<span data-ttu-id="60722-115">Supprimer l’association au serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="60722-115">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)

  - <span></span>  
    [<span data-ttu-id="60722-116">Supprimer le serveur frontal Enterprise Edition ou le serveur frontal Standard Edition</span><span class="sxs-lookup"><span data-stu-id="60722-116">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-enterprise-edition-front-end-server-or-standard-edition-front-end-server.md)

  - <span></span>  
    [<span data-ttu-id="60722-117">Suppression des instances et des bases de données SQL Server sur le serveur principal</span><span class="sxs-lookup"><span data-stu-id="60722-117">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

