---
title: 'Lync Server 2013 : vue d’ensemble de la préparation des services de domaine Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e2712859aa3268b70db9bd126f1ea17463955db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="6c0f3-102">Vue d’ensemble de la préparation des services de domaine Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c0f3-102">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c0f3-103">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="6c0f3-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="6c0f3-104">Pour préparer les services de domaine Active Directory pour votre déploiement Lync Server 2013, vous devez effectuer trois étapes dans un ordre spécifique.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-104">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="6c0f3-105">Le tableau suivant décrit les étapes nécessaires pour préparer AD DS pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-105">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="6c0f3-106">Étapes de préparation d’Active Directory</span><span class="sxs-lookup"><span data-stu-id="6c0f3-106">Active Directory Preparation Steps</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="6c0f3-107">Étape</span><span class="sxs-lookup"><span data-stu-id="6c0f3-107">Step</span></span></th>
<th><span data-ttu-id="6c0f3-108">Description</span><span class="sxs-lookup"><span data-stu-id="6c0f3-108">Description</span></span></th>
<th><span data-ttu-id="6c0f3-109">Emplacement d’exécution</span><span class="sxs-lookup"><span data-stu-id="6c0f3-109">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="6c0f3-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Préparation du schéma Active Directory dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c0f3-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6c0f3-111">Étend le schéma Active Directory en ajoutant de nouvelles classes et attributs utilisés par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-111">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="6c0f3-112">Exécutez une fois pour chaque forêt de votre déploiement où Lync Server sera déployé.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-112">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="6c0f3-113">Sur le contrôleur de schéma dans le domaine racine de chaque forêt où Lync Server sera déployé.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-113">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6c0f3-p101">Il n’est pas nécessaire d’exécuter cette étape dans le domaine racine si vous disposez d’autorisations sur le contrôleur de schéma, mais vous devez être membre du groupe Administrateurs du schéma dans le domaine racine et membre du groupe Administrateurs d’entreprise sur le contrôleur de schéma. Dans une topologie de forêt de ressources, exécutez cette étape uniquement dans la forêt de ressources, et non dans les forêts d’utilisateurs. Dans une topologie de forêt centrale, exécutez cette étape uniquement dans la forêt centrale, et non dans les forêts d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-p101">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master. In a resource forest topology, run this step only in the resource forest, not in any user forests. In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="6c0f3-117"><a href="lync-server-2013-preparing-the-forest.md">Préparation de la forêt pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c0f3-117"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6c0f3-118">Crée des paramètres globaux et des groupes universels qui sont utilisés par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-118">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="6c0f3-119">Exécutez une fois pour chaque forêt de votre déploiement où Lync Server sera déployé.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-119">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="6c0f3-120">Dans le domaine racine de chaque forêt où Lync Server sera déployé.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-120">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="6c0f3-121">Pour effectuer cette tâche, vous devez être membre du groupe Administrateurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-121">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6c0f3-p103">Dans une topologie de forêt de ressources, exécutez cette étape uniquement dans la forêt de ressources, et non dans les forêts d’utilisateurs. Dans une topologie de forêt centrale, exécutez cette étape uniquement dans la forêt centrale, et non dans les forêts d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-p103">In a resource forest topology, run this step only in the resource forest, not in any user forests. In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="6c0f3-124"><a href="lync-server-2013-preparing-domains.md">Préparation des domaines pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6c0f3-124"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="6c0f3-125">Ajoute des autorisations sur les objets utilisés par les membres de groupes universels.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-125">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="6c0f3-126">Exécutez cette opération une seule fois par domaine utilisateur ou domaine serveur.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-126">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6c0f3-127">Si vous effectuez une migration de Lync Server 2010 vers Lync Server 2013, l’Assistant déploiement peut indiquer que la préparation du domaine est déjà terminée.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-127">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="6c0f3-128">Vous n’avez pas besoin de relancer la préparation du domaine.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-128">You do not need to run domain preparation again.</span></span> <span data-ttu-id="6c0f3-129">Les autorisations n’ont pas été modifiées entre Lync Server 2010 et Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-129">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="6c0f3-130">Sur un serveur membre de chaque domaine sur lequel Lync Server est déployé.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-130">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="6c0f3-131">Pour effectuer cette tâche, vous devez être membre du groupe Administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-131">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="6c0f3-132">Lync Server 2013, comme Lync Server 2010, stocke une grande partie des informations de configuration dans le magasin central de gestion et non dans AD DS comme c’était le cas dans Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-132">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="6c0f3-133">Toutefois, les informations suivantes sont stockées dans AD DS :</span><span class="sxs-lookup"><span data-stu-id="6c0f3-133">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="6c0f3-134">**Extensions de schéma** :</span><span class="sxs-lookup"><span data-stu-id="6c0f3-134">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="6c0f3-135">Extensions de l’objet utilisateur</span><span class="sxs-lookup"><span data-stu-id="6c0f3-135">User object extensions</span></span>
    
      - <span data-ttu-id="6c0f3-136">Extensions pour les classes Office Communications Server 2007 R2 afin de maintenir la compatibilité descendante</span><span class="sxs-lookup"><span data-stu-id="6c0f3-136">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="6c0f3-137">**Données** (stockées dans le schéma étendu Lync Server et dans les classes de schéma existantes) :</span><span class="sxs-lookup"><span data-stu-id="6c0f3-137">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="6c0f3-138">URI (Uniform Resource Identifier) SIP de l’utilisateur et autres paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="6c0f3-138">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="6c0f3-139">Objets contact pour des applications telles que le service Response Group et l’Intendant Conférence</span><span class="sxs-lookup"><span data-stu-id="6c0f3-139">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="6c0f3-140">Pointeur vers le magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="6c0f3-140">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="6c0f3-141">Compte d’authentification Kerberos (un objet ordinateur facultatif)</span><span class="sxs-lookup"><span data-stu-id="6c0f3-141">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="6c0f3-142">Dans Lync Server 2013, vous déléguez le programme d’installation et l’administration en accordant des autorisations de configuration au groupe universel RTCUniversalServerAdmins afin que les membres de ce groupe puissent installer et activer Lync Server 2013 sur un serveur local (après que le serveur a été ajouté au topologie, publié et activé).</span><span class="sxs-lookup"><span data-stu-id="6c0f3-142">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="6c0f3-143">Les utilisateurs délégués doivent être des administrateurs locaux sur l’ordinateur sur lequel ils installent et activent Lync Server 2013, mais ils n’ont pas besoin d’être membres du groupe administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-143">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="6c0f3-144">Vous pouvez également accorder des autorisations pour des objets dans des unités d’organisation spécifiées afin que les membres des groupes universels créés lors de la préparation de la forêt puissent accéder à ces objets sans être membres du groupe Administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-144">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="6c0f3-145">Pour les nouveaux déploiements de Lync Server 2013, les paramètres globaux doivent être stockés dans le conteneur de configuration.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-145">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="6c0f3-146">Si votre organisation est en cours de mise à niveau à partir d’une version antérieure et que vous disposez toujours de paramètres globaux dans le conteneur système, le conteneur système est toujours pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-146">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6c0f3-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6c0f3-147">See Also</span></span>


[<span data-ttu-id="6c0f3-148">Préparation du schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c0f3-148">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="6c0f3-149">Extensions de schéma, classes et attributs du schéma Active Directory utilisés par Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c0f3-149">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="6c0f3-150">Préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c0f3-150">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="6c0f3-151">Préparation des domaines pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c0f3-151">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

