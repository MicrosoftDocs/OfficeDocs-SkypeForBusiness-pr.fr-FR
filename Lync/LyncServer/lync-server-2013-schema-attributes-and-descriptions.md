---
title: 'Lync Server 2013 : attributs et descriptions de schéma'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72da4adb0f660604dba7f20c9ddc333425086df2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="c6422-102">Attributs et descriptions de schéma dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6422-102">Schema attributes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6422-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="c6422-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="c6422-104">Cette section décrit tous les attributs de schéma utilisés par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6422-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="c6422-105">Pour les classes associées à des attributs, voir [attributs de schéma par classe dans Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="c6422-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="c6422-106">Pour obtenir la liste des classes et attributs qui sont des nouveautés de Lync Server 2013, voir [modifications de schéma dans Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="c6422-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="c6422-107">Les attributs qui sont des paires liées sont spécifiés en tant que liens de renvoi ou liens d’arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="c6422-107">Attributes that are linked pairs are specified as forward links or back links.</span></span> <span data-ttu-id="c6422-108">Un attribut qui fait référence à un autre objet est un lien de transfert ; l’attribut de l’autre objet qui fait référence au premier objet est un lien précédent.</span><span class="sxs-lookup"><span data-stu-id="c6422-108">An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link.</span></span> <span data-ttu-id="c6422-109">Les liens de renvoi peuvent être mis à jour de façon à être en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="c6422-109">Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="c6422-110">Certains attributs ont une valeur de masque de bits.</span><span class="sxs-lookup"><span data-stu-id="c6422-110">Some attributes have a bit-mask value.</span></span> <span data-ttu-id="c6422-111">Pour ces attributs, chaque paramètre est représenté par un bit et la valeur décimale affichée représente la position en bits.</span><span class="sxs-lookup"><span data-stu-id="c6422-111">For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position.</span></span> <span data-ttu-id="c6422-112">Les positions de bits commencent par le bit 0.</span><span class="sxs-lookup"><span data-stu-id="c6422-112">Bit positions start with bit 0.</span></span> <span data-ttu-id="c6422-113">Par exemple, 1 (binaire) est du bit 0 défini et 10000 (binaire) est le bit 4 défini.</span><span class="sxs-lookup"><span data-stu-id="c6422-113">For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set.</span></span> <span data-ttu-id="c6422-114">Chaque bit représente une propriété.</span><span class="sxs-lookup"><span data-stu-id="c6422-114">Each bit represents a property.</span></span> <span data-ttu-id="c6422-115">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="c6422-115">The following are some examples:</span></span>

  - <span data-ttu-id="c6422-116">10000 (binaire) a une valeur décimale de 16 (c’est-à-dire que le bit 4 est défini).</span><span class="sxs-lookup"><span data-stu-id="c6422-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="c6422-117">100 millions (binaire) a une valeur décimale de 256 (c’est-à-dire que le bit 8 est défini).</span><span class="sxs-lookup"><span data-stu-id="c6422-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="c6422-118">1100 (binaire) a une valeur décimale de 12 (autrement dit, les bits 2 et 3 sont définis ; les propriétés représentées par les deux bits sont activées).</span><span class="sxs-lookup"><span data-stu-id="c6422-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="c6422-119">1111000001 (binaire) a une valeur décimale de 961 (autrement dit, les bits 0, 6, 7, 8 et 9 sont définis ; les propriétés de chacun de ces bits sont activées).</span><span class="sxs-lookup"><span data-stu-id="c6422-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="c6422-120">Attributs de schéma pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6422-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6422-121">Attribut</span><span class="sxs-lookup"><span data-stu-id="c6422-121">Attribute</span></span></th>
<th><span data-ttu-id="c6422-122">Description</span><span class="sxs-lookup"><span data-stu-id="c6422-122">Description</span></span></th>
<th><span data-ttu-id="c6422-123">Commentaires</span><span class="sxs-lookup"><span data-stu-id="c6422-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6422-124">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="c6422-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="c6422-125">Un attribut existant dans les services de domaine Active Directory, désormais associé aux classes <strong>msRTCSIP-pool</strong> et <strong>msRTCSIP-MonitoringServer</strong> .</span><span class="sxs-lookup"><span data-stu-id="c6422-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="c6422-126">Cet attribut spécifie le nom de domaine complet (FQDN) d’un pool ou d’un serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="c6422-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="c6422-127">La valeur valide de chaque segment est de 63 caractères. une valeur valide pour le nom de domaine complet est de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="c6422-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="c6422-128">Nouveautés de Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-129">msDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="c6422-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="c6422-130">Cet attribut contient la représentation de chaîne du nom unique (DN) de l’objet d’une autre forêt qui correspond à cet objet.</span><span class="sxs-lookup"><span data-stu-id="c6422-130">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object.</span></span> <span data-ttu-id="c6422-131">Cet attribut est utilisé pour l’extension du groupe de distribution et la présence automatique.</span><span class="sxs-lookup"><span data-stu-id="c6422-131">This attribute is used for distribution group expansion and auto attendance.</span></span> <span data-ttu-id="c6422-132">Cet attribut est défini dans le schéma Active Directory par défaut de Windows Server 2003 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-132">This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="c6422-133">Pour éviter d’avoir besoin d’une mise à niveau d’AD DS vers Windows Server 2003 R2, la préparation du schéma Active Directory étend le schéma Windows Server 2003 avec cette définition d’attribut.</span><span class="sxs-lookup"><span data-stu-id="c6422-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="c6422-134">Nouveautés de Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="c6422-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="c6422-136">Cet attribut à valeurs multiples contient les paramètres de la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="c6422-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="c6422-137">Cet attribut est partagé avec la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="c6422-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="c6422-138">Nouveautés de Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="c6422-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="c6422-140">Cet attribut à plusieurs valeurs contient des identificateurs pour les stratégies de conservation qui s’appliquent à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="c6422-141">Les stratégies de blocage préservent les éléments de boîte aux lettres de l’utilisateur pendant la durée de la conservation.</span><span class="sxs-lookup"><span data-stu-id="c6422-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="c6422-142">Cet attribut est partagé avec Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="c6422-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="c6422-143">Nouveautés de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6422-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-144">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="c6422-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="c6422-145">Cet attribut stocke les informations du fournisseur de services d’audioconférence pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="c6422-146">Nouveautés de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-147">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="c6422-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="c6422-148">Cet attribut pointe sur l’entrée de service approuvé pour le contact de l’application.</span><span class="sxs-lookup"><span data-stu-id="c6422-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="c6422-149">Nouveautés de Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-150">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="c6422-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="c6422-151">Cet attribut contient une liste des applications hébergées sur le serveur d’applications.</span><span class="sxs-lookup"><span data-stu-id="c6422-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="c6422-152">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-153">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="c6422-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="c6422-154">Cet attribut spécifie les options du contact de l’application.</span><span class="sxs-lookup"><span data-stu-id="c6422-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="c6422-155">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-156">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="c6422-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="c6422-157">Cet attribut contient la langue principale du contact de l’application.</span><span class="sxs-lookup"><span data-stu-id="c6422-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="c6422-158">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-159">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="c6422-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="c6422-160">Cet attribut à plusieurs valeurs contient les langues secondaires du contact de l’application.</span><span class="sxs-lookup"><span data-stu-id="c6422-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="c6422-161">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-162">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="c6422-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="c6422-163">Cet attribut contient une liste des serveurs d’application appartenant à ce pool.</span><span class="sxs-lookup"><span data-stu-id="c6422-163">This attribute contains a list of application servers that belong to this pool.</span></span> <span data-ttu-id="c6422-164">Le lien transférer correspondant à cet attribut de lien précédent est <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-164">The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-165">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-166">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="c6422-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="c6422-167">Cet attribut pointe vers le pool auquel appartient ce serveur d’applications.</span><span class="sxs-lookup"><span data-stu-id="c6422-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="c6422-168">Il s’agit du lien transférer.</span><span class="sxs-lookup"><span data-stu-id="c6422-168">This is the forward link.</span></span> <span data-ttu-id="c6422-169">Le lien inverse correspondant est <strong>msRTCSIP-ApplicationServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-170">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-171">msRTCSIP-ArchiveDefault (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="c6422-172">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="c6422-173">Obsolète dans Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-174">msRTCSIP-ArchiveDefaultFlags (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-175">Cet attribut spécifie la valeur par défaut globale dans la limite de la forêt pour l’archivage de toutes les communications utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-175">This attribute specifies the global default within the forest boundary for archiving all user communications.</span></span> <span data-ttu-id="c6422-176">Cette opération est appliquée par la couche agent d’archivage.</span><span class="sxs-lookup"><span data-stu-id="c6422-176">This is enforced by the archiving agent layer.</span></span> <span data-ttu-id="c6422-177">La plage de valeurs de cet attribut est la suivante :</span><span class="sxs-lookup"><span data-stu-id="c6422-177">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-178"><strong>Vrai</strong>: archiver tous les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="c6422-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="c6422-179"><strong>False</strong>: ne pas archiver tous les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="c6422-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="c6422-180">Cet attribut contrôle globalement, au sein de la frontière de la forêt, le mode d’archivage des communications utilisateur au sein d’un réseau interne.</span><span class="sxs-lookup"><span data-stu-id="c6422-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="c6422-181"><strong>Comportement 2005 de Live Communications Server (désormais obsolète)</strong></span><span class="sxs-lookup"><span data-stu-id="c6422-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="c6422-182">La plage de valeurs de cet attribut est la suivante :</span><span class="sxs-lookup"><span data-stu-id="c6422-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-183">0 : archiver le corps du message [bit 0]</span><span class="sxs-lookup"><span data-stu-id="c6422-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="c6422-184">1 : ne pas archiver le corps du message [bit 0]</span><span class="sxs-lookup"><span data-stu-id="c6422-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="c6422-185"><strong>Comportement 2007 d’Office Communications Server</strong></span><span class="sxs-lookup"><span data-stu-id="c6422-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="c6422-186">La plage de valeurs de cet attribut est la suivante :</span><span class="sxs-lookup"><span data-stu-id="c6422-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-187">0 : ArchiveFederationDefaultWithoutBody (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="c6422-188">1-2 : ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="c6422-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="c6422-189">3-4 : ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="c6422-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="c6422-190">5 : RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="c6422-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="c6422-191">6 : RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="c6422-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="c6422-192">7 : RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="c6422-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="c6422-193">8 : RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="c6422-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="c6422-194">9 : RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="c6422-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="c6422-195">10 : RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="c6422-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="c6422-196">11 : RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="c6422-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="c6422-197">12 : RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="c6422-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="c6422-198">13 : RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="c6422-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="c6422-199">14 : RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="c6422-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="c6422-200">15 : RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="c6422-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="c6422-201">16 : RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="c6422-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c6422-202">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="c6422-203">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-204">msRTCSIP-ArchiveFederationDefault (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="c6422-205">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="c6422-206">Obsolète dans Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="c6422-208">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="c6422-209">Obsolète dans Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-210">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="c6422-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="c6422-211">Cet attribut est un entier utilisé comme champ de bits pour contrôler si les communications d’un utilisateur unique doivent être archivées.</span><span class="sxs-lookup"><span data-stu-id="c6422-211">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived.</span></span> <span data-ttu-id="c6422-212">Ce contrôle est appliqué par la couche de l’agent d’archivage.</span><span class="sxs-lookup"><span data-stu-id="c6422-212">This control is enforced by the archiving agent layer.</span></span> <span data-ttu-id="c6422-213">Il est marqué pour la réplication de catalogue global.</span><span class="sxs-lookup"><span data-stu-id="c6422-213">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="c6422-214">L’objectif de cet attribut est spécifique à un utilisateur ou à un contact unique.</span><span class="sxs-lookup"><span data-stu-id="c6422-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="c6422-215">Les valeurs valides (et positions de bits associées) dans Lync Server sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6422-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-216">0 : do not Archive (aucun jeu de bits)</span><span class="sxs-lookup"><span data-stu-id="c6422-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="c6422-217">1 : retrait (position de bit 0)</span><span class="sxs-lookup"><span data-stu-id="c6422-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="c6422-218">2 : obsolète (position de bit 1)</span><span class="sxs-lookup"><span data-stu-id="c6422-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="c6422-219">4 : archiver des communications internes (position binaire 2)</span><span class="sxs-lookup"><span data-stu-id="c6422-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="c6422-220">8 : archiver des communications fédérées (position binaire 3)</span><span class="sxs-lookup"><span data-stu-id="c6422-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="c6422-221">Les valeurs précédemment valides dans Live Communications Server 2005 sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6422-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-222">0 : utilisez la valeur par défaut définie par <strong>msRTCSIP-ArchiveDefault</strong> et <strong>msRTCSIP-ArchiveFederation</strong> dans cet ordre de priorité :</span><span class="sxs-lookup"><span data-stu-id="c6422-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-223">1 : Archive</span><span class="sxs-lookup"><span data-stu-id="c6422-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="c6422-224">2 : ne pas archiver</span><span class="sxs-lookup"><span data-stu-id="c6422-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="c6422-225">3 : archiver sans le corps du message</span><span class="sxs-lookup"><span data-stu-id="c6422-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="c6422-226">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-227">msRTCSIP-ArchivingServerData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-228">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="c6422-229">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-230">msRTCSIP-ArchivingServerVersion (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-231">Cet attribut définit la version du service d’archivage.</span><span class="sxs-lookup"><span data-stu-id="c6422-231">This attribute defines the version of the Archiving service.</span></span> <span data-ttu-id="c6422-232">Il s’agit d’un monotonously qui augmente de manière à chaque publication officielle du produit.</span><span class="sxs-lookup"><span data-stu-id="c6422-232">This attribute is a monotonously increasing integer type that increments with each official product release.</span></span> <span data-ttu-id="c6422-233">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6422-233">The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-234">Non défini : Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="c6422-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="c6422-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="c6422-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="c6422-236">                 Live Communications Server 2005 avec SP1</span><span class="sxs-lookup"><span data-stu-id="c6422-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="c6422-237">3 : Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="c6422-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="c6422-238">4 : Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c6422-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c6422-239">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-240">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-241">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="c6422-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="c6422-242">Cet attribut spécifie le nom de domaine complet (FQDN) du serveur principal du pool.</span><span class="sxs-lookup"><span data-stu-id="c6422-242">This attribute specifies the FQDN of the Back End Server of the pool.</span></span> <span data-ttu-id="c6422-243">Étant donné qu’il ne peut exister qu’un serveur principal unique par pool, il s’agit d’un attribut à valeur unique.</span><span class="sxs-lookup"><span data-stu-id="c6422-243">Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="c6422-244">La valeur valide de chaque segment est de 63 caractères. la valeur valide pour le nom de domaine complet est de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="c6422-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="c6422-245">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-246">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="c6422-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="c6422-247">Cet attribut contient l’identificateur du pool qui héberge l’annuaire de conférences.</span><span class="sxs-lookup"><span data-stu-id="c6422-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="c6422-248">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-249">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="c6422-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="c6422-250">Cet attribut contient l’identificateur d’un annuaire de conférences.</span><span class="sxs-lookup"><span data-stu-id="c6422-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="c6422-251">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-252">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="c6422-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="c6422-253">Cet attribut contient l’identificateur du pool dans lequel le répertoire de conférences est déplacé.</span><span class="sxs-lookup"><span data-stu-id="c6422-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="c6422-254">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-255">msRTCSIP-par défaut</span><span class="sxs-lookup"><span data-stu-id="c6422-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="c6422-256">Cet attribut booléen définit si l’utilisation du téléphone est une utilisation par défaut.</span><span class="sxs-lookup"><span data-stu-id="c6422-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="c6422-257">Si cet attribut est défini sur <strong>true</strong>, l’utilisation du téléphone est une utilisation par défaut qui ne peut pas être supprimée par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="c6422-258">Si cet attribut est défini sur <strong>false</strong>, l’utilisation peut être supprimée.</span><span class="sxs-lookup"><span data-stu-id="c6422-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="c6422-259">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-260">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="c6422-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="c6422-261">Cet attribut identifie l’URL Communicator Web Access pour les utilisateurs extérieurs à l’organisation.</span><span class="sxs-lookup"><span data-stu-id="c6422-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="c6422-262">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-263">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="c6422-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="c6422-264">Cet attribut identifie l’URL Communicator Web Access pour les utilisateurs qui se trouvent au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="c6422-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="c6422-265">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-266">msRTCSIP-DefaultLocationProfileLink (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-267">Cet attribut à valeur unique contient le nom unique (DN) d’un objet de classe de profil d’emplacement qui lui est affecté.</span><span class="sxs-lookup"><span data-stu-id="c6422-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="c6422-268">Lien suivant : <strong>ID de lien 11036</strong></span><span class="sxs-lookup"><span data-stu-id="c6422-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="c6422-269">Le lien inverse correspondant est <strong>msRTCSIP-ServerReferenceBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-270">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-271">msRTCSIP-DefaultPolicy (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-272">Cet attribut booléen spécifie si la stratégie est une stratégie par défaut.</span><span class="sxs-lookup"><span data-stu-id="c6422-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="c6422-273">La stratégie est une stratégie par défaut définie sur <strong>true</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-274">Nouveautés d’Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="c6422-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="c6422-275">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-277">Cet attribut spécifie le nom de domaine complet (FQDN) du serveur de périphérie exécutant le service Edge d’accès, s’il est accessible directement ou à partir de l’équilibrage de charge matérielle d’un pool de serveurs exécutant le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="c6422-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="c6422-278">Si les serveurs exécutant le service Edge d’accès ne peuvent être utilisés que par le biais d’un ou de plusieurs directeurs, cet attribut spécifie le nom de domaine complet et, éventuellement, le numéro de port du réalisateur ou du système d’équilibrage de la charge matérielle servant un pool de directeurs.</span><span class="sxs-lookup"><span data-stu-id="c6422-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="c6422-279">La valeur valide de chaque segment est de 63 caractères. la valeur valide pour le nom de domaine complet est de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="c6422-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="c6422-280">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="c6422-281">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-283">Cet attribut représente le numéro de port qui doit être utilisé pour la connexion au serveur exécutant le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="c6422-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="c6422-284">La valeur valide est une valeur entière spécifiant le port à utiliser.</span><span class="sxs-lookup"><span data-stu-id="c6422-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="c6422-285">La valeur par défaut est 5061.</span><span class="sxs-lookup"><span data-stu-id="c6422-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="c6422-286">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="c6422-287">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-289">Cet attribut représente le délai d’expiration de l’abonnement de présence par défaut.</span><span class="sxs-lookup"><span data-stu-id="c6422-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="c6422-290">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-291">msRTCSIP-DefRegistrationTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-292">Cet attribut représente la fenêtre délai d’inscription par défaut.</span><span class="sxs-lookup"><span data-stu-id="c6422-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="c6422-293">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-295">Cet attribut représente la fenêtre délai d’abonnement aux données itinérantes par défaut.</span><span class="sxs-lookup"><span data-stu-id="c6422-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="c6422-296">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="c6422-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="c6422-298">Cet attribut est utilisé dans une topologie de domaine fractionné et contient un nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="c6422-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="c6422-299">Nouveautés de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-300">msRTCSIP-Description (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-301">Cet attribut de chaîne UNICODE à valeur unique contient une description conviviale de ce type de route ou de la règle de normalisation.</span><span class="sxs-lookup"><span data-stu-id="c6422-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="c6422-302">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-303">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-304">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="c6422-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="c6422-305">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-306">msRTCSIP-nom_domaine</span><span class="sxs-lookup"><span data-stu-id="c6422-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="c6422-307">Cet attribut représente un domaine configuré pour le Bureau d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="c6422-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-308">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="c6422-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="c6422-309">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="c6422-310">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-311">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="c6422-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="c6422-312">Cet attribut spécifie le nom de domaine complet du serveur exécutant le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="c6422-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="c6422-313">La valeur valide de chaque segment est de 63 caractères. la valeur valide pour le nom de domaine complet est de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="c6422-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="c6422-314">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-315">msRTCSIP-EnableBestEffortNotify (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-316">Cet attribut détermine si un serveur génère une demande de notification d’utilisation optimale, au lieu d’une demande de notification, en réponse à une demande s’ABONNer à partir d’un client.</span><span class="sxs-lookup"><span data-stu-id="c6422-316">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client.</span></span> <span data-ttu-id="c6422-317">BENOTIFY est une extension d’amélioration des performances du protocole de notification d’abonnement où le serveur génère des demandes BENOTIFY au lieu de demandes de notification normales.</span><span class="sxs-lookup"><span data-stu-id="c6422-317">BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests.</span></span> <span data-ttu-id="c6422-318">Le gain de performance réside dans le fait qu’une demande BENOTIFY ne nécessite pas de réponse de 200 OK du client en fonction de la demande de notification.</span><span class="sxs-lookup"><span data-stu-id="c6422-318">The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="c6422-319">Les valeurs valides sont <strong>true</strong> ou <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c6422-320">Live Communications Server 2003 ne prend pas en charge les demandes BENOTIFY.</span><span class="sxs-lookup"><span data-stu-id="c6422-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="c6422-321">Pour interagir avec des applications serveur écrites à l’aide de l’API serveur Live Communications Server 2003 exécutée sur Live Communications Server 2005 et des serveurs tiers, les demandes BENOTIFY peuvent être désactivées en définissant la valeur sur <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c6422-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="c6422-322">BENOTIFY ne fait actuellement pas partie du processus de normalisation SIP de l’IETF (Internet Engineering Task Force).</span><span class="sxs-lookup"><span data-stu-id="c6422-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="c6422-323">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="c6422-324">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-325">msRTCSIP-EnableFederation (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-326">Cet attribut est un commutateur global utilisé par les administrateurs informatiques pour déterminer si les utilisateurs sont autorisés à communiquer avec des utilisateurs d’autres organisations.</span><span class="sxs-lookup"><span data-stu-id="c6422-326">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations.</span></span> <span data-ttu-id="c6422-327">Il permet à un administrateur de remplacer l’attribut <strong>FederationEnabled</strong> d’un utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="c6422-327">It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute.</span></span> <span data-ttu-id="c6422-328">Cet attribut peut vous aider à protéger le réseau interne contre les attaques via Internet qui peuvent être causées par des vers, des virus ou des attaques ciblées au niveau de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="c6422-328">This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="c6422-329">Les valeurs valides (et positions de bits associées) sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6422-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-330">1 : activé pour la connectivité PIC (Public IM Connectivity)</span><span class="sxs-lookup"><span data-stu-id="c6422-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="c6422-331">2 : réservé (position binaire 1)</span><span class="sxs-lookup"><span data-stu-id="c6422-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="c6422-332">4 : réservé (position binaire 2)</span><span class="sxs-lookup"><span data-stu-id="c6422-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="c6422-333">8 : réservé (position binaire 3)</span><span class="sxs-lookup"><span data-stu-id="c6422-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="c6422-334">16 : le contrôle d’appel distant a été activé [téléphonie] (position bit 4)</span><span class="sxs-lookup"><span data-stu-id="c6422-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="c6422-335">64 : AllowOrganizeMeetingWithAnonymousParticipants (permettre aux utilisateurs d’inviter des utilisateurs anonymes à des réunions (position de bit 6)</span><span class="sxs-lookup"><span data-stu-id="c6422-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="c6422-336">128 : UCEnabled (permettre aux utilisateurs pour les communications unifiées) (position binaire 7)</span><span class="sxs-lookup"><span data-stu-id="c6422-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="c6422-337">256 : EnabledForEnhancedPresence (activer l’utilisateur pour la connectivité de messagerie instantanée publique) (position de bit 8)</span><span class="sxs-lookup"><span data-stu-id="c6422-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="c6422-338">512 : RemoteCallControlDualMode (position binaire 9)</span><span class="sxs-lookup"><span data-stu-id="c6422-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c6422-339">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="c6422-340">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-341">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="c6422-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="c6422-342">Cet attribut indique si les services d’entreprise sont chargés sur le serveur donné.</span><span class="sxs-lookup"><span data-stu-id="c6422-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-343">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="c6422-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="c6422-344">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-345">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="c6422-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="c6422-346">Cet attribut contient le code de numérotation pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="c6422-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="c6422-347">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-348">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="c6422-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="c6422-349">Cet attribut détermine si un utilisateur unique est activé pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="c6422-349">This attribute controls whether a single user is enabled for federation.</span></span> <span data-ttu-id="c6422-350">Elle est appliquée par la couche services d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="c6422-350">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="c6422-351">Il est marqué pour la réplication de catalogue global.</span><span class="sxs-lookup"><span data-stu-id="c6422-351">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="c6422-352">Les valeurs valides sont <strong>true</strong> ou <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-353">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-354">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="c6422-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="c6422-355">Cet attribut est une liste à plusieurs valeurs des noms de domaine de tous les serveurs Enterprise Edition associés à un pool.</span><span class="sxs-lookup"><span data-stu-id="c6422-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="c6422-356">Lien précédent : <strong>ID de lien 11023</strong></span><span class="sxs-lookup"><span data-stu-id="c6422-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="c6422-357">Le lien transférer correspondant à ce lien précédent est <strong>msRTCSIP-PoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-358">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-359">msRTCSIP-passerelles (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-360">Cet attribut de chaîne à valeurs multiples contient une liste des passerelles et des ports (par passerelle).</span><span class="sxs-lookup"><span data-stu-id="c6422-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="c6422-361">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-362">msRTCSIP-GlobalSettingsData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-363">Cet attribut stocke les paires nom : valeur.</span><span class="sxs-lookup"><span data-stu-id="c6422-363">This attribute stores name:value pairs.</span></span> <span data-ttu-id="c6422-364">Le nom déjà défini : paire de valeurs correspond au paramètre <strong>autoriser l’interrogation pour la présence</strong> .</span><span class="sxs-lookup"><span data-stu-id="c6422-364">The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="c6422-365">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-366">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="c6422-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="c6422-367">Cet attribut est un identificateur unique d’un groupe qui est utilisé pour regrouper les entrées du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="c6422-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="c6422-368">Nouveautés de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-369">msRTCSIP-HomeServer (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="c6422-370">Nouveautés de Live Communications Server 2003 (non utilisés).</span><span class="sxs-lookup"><span data-stu-id="c6422-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="c6422-371">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-372">msRTCSIP-HomeServerString (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="c6422-373">Nouveautés de Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="c6422-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="c6422-374">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-375">msRTCSIP-HomeUsers (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="c6422-376">Nouveautés de Live Communications Server 2003 (non utilisés).</span><span class="sxs-lookup"><span data-stu-id="c6422-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="c6422-377">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-378">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="c6422-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="c6422-379">Cet attribut détermine si un utilisateur unique est activé pour l’accès extérieur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-379">This attribute controls whether a single user is enabled for outside user access.</span></span> <span data-ttu-id="c6422-380">Elle est appliquée par la couche services d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="c6422-380">It is enforced by the Enterprise Services layer.</span></span> <span data-ttu-id="c6422-381">Il est marqué pour la réplication de catalogue global.</span><span class="sxs-lookup"><span data-stu-id="c6422-381">It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="c6422-382">Les valeurs valides sont <strong>true</strong> ou <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-383">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-384">msRTCSIP-IsMaster (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="c6422-385">Nouveautés de Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="c6422-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="c6422-386">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-387">msRTCSIP-ligne</span><span class="sxs-lookup"><span data-stu-id="c6422-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="c6422-388">Cet attribut à valeur unique contient l’ID de l’appareil (URI SIP ou URI TEL du téléphone contrôles) utilisé par Lync pour la téléphonie.</span><span class="sxs-lookup"><span data-stu-id="c6422-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="c6422-389">Cet attribut est marqué pour la réplication de catalogue global et est indexé.</span><span class="sxs-lookup"><span data-stu-id="c6422-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="c6422-390">Si un utilisateur est activé pour voix entreprise, cet attribut stocke la version normalisée E. 164 du numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="c6422-391">Nouveautés de Microsoft Office Live Communications Server 2005 avec SP1</span><span class="sxs-lookup"><span data-stu-id="c6422-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-392">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="c6422-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="c6422-393">Cet attribut à valeur unique contient l’URI SIP du serveur de passerelle CSTA-SIP.</span><span class="sxs-lookup"><span data-stu-id="c6422-393">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server.</span></span> <span data-ttu-id="c6422-394">Cet attribut est marqué pour la réplication de catalogue global, mais n’est pas indexé.</span><span class="sxs-lookup"><span data-stu-id="c6422-394">This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="c6422-395">Nouveautés de Microsoft Office Live Communications Server 2005 avec SP1</span><span class="sxs-lookup"><span data-stu-id="c6422-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-396">msRTCSIP-LocalNormalizationData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-397">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="c6422-398">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-399">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-400">msRTCSIP-LocalNormalizationLinks (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-401">Cet attribut à valeurs multiples contient une liste de noms uniques (ND) de normalisation locale associés à ce profil d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="c6422-401">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile.</span></span> <span data-ttu-id="c6422-402">Le type de cet attribut est un fichier binaire DN.</span><span class="sxs-lookup"><span data-stu-id="c6422-402">The type of this attribute is a DN binary.</span></span> <span data-ttu-id="c6422-403">Il existe une relation un-à-plusieurs entre le profil d’emplacement et les règles de normalisation locales.</span><span class="sxs-lookup"><span data-stu-id="c6422-403">There is a one-to-many relationship between location profile and local normalization rules.</span></span> <span data-ttu-id="c6422-404">Le classement de la liste du DNs de normalisation local doit être maintenu dans l’ordre indiqué par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-404">The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator.</span></span> <span data-ttu-id="c6422-405">La conservation de l’ordre est gérée par la partie binaire du fichier binaire du DN, qui spécifie l’index de l’ordre.</span><span class="sxs-lookup"><span data-stu-id="c6422-405">The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="c6422-406">Lien suivant : <strong>ID de lien 11034</strong></span><span class="sxs-lookup"><span data-stu-id="c6422-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="c6422-407">Le lien précédent correspondant à cet attribut de lien suivant est <strong>msRTCSIP-LocationProfileBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-408">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-409">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-410">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="c6422-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="c6422-411">Cet attribut contient une liste des options de la règle de normalisation.</span><span class="sxs-lookup"><span data-stu-id="c6422-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="c6422-412">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-413">msRTCSIP-LocationName (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-414">Cet attribut à valeur unique contient un nom convivial pour le profil d’emplacement indiquant l’emplacement que ce profil représente.</span><span class="sxs-lookup"><span data-stu-id="c6422-414">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents.</span></span> <span data-ttu-id="c6422-415">Dans la mesure où il existe plusieurs profils d’emplacement, l’administrateur a besoin d’une méthode pour distinguer les différents profils.</span><span class="sxs-lookup"><span data-stu-id="c6422-415">Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="c6422-416">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-417">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-418">msRTCSIP-locationProfileBL (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-419">Cet attribut à valeurs multiples contient une liste de noms uniques de profils d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="c6422-419">This multi-valued attribute contains a list of location profile distinguished names.</span></span> <span data-ttu-id="c6422-420">Cet attribut spécifie le lien précédent vers un ou plusieurs profils d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="c6422-420">This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="c6422-421">Lien précédent : <strong>ID de lien 11035</strong></span><span class="sxs-lookup"><span data-stu-id="c6422-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="c6422-422">Cet attribut correspond à la liaison suivante <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-423">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-424">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-425">msRTCSIP-LocationProfileData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-426">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="c6422-427">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-428">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-429">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="c6422-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="c6422-430">Cet attribut contient les options du profil d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="c6422-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="c6422-431">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-432">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="c6422-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="c6422-433">Cet attribut à plusieurs valeurs contient une liste des contacts de l’application.</span><span class="sxs-lookup"><span data-stu-id="c6422-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="c6422-434">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-435">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="c6422-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="c6422-436">Cet attribut à valeurs multiples comporte une liste de profils d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="c6422-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="c6422-437">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-439">Cet attribut représente le nombre maximal de demandes de recherche en suspens par serveur.</span><span class="sxs-lookup"><span data-stu-id="c6422-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="c6422-440">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-442">L’attribut représente le nombre maximal d’abonnements par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="c6422-443">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-445">Cet attribut représente la fenêtre délai d’abonnement maximal.</span><span class="sxs-lookup"><span data-stu-id="c6422-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="c6422-446">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-447">msRTCSIP-MaxRegistrationsTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-448">Cet attribut représente la fenêtre délai maximal d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="c6422-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="c6422-449">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-451">Cet attribut représente la fenêtre délai maximal d’abonnements aux données itinérantes.</span><span class="sxs-lookup"><span data-stu-id="c6422-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="c6422-452">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-453">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="c6422-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="c6422-454">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="c6422-455">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-456">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="c6422-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="c6422-457">Cet attribut est un attribut de point de contrôle de service sous la classe ordinateur qui spécifie un lien vers une fabrique de contrôle multipoint (MCU) auquel il appartient.</span><span class="sxs-lookup"><span data-stu-id="c6422-457">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs.</span></span> <span data-ttu-id="c6422-458">Ce point et cet attribut de contrôle de service est créé pour chaque MCU Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6422-458">This service control point and attribute is created for every Microsoft MCU.</span></span> <span data-ttu-id="c6422-459">Chaque MCU Microsoft doit trouver le serveur principal du pool auquel il appartient, afin de récupérer les paramètres au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="c6422-459">Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="c6422-460">La valeur de cet attribut est le nom unique (DN) de la fabrique MCU.</span><span class="sxs-lookup"><span data-stu-id="c6422-460">The value of this attribute is the distinguished name (DN) of the MCU Factory.</span></span> <span data-ttu-id="c6422-461">Il s’agit d’un attribut à valeur unique qui est marqué pour la réplication de catalogue global.</span><span class="sxs-lookup"><span data-stu-id="c6422-461">This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="c6422-462">Lien suivant : <strong>ID de lien 11026</strong></span><span class="sxs-lookup"><span data-stu-id="c6422-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="c6422-463">Le lien précédent correspondant à cet attribut de lien suivant est <strong>msRTCSIP-MCUServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-464">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-465">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="c6422-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="c6422-466">Il s’agit d’un attribut réservé multichaîne.</span><span class="sxs-lookup"><span data-stu-id="c6422-466">This is a multi-string reserved attribute.</span></span> <span data-ttu-id="c6422-467">Les paramètres stockés dans cet attribut sont représentés par des paires name = value.</span><span class="sxs-lookup"><span data-stu-id="c6422-467">Settings stored in this attribute are represented as name=value pairs.</span></span> <span data-ttu-id="c6422-468">Nom actuellement défini = paires de valeurs :</span><span class="sxs-lookup"><span data-stu-id="c6422-468">Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-469">FactoryURL = &lt;URL&gt;</span><span class="sxs-lookup"><span data-stu-id="c6422-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c6422-470">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-471">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="c6422-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="c6422-472">Il s’agit d’un attribut à valeur unique qui contient le nom unique (DN) d’une fabrique MCU unique associée à un pool.</span><span class="sxs-lookup"><span data-stu-id="c6422-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="c6422-473">Lien suivant : <strong>ID de lien 11024</strong></span><span class="sxs-lookup"><span data-stu-id="c6422-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="c6422-474">Le lien précédent correspondant à cet attribut de lien suivant est <strong>msRTCSIP-PoolAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-475">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-476">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="c6422-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="c6422-477">Cet attribut est une chaîne à valeur unique qui spécifie le GUID du fournisseur de fabrique MCU.</span><span class="sxs-lookup"><span data-stu-id="c6422-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="c6422-478">En fonction de la valeur GUID, le processus de fabrique MCU détermine si ce type MCU doit être desservi.</span><span class="sxs-lookup"><span data-stu-id="c6422-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="c6422-479">Si la valeur GUID est <strong>{F0810510-424F-46ef-84fe-6CC720DF1791}</strong>, le processus de fabrique MCU (disponible par défaut dans Lync Server) la traitera.</span><span class="sxs-lookup"><span data-stu-id="c6422-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="c6422-480">Pour toute autre valeur GUID, le processus de fabrique MCU ne traitera pas le type MCU.</span><span class="sxs-lookup"><span data-stu-id="c6422-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="c6422-481">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-482">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="c6422-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="c6422-483">Cet attribut est une liste à plusieurs valeurs de noms uniques (DN).</span><span class="sxs-lookup"><span data-stu-id="c6422-483">This attribute is a multi-valued list of distinguished names (DN).</span></span> <span data-ttu-id="c6422-484">Cet attribut contient la liste de tous les serveurs MCU du même type et fournisseur associé à cette fabrique MCU.</span><span class="sxs-lookup"><span data-stu-id="c6422-484">This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory.</span></span> <span data-ttu-id="c6422-485">La valeur valide de chaque segment est de 63 caractères. la valeur valide pour le nom de domaine complet est de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="c6422-485">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="c6422-486">Lien précédent : ID de lien 11027</span><span class="sxs-lookup"><span data-stu-id="c6422-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="c6422-487">Le lien transférer correspondant à ce lien précédent est <strong>msRTCSIP-MCUFactoryAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-488">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-489">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="c6422-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="c6422-490">Cet attribut est une chaîne à valeur unique qui spécifie le média que la MCU peut gérer.</span><span class="sxs-lookup"><span data-stu-id="c6422-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="c6422-491">Les types valides pris en charge sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="c6422-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-492">répond</span><span class="sxs-lookup"><span data-stu-id="c6422-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="c6422-493">audio-vidéo</span><span class="sxs-lookup"><span data-stu-id="c6422-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="c6422-494">salons</span><span class="sxs-lookup"><span data-stu-id="c6422-494">chat</span></span></p></li>
<li><p><span data-ttu-id="c6422-495">Téléphone-CONF</span><span class="sxs-lookup"><span data-stu-id="c6422-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c6422-496">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-497">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="c6422-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="c6422-498">Cet attribut est une chaîne à valeur unique qui spécifie le nom d’un fournisseur MCU.</span><span class="sxs-lookup"><span data-stu-id="c6422-498">This attribute is a single-valued string that specifies an MCU vendor’s name.</span></span> <span data-ttu-id="c6422-499">Tous les Microsoft MCU doivent spécifier cet attribut en tant que <strong>Microsoft Corporation</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-499">All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-500">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-501">msRTCSIP-MeetingFlags (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-502">Cet attribut définit différentes options de réunion qui sont activées globalement pour tous les utilisateurs ou objets de contact.</span><span class="sxs-lookup"><span data-stu-id="c6422-502">This attribute defines different meeting options that are enabled globally for all users or contact objects.</span></span> <span data-ttu-id="c6422-503">Cet attribut est une valeur de masque de bits de type entier.</span><span class="sxs-lookup"><span data-stu-id="c6422-503">This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="c6422-504">Les valeurs valides (et positions de bits associées) sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6422-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-505">0 : AllowOrganizeMeetingWithAnonymousParticipants est défini sur aucun (ne pas autoriser les utilisateurs à inviter des utilisateurs anonymes à des réunions) (aucun bit)</span><span class="sxs-lookup"><span data-stu-id="c6422-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="c6422-506">4 : AllowOrganizeMeetingWithAnonymousParticipants est tout le monde (permettre à tous les utilisateurs d’inviter des utilisateurs anonymes à des réunions) (position de bit 2)</span><span class="sxs-lookup"><span data-stu-id="c6422-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="c6422-507">8 : AllowOrganizeMeetingWithAnonymousParticipants est UsePerUserSetting (permet aux utilisateurs d’inviter des utilisateurs anonymes à des réunions en fonction de leur paramètre par utilisateur) (position de bit 3)</span><span class="sxs-lookup"><span data-stu-id="c6422-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="c6422-508">16 : UserPerUserMeetingPolicy (la stratégie de réunion est définie par l’utilisateur) (position binaire 4)</span><span class="sxs-lookup"><span data-stu-id="c6422-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c6422-509">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-510">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-511">msRTCSIP-MeetingPolicy (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-512">Cet attribut spécifie le nom unique (DN) de la stratégie affectée à l’administrateur pour cet utilisateur en tant qu’attribut à valeur unique.</span><span class="sxs-lookup"><span data-stu-id="c6422-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="c6422-513">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-514">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-516">Cet attribut représente la fenêtre délai d’expiration de l’abonnement de présence minimum.</span><span class="sxs-lookup"><span data-stu-id="c6422-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="c6422-517">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-518">msRTCSIP-MinRegistrationTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-519">Cet attribut représente la fenêtre délai d’inscription minimum.</span><span class="sxs-lookup"><span data-stu-id="c6422-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="c6422-520">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-521">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-523">Cet attribut représente la fenêtre délai d’abonnement aux données itinérantes minimum.</span><span class="sxs-lookup"><span data-stu-id="c6422-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="c6422-524">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-525">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-526">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="c6422-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="c6422-527">Cet attribut est utilisé pour stocker le serveur principal SQL Server utilisé par le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="c6422-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="c6422-528">Nouveautés de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6422-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-529">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="c6422-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="c6422-530">Cet attribut contient des options et des indicateurs qui définissent les paramètres de mobilité.</span><span class="sxs-lookup"><span data-stu-id="c6422-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="c6422-531">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-532">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="c6422-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="c6422-533">Cet attribut contient le DN d’un objet de stratégie de mobilité.</span><span class="sxs-lookup"><span data-stu-id="c6422-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="c6422-534">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-535">msRTCSIP-NumDevicesPerUser (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-536">Cet attribut représente le nombre autorisé d’appareils sur lesquels un utilisateur peut s’inscrire pour les communications SIP et s’abonner à la présence.</span><span class="sxs-lookup"><span data-stu-id="c6422-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="c6422-537">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-538">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-539">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="c6422-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="c6422-540">Cet attribut spécifie les options qui sont activées pour l’objet utilisateur ou contact.</span><span class="sxs-lookup"><span data-stu-id="c6422-540">This attribute specifies the options that are enabled for the user or contact object.</span></span> <span data-ttu-id="c6422-541">Cet attribut est une valeur de masquage de type binaire de type entier.</span><span class="sxs-lookup"><span data-stu-id="c6422-541">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="c6422-542">Chaque option est représentée par un bit.</span><span class="sxs-lookup"><span data-stu-id="c6422-542">Each option is represented by a bit.</span></span> <span data-ttu-id="c6422-543">Cet attribut est marqué pour la réplication de catalogue global.</span><span class="sxs-lookup"><span data-stu-id="c6422-543">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="c6422-544">Les valeurs valides (et positions de bits associées) sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6422-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-545">1 : activé pour la connectivité de messagerie instantanée publique (position de bit 0)</span><span class="sxs-lookup"><span data-stu-id="c6422-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="c6422-546">2 : réservé (position binaire 1)</span><span class="sxs-lookup"><span data-stu-id="c6422-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="c6422-547">4 : réservé (position binaire 2)</span><span class="sxs-lookup"><span data-stu-id="c6422-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="c6422-548">8 : réservé (position binaire 3)</span><span class="sxs-lookup"><span data-stu-id="c6422-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="c6422-549">16 : le contrôle d’appel distant a été activé [téléphonie] (position bit 4)</span><span class="sxs-lookup"><span data-stu-id="c6422-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="c6422-550">64 : AllowOrganizeMeetingWithAnonymousParticipants (permettre aux utilisateurs d’inviter des utilisateurs anonymes à des réunions (position de bit 6)</span><span class="sxs-lookup"><span data-stu-id="c6422-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="c6422-551">128 : UCEnabled (permettre aux utilisateurs pour les communications unifiées) (position bit 7)</span><span class="sxs-lookup"><span data-stu-id="c6422-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="c6422-552">256 : EnabledForEnhancedPresence (activer l’utilisateur pour la connectivité de messagerie instantanée publique) (position de bit 8)</span><span class="sxs-lookup"><span data-stu-id="c6422-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="c6422-553">512 : RemoteCallControlDualMode (position binaire 9)</span><span class="sxs-lookup"><span data-stu-id="c6422-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c6422-554">Nouveautés de Live Communications Server 2005 avec SP1.</span><span class="sxs-lookup"><span data-stu-id="c6422-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="c6422-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="c6422-556">Cet attribut est utilisé dans les topologies de ressources et de forêts centrales pour activer l’authentification unique lorsque l’objet ObjectSID d’un utilisateur à partir du compte principal du serveur Windows NT est copié dans cet attribut de l’objet utilisateur ou contact correspondant dans la ressource ou la forêt centrale.</span><span class="sxs-lookup"><span data-stu-id="c6422-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="c6422-557">Office Communicator Web Access recherche un utilisateur dans AD DS en utilisant cet attribut ou l’ObjectSID de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="c6422-558">Cet attribut est marqué pour la réplication de catalogue global.</span><span class="sxs-lookup"><span data-stu-id="c6422-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-559">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="c6422-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="c6422-560">Cet attribut est le nom de ressource uniforme (URN) du propriétaire d’un contact d’application.</span><span class="sxs-lookup"><span data-stu-id="c6422-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="c6422-561">Nouveautés de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-562">msRTCSIP-pattern (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-563">Cet attribut de chaîne à une seule valeur contient un modèle utilisé pour faire correspondre les numéros de téléphone au format E. 164.</span><span class="sxs-lookup"><span data-stu-id="c6422-563">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format.</span></span> <span data-ttu-id="c6422-564">Si le numéro de téléphone correspond à ce modèle, la traduction est appliquée au numéro composé.</span><span class="sxs-lookup"><span data-stu-id="c6422-564">If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="c6422-565">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-566">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-567">msRTCSIP-PhoneRouteBL (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-568">Cet attribut à valeurs multiples contient une liste de noms uniques d’itinéraires téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="c6422-568">This multi-valued attribute contains a list of phone route distinguished names (DN).</span></span> <span data-ttu-id="c6422-569">Cet attribut spécifie le lien précédent vers un ou plusieurs itinéraires téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="c6422-569">This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="c6422-570">Lien précédent : <strong>ID de lien 11033</strong></span><span class="sxs-lookup"><span data-stu-id="c6422-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="c6422-571">Cet attribut correspond à la liaison suivante <strong>msRTCSIP-RouteUsageLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-572">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-573">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-574">msRTCSIP-PhoneRouteData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-575">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="c6422-576">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-577">msRTCSIP-PhoneRouteName (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-578">Cet attribut de chaîne UNICODE à valeur unique spécifie le nom convivial de l’itinéraire téléphonique, de sorte qu’il puisse facilement être référencé par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="c6422-579">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-580">msRTCSIP-PhoneUsageData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-581">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="c6422-582">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-583">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-584">msRTCSIP-PolicyContent (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-585">Cet attribut est une chaîne Unicode à valeur unique.</span><span class="sxs-lookup"><span data-stu-id="c6422-585">This attribute is a single-valued Unicode string.</span></span> <span data-ttu-id="c6422-586">Cet attribut de chaîne contient la définition de la stratégie au format XML.</span><span class="sxs-lookup"><span data-stu-id="c6422-586">This string attribute contains the policy definition in XML format.</span></span> <span data-ttu-id="c6422-587">La définition de schéma XML est courante dans les différents types de stratégies, seuls les paramètres sont différents pour chaque type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="c6422-587">The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="c6422-588">La définition de schéma XML (XSD) est définie comme suit :</span><span class="sxs-lookup"><span data-stu-id="c6422-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p><span data-ttu-id="c6422-589">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-590">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-591">msRTCSIP-PolicyData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-592">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="c6422-593">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-594">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-595">msRTCSIP-PolicyType (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-596">Cet attribut de chaîne Unicode à valeur unique contient le type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="c6422-596">This single-valued Unicode string attribute contains the policy type.</span></span> <span data-ttu-id="c6422-597">Les types de stratégie valides sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="c6422-597">Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-598">répond</span><span class="sxs-lookup"><span data-stu-id="c6422-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="c6422-599">téléphonie</span><span class="sxs-lookup"><span data-stu-id="c6422-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c6422-600">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-601">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-602">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="c6422-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="c6422-603">Cet attribut spécifie un lien vers le pool auquel appartient un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="c6422-604">Cet attribut est défini, que l’ordinateur exécute l’édition standard ou l’édition Enterprise de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6422-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="c6422-605">Cet attribut est marqué pour la réplication de catalogue global.</span><span class="sxs-lookup"><span data-stu-id="c6422-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="c6422-606">La valeur valide est le nom de domaine du pool.</span><span class="sxs-lookup"><span data-stu-id="c6422-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="c6422-607">Lien suivant : <strong>ID de lien 11022</strong></span><span class="sxs-lookup"><span data-stu-id="c6422-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="c6422-608">Le lien précédent correspondant à cet attribut de lien suivant est <strong>msRTCSIP-FrontEndServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-609">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-610">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="c6422-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="c6422-611">Il s’agit d’un attribut à valeurs multiples qui contient une liste de noms uniques (DN) de pools avec lesquels la fabrique MCU est associée.</span><span class="sxs-lookup"><span data-stu-id="c6422-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="c6422-612">Lien précédent : <strong>ID de lien 11025</strong></span><span class="sxs-lookup"><span data-stu-id="c6422-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="c6422-613">Le lien transférer correspondant à ce lien précédent est <strong>msRTCSIP-MCUFactoryPath</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-614">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-615">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="c6422-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="c6422-616">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="c6422-617">Nouveautés de Live Communications Server 2005 avec SP1.</span><span class="sxs-lookup"><span data-stu-id="c6422-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-618">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="c6422-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="c6422-619">Cet attribut spécifie un nom arbitraire pour un pool affiché par la console de gestion.</span><span class="sxs-lookup"><span data-stu-id="c6422-619">This attribute specifies an arbitrary name for a pool that is displayed by the management console.</span></span> <span data-ttu-id="c6422-620">Ce nom peut être modifié par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-620">This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="c6422-621">La valeur valide est une chaîne qui représente le nom d’un pool.</span><span class="sxs-lookup"><span data-stu-id="c6422-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="c6422-622">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-623">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="c6422-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="c6422-624">Cet attribut est une valeur de chaîne à valeur unique.</span><span class="sxs-lookup"><span data-stu-id="c6422-624">This attribute is a single-valued string value.</span></span> <span data-ttu-id="c6422-625">La valeur de cet attribut, le cas échéant, représente le nom de domaine complet (FQDN) du pool si l’administrateur souhaite créer un pool frontal avec un nom de domaine complet qui n’est pas conforme à la structure de domaine Active Directory (par exemple, un SIP). espace de noms disjoint de l’espace de noms DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="c6422-625">The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="c6422-626">Nous vous recommandons de mapper le nom de domaine complet (FQDN) du pool frontal à la partie nom de domaine en tant que domaine Active Directory dans lequel réside le pool.</span><span class="sxs-lookup"><span data-stu-id="c6422-626">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides.</span></span> <span data-ttu-id="c6422-627">Par conséquent, quand aucune valeur n’est présente dans cet attribut, le nom de domaine complet du pool frontal est défini par défaut sur la structure de nom de domaine Active Directory, tel qu’il est indiqué par l’attribut <strong>dNSHostName</strong> .</span><span class="sxs-lookup"><span data-stu-id="c6422-627">Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="c6422-628">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-629">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="c6422-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="c6422-630">Liste à plusieurs valeurs des noms de domaine de tous les serveurs Lync Server Enterprise Edition associés à un pool.</span><span class="sxs-lookup"><span data-stu-id="c6422-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="c6422-631">Cet attribut de type entier détermine si le pool est compatible avec la messagerie instantanée (mi) et la présence et les réunions.</span><span class="sxs-lookup"><span data-stu-id="c6422-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="c6422-632">Les types de valeurs valides possibles sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="c6422-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-633">Non défini : service de messagerie instantanée et de présence (Live Communications Server 2005 et 2003)</span><span class="sxs-lookup"><span data-stu-id="c6422-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="c6422-634">1 : service de messagerie instantanée et de présence (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="c6422-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="c6422-635">2 : messagerie instantanée, présence et service de réunion (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="c6422-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c6422-636">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-637">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="c6422-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="c6422-638">Cet attribut spécifie si un pool de serveurs exécute Standard Edition Server ou Server Enterprise Edition Server.</span><span class="sxs-lookup"><span data-stu-id="c6422-638">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server.</span></span> <span data-ttu-id="c6422-639">Cet attribut est une valeur de masquage de type binaire de type entier.</span><span class="sxs-lookup"><span data-stu-id="c6422-639">This attribute is a bit-mask value of type integer.</span></span> <span data-ttu-id="c6422-640">Chaque option est représentée par un bit.</span><span class="sxs-lookup"><span data-stu-id="c6422-640">Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="c6422-641">Les valeurs valides (et positions de bits associées) sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6422-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-642">1 : Standard Edition Server, hébergement des utilisateurs (position de bit 0)</span><span class="sxs-lookup"><span data-stu-id="c6422-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="c6422-643">2 : serveur Enterprise Edition, hébergement des utilisateurs (position binaire 1)</span><span class="sxs-lookup"><span data-stu-id="c6422-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="c6422-644">4 : Standard Edition Server et applications hébergées (position binaire 2)</span><span class="sxs-lookup"><span data-stu-id="c6422-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="c6422-645">8 : serveur Enterprise Edition, applications d’hébergement (position de bit 3)</span><span class="sxs-lookup"><span data-stu-id="c6422-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="c6422-646">Dans la mesure où Lync Server ne prend pas en charge les pools hébergeant uniquement des applications, les seules valeurs valides sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6422-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-647">5 : Standard Edition Server, hébergement des utilisateurs et des applications (positions de bit 0 et 2)</span><span class="sxs-lookup"><span data-stu-id="c6422-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="c6422-648">10 : serveur Enterprise Edition, héberge les utilisateurs et les applications (emplacements des points 1 et 3)</span><span class="sxs-lookup"><span data-stu-id="c6422-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c6422-649">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-650">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="c6422-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="c6422-651">Cet attribut définit la version du pool.</span><span class="sxs-lookup"><span data-stu-id="c6422-651">This attribute defines the pool version.</span></span> <span data-ttu-id="c6422-652">Il s’agit d’un type entier qui est incrémenté avec chaque version de produit majeure.</span><span class="sxs-lookup"><span data-stu-id="c6422-652">It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="c6422-653">Les types de valeurs valides possibles sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="c6422-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-654">0 : Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="c6422-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="c6422-655">1 : Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="c6422-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="c6422-656">2 : Live Communications Server 2005 avec SP1</span><span class="sxs-lookup"><span data-stu-id="c6422-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="c6422-657">3 : Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="c6422-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="c6422-658">4 : Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c6422-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="c6422-659">5 : Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c6422-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c6422-660">Live Communications Server 2005 avec SP1.</span><span class="sxs-lookup"><span data-stu-id="c6422-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-661">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="c6422-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="c6422-662">Cet attribut contient des options et des indicateurs permettant de définir les paramètres de présence.</span><span class="sxs-lookup"><span data-stu-id="c6422-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="c6422-663">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-664">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="c6422-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="c6422-665">Cet attribut contient le DN d’un objet de stratégie de présence.</span><span class="sxs-lookup"><span data-stu-id="c6422-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="c6422-666">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-667">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="c6422-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="c6422-668">Cet attribut autorise un utilisateur ou un contact à la messagerie SIP.</span><span class="sxs-lookup"><span data-stu-id="c6422-668">This attribute enables a user or contact for SIP messaging.</span></span> <span data-ttu-id="c6422-669">Il est ajouté à la classe contact, car dans la topologie centrale de la forêt, les objets de contact, pas les objets utilisateur, sont activés par SIP.</span><span class="sxs-lookup"><span data-stu-id="c6422-669">It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="c6422-670">La valeur valide est le nom de domaine principal du serveur Standard Edition Server ou du pool frontal d’Enterprise Edition dans lequel un utilisateur est hébergé.</span><span class="sxs-lookup"><span data-stu-id="c6422-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="c6422-671">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="c6422-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="c6422-673">Cet attribut contient l’adresse SIP d’un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="c6422-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-674">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="c6422-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="c6422-675">Cet attribut contient l’ID d’appareil de l’appareil de lignes privées.</span><span class="sxs-lookup"><span data-stu-id="c6422-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="c6422-676">Nouveautés de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-677">msRTCSIP-routable</span><span class="sxs-lookup"><span data-stu-id="c6422-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="c6422-678">Cet attribut est un attribut booléen utilisé pour déterminer si Lync Server est autorisé à router vers ce service en utilisant son adresse GRUU.</span><span class="sxs-lookup"><span data-stu-id="c6422-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="c6422-679">Si cette valeur est définie sur <strong>true</strong>, Lync Server est autorisé à effectuer le routage vers ce service.</span><span class="sxs-lookup"><span data-stu-id="c6422-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="c6422-680">Si cette valeur est définie sur <strong>false</strong>, le serveur Lync n’est pas autorisé à router vers ce service.</span><span class="sxs-lookup"><span data-stu-id="c6422-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="c6422-681">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-682">msRTCSIP-RouteUsageAttribute (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-683">Cet attribut de chaîne UNICODE à valeur unique définit un attribut qui qualifie l’utilisation pour un itinéraire téléphonique.</span><span class="sxs-lookup"><span data-stu-id="c6422-683">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route.</span></span> <span data-ttu-id="c6422-684">La sélection d’un itinéraire de téléphone est déterminée en fonction de deux éléments : l’attribut utilisation attribué à l’itinéraire du téléphone et les attributs d’utilisation de stratégie autorisés de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="c6422-684">Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes.</span></span> <span data-ttu-id="c6422-685">Le premier itinéraire téléphonique avec un attribut utilisation qui correspond à l’utilisation autorisée de l’appelant est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c6422-685">The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="c6422-686">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-687">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-688">msRTCSIP-RouteUsageLinks (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-689">Cet attribut de nom unique (DN) à valeurs multiples contient une liste des noms uniques de l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="c6422-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="c6422-690">Lien suivant : <strong>ID de lien 11032</strong></span><span class="sxs-lookup"><span data-stu-id="c6422-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="c6422-691">Cet attribut est un lien de transfert vers la liaison de renvoi correspondante de <strong>msRTCSIP-PhoneRouteBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-692">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-693">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="c6422-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="c6422-694">Cet attribut contient le DN qui pointe vers le pool sur lequel tout le trafic SIP adressé à ce MCU ou à ce service approuvé doit traverser.</span><span class="sxs-lookup"><span data-stu-id="c6422-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="c6422-695">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-696">msRTCSIP-RuleName (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-697">Cet attribut de chaîne UNICODE à valeur unique spécifie le nom convivial de la règle de normalisation, afin qu’il puisse facilement être référencé par un administrateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="c6422-698">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-699">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-700">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="c6422-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="c6422-701">Cet attribut représente la version de schéma actuellement déployée au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="c6422-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-702">msRTCSIP-SearchMaxRequests (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-703">Cet attribut limite le nombre de résultats de recherche à retourner à partir d’une recherche dans l’annuaire lorsqu’un utilisateur recherche un contact à l’aide de Communicator.</span><span class="sxs-lookup"><span data-stu-id="c6422-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="c6422-704">Cet attribut remplace la valeur fournie par le client.</span><span class="sxs-lookup"><span data-stu-id="c6422-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="c6422-705">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-706">msRTCSIP-SearchMaxResults (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-707">Cet attribut limite le nombre de demandes de recherche renvoyées.</span><span class="sxs-lookup"><span data-stu-id="c6422-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="c6422-708">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-709">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="c6422-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="c6422-710">Cet attribut à valeurs multiples est un lien précédent contenant une liste de noms uniques (DN).</span><span class="sxs-lookup"><span data-stu-id="c6422-710">This multi-valued attribute is a back link that contains a list of distinguished names (DN).</span></span> <span data-ttu-id="c6422-711">Ces DN pointent vers un objet pool ou <strong>TrustedService</strong> .</span><span class="sxs-lookup"><span data-stu-id="c6422-711">These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="c6422-712">Cet attribut correspond à la liaison suivante <strong>msRTCSIP-TrustedServiceLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-713">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-714">msRTCSIP-ServerData</span><span class="sxs-lookup"><span data-stu-id="c6422-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="c6422-715">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-716">msRTCSIP-ServerReferenceBL (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-717">Cet attribut à valeurs multiples contient une liste de noms uniques.</span><span class="sxs-lookup"><span data-stu-id="c6422-717">This multi-valued attribute contains a list of distinguished names.</span></span> <span data-ttu-id="c6422-718">Ces noms uniques sont des liens de retour qui font référence à d’autres objets serveur qui peuvent être affectés à un profil d’emplacement par défaut.</span><span class="sxs-lookup"><span data-stu-id="c6422-718">These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="c6422-719">Lien précédent : <strong>ID de lien 11037</strong></span><span class="sxs-lookup"><span data-stu-id="c6422-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="c6422-720">Le lien transférer correspondant à ce lien précédent est <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="c6422-721">Cet attribut de lien précédent fait référence uniquement aux pools et aux serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="c6422-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="c6422-722">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-723">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-724">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="c6422-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="c6422-725">Cet attribut définit les informations de version du serveur.</span><span class="sxs-lookup"><span data-stu-id="c6422-725">This attribute defines the version information of the server.</span></span> <span data-ttu-id="c6422-726">Ce numéro de version s’applique à tous les rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="c6422-726">This version number applies to all server roles.</span></span> <span data-ttu-id="c6422-727">Il s’agit d’un entier monotonously croissant qui s’incrémente avec chaque publication officielle du produit.</span><span class="sxs-lookup"><span data-stu-id="c6422-727">It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="c6422-728">Les valeurs valides possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6422-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-729">Non défini : Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="c6422-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="c6422-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="c6422-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="c6422-731">                 Live Communications Server 2005 avec SP1</span><span class="sxs-lookup"><span data-stu-id="c6422-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="c6422-732">3 : Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="c6422-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="c6422-733">4 : Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c6422-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="c6422-734">5 : Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c6422-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="c6422-735">6 : Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6422-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c6422-736">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-737">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="c6422-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="c6422-738">Cet attribut à une seule valeur de type entier spécifie le type d’objet sur lequel pointe <strong>MSDS-SourceObjectDN</strong> , comme suit :</span><span class="sxs-lookup"><span data-stu-id="c6422-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-739">null | 0x00000001 : représente un objet utilisateur principal du serveur Windows NT d’une autre forêt</span><span class="sxs-lookup"><span data-stu-id="c6422-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="c6422-740">Les attributs suivants représentent un type de groupe à partir d’une autre forêt pour l’extension du groupe de distribution :</span><span class="sxs-lookup"><span data-stu-id="c6422-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-741">0x00000002 : ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="c6422-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="c6422-742">0x00000004 : ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="c6422-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="c6422-743">0x00000004 : ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="c6422-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="c6422-744">0x00000008 : ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="c6422-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="c6422-745">0x80000000 : ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="c6422-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="c6422-746">0x90000000 : représente un objet de standard automatique ou d’accès d’abonné de la même forêt ou d’une autre forêt.</span><span class="sxs-lookup"><span data-stu-id="c6422-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="c6422-747">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-748">msRTCSIP-SubscriptionAuthRequired (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="c6422-749">Nouveautés de Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="c6422-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="c6422-750">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-751">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="c6422-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="c6422-752">Cet attribut vous permet de déplacer un utilisateur ou un objet contact d’un pool de serveurs Lync vers un autre.</span><span class="sxs-lookup"><span data-stu-id="c6422-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="c6422-753">Cet attribut est ajouté à la classe contact en raison de l’activation de l’option SIP dans la topologie centrale de la forêt.</span><span class="sxs-lookup"><span data-stu-id="c6422-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="c6422-754">La valeur valide est le nom d’utilisateur de l’emplacement du serveur Standard Edition Server ou du pool frontal vers lequel un utilisateur doit être déplacé.</span><span class="sxs-lookup"><span data-stu-id="c6422-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="c6422-755">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-756">msRTCSIP-TargetPhoneNumber (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-757">Cet attribut de chaîne à une seule valeur contient un modèle de numéro de téléphone ou une plage pour diriger vers les passerelles spécifiées définies dans <strong>msRTCSIP-passerelles</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-758">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-759">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="c6422-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="c6422-760">Cet attribut stocke les paires nom-valeur pour les stratégies cibles pour les utilisateurs de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6422-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="c6422-761">Nouveautés de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-762">msRTCSIP-IDClient</span><span class="sxs-lookup"><span data-stu-id="c6422-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="c6422-763">Cet attribut stocke l’identificateur unique d’un client.</span><span class="sxs-lookup"><span data-stu-id="c6422-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="c6422-764">Nouveautés de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-765">msRTCSIP-traduction (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-766">Cet attribut est utilisé par la fonctionnalité voix de Lync Server et contient la chaîne de traduction à appliquer sur le numéro composé, si une correspondance est trouvée.</span><span class="sxs-lookup"><span data-stu-id="c6422-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="c6422-767">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="c6422-768">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-769">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="c6422-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="c6422-770">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="c6422-771">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-772">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="c6422-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="c6422-773">Cet attribut est une valeur de chaîne qui contient le nom de domaine complet de la MCU.</span><span class="sxs-lookup"><span data-stu-id="c6422-773">This attribute is a string value that contains the FQDN of the MCU.</span></span> <span data-ttu-id="c6422-774">Il s’agit d’un attribut à valeur unique.</span><span class="sxs-lookup"><span data-stu-id="c6422-774">This is a single-valued attribute.</span></span> <span data-ttu-id="c6422-775">La valeur valide de chaque segment est de 63 caractères. la valeur valide pour le nom de domaine complet est de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="c6422-775">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="c6422-776">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-777">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="c6422-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="c6422-778">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="c6422-779">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-780">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="c6422-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="c6422-781">Cet attribut est une valeur de chaîne contenant le nom de domaine complet du serveur proxy exécutant.</span><span class="sxs-lookup"><span data-stu-id="c6422-781">This attribute is a string value that contains the FQDN of the server running Proxy Server.</span></span> <span data-ttu-id="c6422-782">Cet attribut a une valeur unique.</span><span class="sxs-lookup"><span data-stu-id="c6422-782">This attribute is single-valued.</span></span> <span data-ttu-id="c6422-783">La valeur valide de chaque segment est de 63 caractères. la valeur valide pour le nom de domaine complet est de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="c6422-783">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="c6422-784">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-785">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="c6422-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="c6422-786">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-787">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="c6422-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="c6422-788">Cet attribut est un attribut à valeur unique qui représente le nom de domaine complet d’un serveur approuvé.</span><span class="sxs-lookup"><span data-stu-id="c6422-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="c6422-789">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-790">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="c6422-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="c6422-791">Cet attribut spécifie le numéro de version d’un serveur dans la liste des serveurs approuvés.</span><span class="sxs-lookup"><span data-stu-id="c6422-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="c6422-792">Les valeurs valides possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6422-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-793">NULL : Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="c6422-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="c6422-794">2 : Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="c6422-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="c6422-795">3 : Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="c6422-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="c6422-796">4 : Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c6422-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="c6422-797">5 : Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c6422-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="c6422-798">6 : Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6422-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c6422-799">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-800">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="c6422-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="c6422-801">Cet attribut définit les options qui sont activées pour le service approuvé.</span><span class="sxs-lookup"><span data-stu-id="c6422-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="c6422-802">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-803">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="c6422-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="c6422-804">Cet attribut à valeurs multiples contient une liste de noms uniques (ND) qui font référence à un objet de service approuvé, tel qu’un service d’authentification par relais de média.</span><span class="sxs-lookup"><span data-stu-id="c6422-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="c6422-805">Un service d’authentification de relais de média (physiquement localisé sur le serveur Edge exécutant le service de conférence A/V) doit être associé à un pool pour prendre en charge les scénarios audio des utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="c6422-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="c6422-806">Le lien précédent correspondant à cet attribut de lien suivant est <strong>msRTCSIP-ServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-807">CITÉ</span><span class="sxs-lookup"><span data-stu-id="c6422-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-808">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="c6422-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="c6422-809">Cet attribut est un entier qui définit le numéro de port utilisé pour la connexion à ce service GRUU.</span><span class="sxs-lookup"><span data-stu-id="c6422-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="c6422-810">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-811">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="c6422-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="c6422-812">Cet attribut est une valeur de chaîne qui définit le type de service GRUU qu’il représente.</span><span class="sxs-lookup"><span data-stu-id="c6422-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="c6422-813">Les types de services GRUU valides sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="c6422-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-814">Le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="c6422-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="c6422-815">Passerelle</span><span class="sxs-lookup"><span data-stu-id="c6422-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="c6422-816">Service d’authentification de relais de média (MRAS)</span><span class="sxs-lookup"><span data-stu-id="c6422-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="c6422-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="c6422-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="c6422-818">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="c6422-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c6422-819">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-820">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="c6422-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="c6422-821">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="c6422-822">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-823">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="c6422-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="c6422-824">Cet attribut est une valeur de chaîne qui contient le nom de domaine complet (FQDN) du serveur IIS exécutant les services Web de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6422-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="c6422-825">Il s’agit d’un attribut à valeur unique.</span><span class="sxs-lookup"><span data-stu-id="c6422-825">This is a single-valued attribute.</span></span> <span data-ttu-id="c6422-826">La valeur valide de chaque segment est de 63 caractères. la valeur valide pour le nom de domaine complet est de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="c6422-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="c6422-827">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-828">msRTCSIP-UCFlags (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-829">Cet attribut définit différentes options de communications unifiées qui sont activées globalement pour tous les objets utilisateur ou contact.</span><span class="sxs-lookup"><span data-stu-id="c6422-829">This attribute defines different UC options that are enabled globally to all user or contact objects.</span></span> <span data-ttu-id="c6422-830">Cet attribut est une valeur de masque de bits de type entier.</span><span class="sxs-lookup"><span data-stu-id="c6422-830">This attribute is a bit-mask value of integer type.</span></span> <span data-ttu-id="c6422-831">Chaque option est représentée par la présence d’un bit.</span><span class="sxs-lookup"><span data-stu-id="c6422-831">Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="c6422-832">La valeur valide possible (et la position de bit associée) sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6422-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-833">4 : UsePerUserUCPolicy (position binaire 2)</span><span class="sxs-lookup"><span data-stu-id="c6422-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="c6422-834">Lorsque ce bit est défini, la stratégie de Cu est définie par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="c6422-835">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-836">msRTCSIP-UCPolicy (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-837">Cet attribut à valeur unique contient le nom unique (DN) de la stratégie de Cu attribuée par l’administrateur pour cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="c6422-838">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-839">msRTCSIP-UserDomainList (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="c6422-840">Cet attribut fournit une liste de tous les domaines d’une forêt qui hébergent des utilisateurs compatibles SIP.</span><span class="sxs-lookup"><span data-stu-id="c6422-840">This attribute provides a list of all the domains in a forest that host SIP-enabled users.</span></span> <span data-ttu-id="c6422-841">La valeur par défaut est une liste vide, ce qui signifie que tous les domaines de la forêt sont compatibles SIP.</span><span class="sxs-lookup"><span data-stu-id="c6422-841">The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="c6422-842">Les valeurs valides sont des chaînes multiples qui représentent le nom de domaine de chaque domaine.</span><span class="sxs-lookup"><span data-stu-id="c6422-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="c6422-843">Nouveautés de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="c6422-844">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-845">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="c6422-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="c6422-846">Cet attribut détermine si l’utilisateur est actuellement activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6422-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-847">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="c6422-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="c6422-848">Cet attribut à valeurs multiples contient une liste de paires nom-valeur au format de &quot;nom = valeur. &quot; Cet attribut est marqué pour la réplication de catalogue global.</span><span class="sxs-lookup"><span data-stu-id="c6422-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="c6422-849">Nouveautés de Live Communications Server 2005 avec SP1.</span><span class="sxs-lookup"><span data-stu-id="c6422-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-850">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="c6422-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="c6422-851">Cet attribut contient le nom unique (DN) qui pointe vers un objet de profil d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="c6422-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="c6422-852">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c6422-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-853">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="c6422-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="c6422-854">Cet attribut stocke les paires nom-valeur pour les stratégies utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="c6422-855">Nouveautés de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c6422-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-856">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="c6422-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="c6422-857">Il s’agit d’un attribut à valeurs multiples contenant une liste de noms uniques avec des valeurs binaires (DN_WITH_BINARY) pointant vers des stratégies utilisateur globales de différents types.</span><span class="sxs-lookup"><span data-stu-id="c6422-857">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types.</span></span> <span data-ttu-id="c6422-858">La partie binaire indique le type de stratégie auquel la partie du DN pointe.</span><span class="sxs-lookup"><span data-stu-id="c6422-858">The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="c6422-859">Les valeurs binaires valides sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6422-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-860">0x00000001 : stratégie de réunion</span><span class="sxs-lookup"><span data-stu-id="c6422-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="c6422-861">0x00000002 : stratégie d’UC</span><span class="sxs-lookup"><span data-stu-id="c6422-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="c6422-862">0x00000005 : politique de présence</span><span class="sxs-lookup"><span data-stu-id="c6422-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c6422-863">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-864">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="c6422-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="c6422-865">Il s’agit de l’ID du groupe de routage SIP.</span><span class="sxs-lookup"><span data-stu-id="c6422-865">This is the SIP routing group ID.</span></span> <span data-ttu-id="c6422-866">Les utilisateurs du même groupe seront enregistrés sur le même serveur principal.</span><span class="sxs-lookup"><span data-stu-id="c6422-866">Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="c6422-867">Nouveautés de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6422-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-868">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="c6422-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="c6422-869">Il s’agit d’un attribut à valeurs multiples.</span><span class="sxs-lookup"><span data-stu-id="c6422-869">This is a multi-valued attribute.</span></span> <span data-ttu-id="c6422-870">Cet attribut est réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6422-870">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="c6422-871">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-872">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="c6422-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="c6422-873">Cet attribut à valeur unique pointe vers le pool ou le serveur Standard Edition auquel appartiennent les composants Web.</span><span class="sxs-lookup"><span data-stu-id="c6422-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="c6422-874">Lien suivant : <strong>ID de lien 11028</strong></span><span class="sxs-lookup"><span data-stu-id="c6422-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="c6422-875">Le lien précédent correspondant à cet attribut de lien suivant est <strong>msRTCSIP-WebComponentsServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-876">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-877">msRTCSIP-WebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="c6422-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="c6422-878">Cet attribut est une liste à plusieurs valeurs de noms uniques.</span><span class="sxs-lookup"><span data-stu-id="c6422-878">This attribute is a multi-valued list of distinguished names.</span></span> <span data-ttu-id="c6422-879">Cet attribut contient la liste de tous les serveurs Web associés à ce pool.</span><span class="sxs-lookup"><span data-stu-id="c6422-879">This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="c6422-880">Lien précédent : <strong>ID de lien 11029</strong></span><span class="sxs-lookup"><span data-stu-id="c6422-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="c6422-881">Le lien transférer correspondant à ce lien précédent est <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6422-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c6422-882">Nouveautés d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c6422-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-883">msRTCSIP-WMIInstanceId (obsolète)</span><span class="sxs-lookup"><span data-stu-id="c6422-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="c6422-884">Nouveautés de Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="c6422-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="c6422-885">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="c6422-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-886">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="c6422-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="c6422-887">Cet attribut Active Directory existant est utilisé par la téléphonie pour spécifier la liste d’adresses IP supplémentaires pour un téléphone.</span><span class="sxs-lookup"><span data-stu-id="c6422-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="c6422-888">Nouveauté du système d’exploitation Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="c6422-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-889">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="c6422-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="c6422-890">Cet attribut Active Directory existant est utilisé par les composants vocaux de Lync Server, uniquement pour les objets contact, dans le but de router les appels vers les numéros d’accès d’abonné et de standard de messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="c6422-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="c6422-891">L’adresse de transfert d’appel sans condition est stockée dans cet attribut à valeurs multiples.</span><span class="sxs-lookup"><span data-stu-id="c6422-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="c6422-892">Ce compte est créé pour l’objet spécifique du standard automatique et de l’accès abonné.</span><span class="sxs-lookup"><span data-stu-id="c6422-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="c6422-893">Les attributs de ce compte ne doivent pas être modifiés par les administrateurs.</span><span class="sxs-lookup"><span data-stu-id="c6422-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="c6422-894">Nouveauté du système d’exploitation Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="c6422-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6422-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="c6422-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="c6422-896">Cet attribut multivaleur Active Directory existant fait partie du schéma Active Directory de base introduit dans Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="c6422-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="c6422-897">Cet attribut contient les différentes adresses x400, X500 et SMTP de l’adresse de messagerie de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="c6422-898">Dans Live Communications Server 2003 et versions ultérieures, l’URI SIP de l’utilisateur est ajouté à cette liste &quot;à l'&quot; aide de la balise SIP :.</span><span class="sxs-lookup"><span data-stu-id="c6422-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="c6422-899">Les applications suivantes recherchent l’URI SIP de l’utilisateur à partir de cet attribut :</span><span class="sxs-lookup"><span data-stu-id="c6422-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6422-900">Client de messagerie et de collaboration de Microsoft Office Outlook 2003</span><span class="sxs-lookup"><span data-stu-id="c6422-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="c6422-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="c6422-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c6422-902">Nouveauté du système d’exploitation Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="c6422-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6422-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="c6422-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="c6422-904">Cet attribut Active Directory existant contient le numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6422-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="c6422-905">Nouveauté du système d’exploitation Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="c6422-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

