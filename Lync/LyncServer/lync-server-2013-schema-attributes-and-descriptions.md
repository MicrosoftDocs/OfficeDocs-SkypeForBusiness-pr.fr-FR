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
ms.openlocfilehash: c95fa0450a85aea4ffdd53dfcb61ddb5b97ed532
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="3e9d3-102">Attributs et descriptions de schéma dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e9d3-102">Schema attributes and descriptions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e9d3-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="3e9d3-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="3e9d3-104">Cette section décrit tous les attributs de schéma utilisés par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-104">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="3e9d3-105">Pour les classes associées aux attributs, consultez la rubrique [attributs de schéma par classe dans Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="3e9d3-105">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="3e9d3-106">Pour obtenir la liste des classes et des attributs qui sont nouveaux dans Lync Server 2013, consultez la rubrique [modifications de schéma dans Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="3e9d3-106">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="3e9d3-p102">Les attributs appartenant à des paires liées sont spécifiés en tant que liens avant ou liens arrière. Un attribut qui fait référence à un autre objet est un lien avant, tandis que l’attribut de l’objet cible qui fait référence au premier objet est un lien arrière. Les liens avant peuvent être mis à jour, contrairement aux liens arrière qui sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p102">Attributes that are linked pairs are specified as forward links or back links. An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link. Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="3e9d3-p103">Certains attributs ont une valeur masque de bits. Pour ces attributs, chaque paramètre est représenté par un bit et la valeur décimale affichée représente la position du bit. Les positions des bits commencent par le bit 0. 1 (binaire) correspond au bit 0 défini et 10000 (binaire) au bit 4 défini. Chaque bit représente une propriété. Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p103">Some attributes have a bit-mask value. For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position. Bit positions start with bit 0. For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set. Each bit represents a property. The following are some examples:</span></span>

  - <span data-ttu-id="3e9d3-116">10000 (binaire) a une valeur décimale de 16 (le bit 4 est défini).</span><span class="sxs-lookup"><span data-stu-id="3e9d3-116">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="3e9d3-117">100000000 (binaire) a une valeur décimale de 256 (le bit 8 est défini).</span><span class="sxs-lookup"><span data-stu-id="3e9d3-117">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="3e9d3-118">1100 (binaire) a une valeur décimale de 12 (les bits 2 et 3 sont définis ; les propriétés représentées par les deux bits sont activées).</span><span class="sxs-lookup"><span data-stu-id="3e9d3-118">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="3e9d3-119">1111000001 (binaire) a une valeur décimale de 961 (les bits 0, 6, 7, 8 et 9 sont définis ; les propriétés pour chacun de ces bits sont activées).</span><span class="sxs-lookup"><span data-stu-id="3e9d3-119">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="3e9d3-120">Attributs de schéma pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e9d3-120">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e9d3-121">Attribut</span><span class="sxs-lookup"><span data-stu-id="3e9d3-121">Attribute</span></span></th>
<th><span data-ttu-id="3e9d3-122">Description</span><span class="sxs-lookup"><span data-stu-id="3e9d3-122">Description</span></span></th>
<th><span data-ttu-id="3e9d3-123">Commentaires</span><span class="sxs-lookup"><span data-stu-id="3e9d3-123">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-124">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="3e9d3-124">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-125">Attribut existant dans les services de domaine Active Directory qui est désormais associé aux classes <strong>msRTCSIP-pool</strong> et <strong>msRTCSIP-MonitoringServer</strong> .</span><span class="sxs-lookup"><span data-stu-id="3e9d3-125">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="3e9d3-126">Cet attribut spécifie le nom de domaine complet (FQDN) d’un pool ou d’un serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-126">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="3e9d3-127">Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-127">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-128">Nouveauté de Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-128">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-129">msDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="3e9d3-129">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p105">Cet attribut contient la représentation sous forme de chaîne du nom unique (DN) de l’objet, situé dans une autre forêt, qui correspond à cet objet. Cet attribut est utilisé pour le développement des groupes de distribution et le standard automatique. Il est défini dans le schéma Active Directory par défaut de Windows Server 2003 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p105">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object. This attribute is used for distribution group expansion and auto attendance. This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="3e9d3-133">Pour éviter la nécessité d’une mise à niveau des services de domaine Active Directory vers Windows Server 2003 R2, la procédure de préparation du schéma Active Directory étend le schéma Windows Server 2003 à l’aide de cette définition d’attribut.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-133">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-134">Nouveauté de Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-134">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-135">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="3e9d3-135">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-136">Cet attribut qui gère plusieurs valeurs contient les paramètres de messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-136">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="3e9d3-137">Cet attribut est partagé avec la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-137">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-138">Nouveauté de Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-138">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-139">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="3e9d3-139">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-140">Cet attribut à valeurs multiples contient les stratégies d’archive qui s’appliquent à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-140">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="3e9d3-141">Les stratégies d’archive conservent les éléments de boîte aux lettres de l’utilisateur pendant la durée de la suspension.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-141">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="3e9d3-142">Cet attribut est partagé avec Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-142">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-143">Nouveauté de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-143">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-144">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="3e9d3-144">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-145">Cet attribut stocke les informations sur les fournisseurs de services d’audioconférence pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-145">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-146">Nouveauté de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-146">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-147">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="3e9d3-147">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-148">Cet attribut pointe sur l’entrée de service approuvé pour le contact d’application.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-148">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-149">Nouveauté de Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-149">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-150">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="3e9d3-150">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-151">Cet attribut contient une liste des applications hébergées sur le serveur d’applications.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-151">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-152">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-152">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-153">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="3e9d3-153">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-154">Cet attribut spécifie les options pour le contact d’application.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-154">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-155">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-155">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-156">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="3e9d3-156">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-157">Cet attribut contient la langue principale pour le contact d’application.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-157">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-158">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-158">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-159">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="3e9d3-159">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-160">Cet attribut gérant plusieurs valeurs contient les langues secondaires pour le contact d’application.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-160">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-161">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-161">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-162">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="3e9d3-162">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p108">Cet attribut contient une liste de serveurs d’applications appartenant à ce pool. Le lien avant correspondant à cet attribut de lien arrière est <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p108">This attribute contains a list of application servers that belong to this pool. The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-165">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-165">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-166">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="3e9d3-166">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-167">Cet attribut pointe vers le pool auquel appartient ce serveur d’applications.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-167">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="3e9d3-168">Il s’agit du lien avant.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-168">This is the forward link.</span></span> <span data-ttu-id="3e9d3-169">Le lien arrière correspondant est <strong>msRTCSIP-ApplicationServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-169">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-170">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-170">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-171">msRTCSIP-ArchiveDefault (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-171">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3e9d3-172">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-172">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3e9d3-173">Obsolète dans Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-173">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-174">msRTCSIP-ArchiveDefaultFlags (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-174">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p110">Cet attribut spécifie la valeur par défaut globale, dans les limites de la forêt, déterminant si les communications de tous les utilisateurs doivent être archivées ou non. Il est appliqué par la couche de l’agent d’archivage. Les valeurs prises en charge pour cet attribut sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p110">This attribute specifies the global default within the forest boundary for archiving all user communications. This is enforced by the archiving agent layer. The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-178"><strong>TRUE</strong> : archiver tous les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="3e9d3-178"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-179"><strong>FALSE</strong> : ne pas archiver tous les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="3e9d3-179"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="3e9d3-180">Cet attribut permet de vérifier globalement, dans les limites de la forêt, le mode d’archivage des communications des utilisateurs d’un réseau interne.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-180">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="3e9d3-181"><strong>Comportement de Live Communications Server 2005 (obsolète)</strong></span><span class="sxs-lookup"><span data-stu-id="3e9d3-181"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="3e9d3-182">Les valeurs prises en charge pour cet attribut sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-182">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-183">0 : archiver le corps du message [bit 0]</span><span class="sxs-lookup"><span data-stu-id="3e9d3-183">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-184">1 : ne pas archiver le corps du message [bit 0]</span><span class="sxs-lookup"><span data-stu-id="3e9d3-184">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="3e9d3-185"><strong>Comportement d’Office Communications Server 2007</strong></span><span class="sxs-lookup"><span data-stu-id="3e9d3-185"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="3e9d3-186">Les valeurs prises en charge pour cet attribut sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-186">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-187">0 : ArchiveFederationDefaultWithoutBody (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-187">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-188">1-2 : ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="3e9d3-188">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-189">3-4 : ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="3e9d3-189">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-190">5 : RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="3e9d3-190">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-191">6 : RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="3e9d3-191">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-192">7 : RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="3e9d3-192">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-193">8 : RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="3e9d3-193">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-194">9 : RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="3e9d3-194">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-195">10 : RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="3e9d3-195">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-196">11 : RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="3e9d3-196">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-197">12 : RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="3e9d3-197">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-198">13 : RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="3e9d3-198">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-199">14 : RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="3e9d3-199">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-200">15 : RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="3e9d3-200">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-201">16 : RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="3e9d3-201">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-202">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-202">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3e9d3-203">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-203">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-204">msRTCSIP-ArchiveFederationDefault (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-204">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3e9d3-205">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-205">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3e9d3-206">Obsolète dans Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-206">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-207">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3e9d3-208">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-208">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3e9d3-209">Obsolète dans Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-209">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-210">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="3e9d3-210">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p111">Cet attribut est un entier utilisé comme champ bit pour contrôler si les communications d’un utilisateur sont archivées. Ce contrôle est appliqué par la couche de l’agent d’archivage. Il est identifié pour la réplication des catalogues globaux.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p111">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived. This control is enforced by the archiving agent layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="3e9d3-214">Cet attribut est spécifique à un utilisateur ou contact unique.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-214">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="3e9d3-215">Les valeurs valides (et les positions de bits associées) dans Lync Server sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-215">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-216">0 : ne pas archiver (aucun bit défini)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-216">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-217">1 : obsolète (position de bit 0)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-217">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-218">2 : obsolète (position de bit 1)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-218">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-219">4 : archiver les communications internes (position de bit 2)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-219">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-220">8 : archiver les communications fédérées (position de bit 3)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-220">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="3e9d3-221">Les valeurs valides précédemment dans Live Communications Server 2005 sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-221">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-222">0 : utiliser la valeur par défaut définie par <strong>msRTCSIP-ArchiveDefault</strong> et <strong>msRTCSIP-ArchiveFederation</strong> dans cet ordre de priorité :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-222">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-223">1 : archiver</span><span class="sxs-lookup"><span data-stu-id="3e9d3-223">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-224">2 : ne pas archiver</span><span class="sxs-lookup"><span data-stu-id="3e9d3-224">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-225">3 : archiver sans le corps du message</span><span class="sxs-lookup"><span data-stu-id="3e9d3-225">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-226">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-226">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-227">msRTCSIP-ArchivingServerData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-227">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-228">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-228">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-229">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-229">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-230">msRTCSIP-ArchivingServerVersion (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-230">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p113">Cet attribut définit la version du service d’archivage. C’est un entier qui augmente de façon monotone et est incrémenté à chaque version officielle du produit. Les valeurs prises en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p113">This attribute defines the version of the Archiving service. This attribute is a monotonously increasing integer type that increments with each official product release. The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-234">Non défini : Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="3e9d3-234">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="3e9d3-235">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="3e9d3-235">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="3e9d3-236">                 Live Communications Server 2005 avec SP1</span><span class="sxs-lookup"><span data-stu-id="3e9d3-236">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-237">3 : Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="3e9d3-237">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-238">4 : Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3e9d3-238">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-239">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-239">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-240">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-240">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-241">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="3e9d3-241">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p114">Cet attribut indique le nom de domaine complet du serveur principal du pool. Étant donné qu’il ne peut exister qu’un serveur principal par pool, il s’agit d’un attribut à valeur unique.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p114">This attribute specifies the FQDN of the Back End Server of the pool. Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="3e9d3-244">Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-244">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-245">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-245">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-246">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="3e9d3-246">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-247">Cet attribut contient l’identificateur du pool qui héberge l’annuaire de conférences.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-247">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-248">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-248">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-249">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="3e9d3-249">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-250">Cet attribut contient l’identificateur d’un annuaire de conférences.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-250">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-251">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-251">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-252">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="3e9d3-252">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-253">Cet attribut contient l’identificateur du pool vers lequel l’annuaire de conférences est déplacé.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-253">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-254">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-254">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-255">msRTCSIP-default</span><span class="sxs-lookup"><span data-stu-id="3e9d3-255">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-256">Cet attribut booléen définit si l’utilisation téléphonique est une utilisation par défaut.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-256">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="3e9d3-257">Si la valeur est <strong>TRUE</strong>, l’utilisation téléphonique est une utilisation par défaut et ne peut pas être supprimée par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-257">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="3e9d3-258">Si la valeur est <strong>FALSE</strong>, l’utilisation peut être supprimée.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-258">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-259">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-259">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-260">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="3e9d3-260">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-261">Cet attribut identifie l’URL d’Office Communicator Web Access pour les utilisateurs qui se trouvent à l’extérieur de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-261">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-262">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-262">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-263">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="3e9d3-263">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-264">Cet attribut identifie l’URL d’Office Communicator Web Access pour les utilisateurs qui se trouvent à l’intérieur de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-264">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-265">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-265">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-266">msRTCSIP-DefaultLocationProfileLink (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-266">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-267">Cet attribut à valeur unique contient le nom unique (DN) d’un objet de classe de profil d’emplacement qui lui est affecté.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-267">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="3e9d3-268">Lien avant : <strong>ID de lien 11036</strong></span><span class="sxs-lookup"><span data-stu-id="3e9d3-268">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="3e9d3-269">Le lien arrière correspondant est <strong>msRTCSIP-ServerReferenceBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-269">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-270">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-270">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-271">msRTCSIP-DefaultPolicy (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-271">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-272">Cet attribut booléen indique si la stratégie est une stratégie par défaut.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-272">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="3e9d3-273">C’est le cas lorsque l’attribut a la valeur <strong>TRUE</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-273">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-274">Nouveauté d’Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="3e9d3-274">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="3e9d3-275">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-275">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-276">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-277">Cet attribut spécifie le nom de domaine complet (FQDN) du serveur Edge exécutant le service Edge d’accès, s’il est accessible directement, ou du programme d’équilibrage de la charge matérielle pour un pool de serveurs exécutant le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-277">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="3e9d3-278">Si les serveurs exécutant le service Edge d’accès sont accessibles uniquement par le biais d’un ou de plusieurs directeurs, cet attribut spécifie le nom de domaine complet (FQDN) et éventuellement le numéro de port du directeur ou du programme d’équilibrage de la charge matérielle servant de pool directeur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-278">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="3e9d3-279">Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-279">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-280">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-280">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3e9d3-281">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-281">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-282">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-283">Cet attribut représente le numéro de port qui doit être utilisé pour se connecter au serveur exécutant le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-283">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="3e9d3-284">La valeur correcte est un nombre entier spécifiant le port à utiliser.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-284">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="3e9d3-285">La valeur par défaut est 5061.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-285">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-286">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-286">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3e9d3-287">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-287">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-288">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-289">Cet attribut représente le délai d’expiration par défaut de l’abonnement aux informations de présence.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-289">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-290">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-290">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-291">msRTCSIP-DefRegistrationTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-291">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-292">Cet attribut représente le délai d’expiration d’inscription par défaut.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-292">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-293">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-293">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-294">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-295">Cet attribut représente le délai d’expiration par défaut de l’abonnement aux données d’itinérance.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-295">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-296">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-296">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-297">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="3e9d3-297">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-298">Cet attribut est utilisé dans une topologie de domaine fractionné et contient un nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="3e9d3-298">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-299">Nouveauté de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-299">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-300">msRTCSIP-Description (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-300">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-301">Cet attribut de type chaîne UNICODE à valeur unique contient une description conviviale de cet itinéraire téléphonique ou de cette règle de normalisation.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-301">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-302">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-302">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-303">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-303">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-304">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="3e9d3-304">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-305">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-305">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-306">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="3e9d3-306">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-307">Cet attribut représente un domaine configuré pour le serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-307">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-308">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="3e9d3-308">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-309">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-309">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-310">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-310">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-311">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="3e9d3-311">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-312">Cet attribut indique le nom de domaine complet du serveur exécutant le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-312">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="3e9d3-313">Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-313">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-314">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-314">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-315">msRTCSIP-EnableBestEffortNotify (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-315">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p119">Cet attribut détermine si un serveur génère une demande BENOTIFY (Best Effort NOTIFY), plutôt qu’une demande NOTIFY, en réponse à la demande SUBSCRIBE envoyée par un client. BENOTIFY est une extension d’amélioration des performances du protocole de transfert de notification de l’inscription dans laquelle le serveur génère des demandes BENOTIFY, plutôt que des demandes NOTIFY normales. Les performances sont améliorées dans la mesure où une demande BENOTIFY ne nécessite pas de réponse 200 OK d’un client, contrairement à la demande NOTIFY.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p119">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client. BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests. The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="3e9d3-319">La valeur correcte est <strong>TRUE</strong> ou <strong>FALSE</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-319">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3e9d3-320">Live Communications Server 2003 ne prend pas en charge les demandes BENOTIFY.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-320">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="3e9d3-321">Pour interagir avec les applications serveur écrites avec l’API serveur de Live Communications Server 2003 exécutée sur Live Communications Server 2005 et les serveurs tiers, les demandes BENOTIFY peuvent être désactivées en définissant sa valeur sur <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-321">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="3e9d3-322">Actuellement, cette fonction ne fait pas partie du processus de standardisation SIP IETF (Internet Engineering Task Force).</span><span class="sxs-lookup"><span data-stu-id="3e9d3-322">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="3e9d3-323">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-323">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3e9d3-324">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-324">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-325">msRTCSIP-EnableFederation (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-325">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p121">Cet attribut est un commutateur global utilisé par les administrateurs informatiques pour déterminer si les utilisateurs sont autorisés ou non à communiquer avec ceux d’autres organisations. Il permet à un administrateur de remplacer l’attribut <strong>FederationEnabled</strong> d’un utilisateur. Cet attribut peut être utile pour protéger le réseau interne contre les attaques en provenance d’Internet pouvant être causées par des vers ou des virus, ou encore contre les attaques ciblées contre la société.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p121">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations. It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute. This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="3e9d3-329">Les valeurs (et les positions des bits associées) prises en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-329">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-330">1 : activé pour la solution PIC (position de bit 0)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-330">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-331">2 : réservé (position de bit 1)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-331">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-332">4 : réservé (position de bit 2)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-332">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-333">8 : réservé (position de bit 3)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-333">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-334">16 : Contrôle d’appel distant activé [Téléphonie] (position de bit 4)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-334">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-335">64 : AllowOrganizeMeetingWithAnonymousParticipants (permet d’inviter des utilisateurs anonymes à des réunions) (position de bit 6)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-335">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-336">128 : UCEnabled (active les utilisateurs pour les communications unifiées) (position de bit 7)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-336">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-337">256 : EnabledForEnhancedPresence (active l’utilisateur pour la solution PIC) (position de bit 8)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-337">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-338">512 : RemoteCallControlDualMode (position de bit 9)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-338">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-339">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-339">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3e9d3-340">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-340">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-341">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="3e9d3-341">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-342">Cet attribut indique si les services d’entreprise sont chargés sur un serveur donné.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-342">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-343">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="3e9d3-343">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-344">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-344">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-345">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="3e9d3-345">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-346">Cet attribut contient l’indicatif pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-346">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-347">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-347">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-348">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="3e9d3-348">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p122">Cet attribut permet de contrôler si un utilisateur unique est activé pour la fédération. Il est appliqué par la couche Services d’entreprise. Il est identifié pour la réplication des catalogues globaux.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p122">This attribute controls whether a single user is enabled for federation. It is enforced by the Enterprise Services layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="3e9d3-352">Les valeurs valides sont <strong>true</strong> ou <strong>false</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-352">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-353">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-353">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-354">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="3e9d3-354">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-355">Cet attribut gérant plusieurs valeurs contient les noms de domaines de tous les serveurs Enterprise Edition associés à un pool.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-355">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="3e9d3-356">Lien arrière : <strong>ID de lien 11023</strong></span><span class="sxs-lookup"><span data-stu-id="3e9d3-356">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="3e9d3-357">Le lien avant correspondant à ce lien arrière est <strong>msRTCSIP-PoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-357">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-358">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-358">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-359">msRTCSIP-Gateways (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-359">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-360">Cet attribut de type chaîne gérant plusieurs valeurs contient une liste de passerelles et de ports (par passerelle).</span><span class="sxs-lookup"><span data-stu-id="3e9d3-360">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-361">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-361">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-362">msRTCSIP-GlobalSettingsData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-362">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p123">Cet attribut permet de stocker les paires nom:valeur. La paire nom:valeur déjà définie correspond au paramètre <strong>autoriser l’interrogation de présence</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p123">This attribute stores name:value pairs. The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-365">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-365">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-366">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="3e9d3-366">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-367">Cet attribut est un identificateur unique d’un groupe utilisé pour regrouper les entrées de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-367">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-368">Nouveauté de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-368">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-369">msRTCSIP-HomeServer (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-369">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3e9d3-370">Nouveauté de Live Communications Server 2003 (non utilisé).</span><span class="sxs-lookup"><span data-stu-id="3e9d3-370">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="3e9d3-371">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-371">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-372">msRTCSIP-HomeServerString (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-372">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3e9d3-373">Nouveauté de Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-373">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="3e9d3-374">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-374">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-375">msRTCSIP-HomeUsers (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-375">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3e9d3-376">Nouveauté de Live Communications Server 2003 (non utilisé).</span><span class="sxs-lookup"><span data-stu-id="3e9d3-376">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="3e9d3-377">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-377">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-378">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="3e9d3-378">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p124">Cet attribut permet de contrôler si un utilisateur unique est activé pour l’accès des utilisateurs extérieurs. Il est appliqué par la couche Services d’entreprise. Il est identifié pour la réplication des catalogues globaux.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p124">This attribute controls whether a single user is enabled for outside user access. It is enforced by the Enterprise Services layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="3e9d3-382">La valeur correcte est <strong>TRUE</strong> ou <strong>FALSE</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-382">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-383">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-383">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-384">msRTCSIP-IsMaster (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-384">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3e9d3-385">Nouveauté de Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="3e9d3-385">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="3e9d3-386">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-386">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-387">msRTCSIP-Line</span><span class="sxs-lookup"><span data-stu-id="3e9d3-387">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-388">Cet attribut à valeur unique contient l’ID de périphérique (l’URI SIP ou l’URI TEL du téléphone que les contrôles utilisateur) utilisent dans Lync pour la téléphonie.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-388">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="3e9d3-389">Il est identifié pour la réplication des catalogues globaux et est indexé.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-389">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="3e9d3-390">Si un utilisateur est activé pour Voix Entreprise, cet attribut stocke la version normalisée E.164 du numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-390">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-391">Nouveauté de Microsoft Office Live Communications Server 2005 avec SP1</span><span class="sxs-lookup"><span data-stu-id="3e9d3-391">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-392">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="3e9d3-392">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p126">Cet attribut à valeur unique contient l’URI SIP du serveur de passerelle CSTA-SIP. Il est identifié pour la réplication des catalogues globaux mais n’est pas indexé.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p126">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server. This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-395">Nouveauté de Microsoft Office Live Communications Server 2005 avec SP1</span><span class="sxs-lookup"><span data-stu-id="3e9d3-395">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-396">msRTCSIP-LocalNormalizationData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-396">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-397">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-397">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-398">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-398">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-399">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-399">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-400">msRTCSIP-LocalNormalizationLinks (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-400">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p127">Cet attribut gérant plusieurs valeurs contient la liste des noms uniques (DN) des règles de normalisation locales associés à ce profil d’emplacement. Ce type d’attribut est un attribut binaire de nom unique. Il existe une relation un à plusieurs entre le profil d’emplacement et les règles de normalisation locales. L’ordre des noms uniques des règles de normalisation locales doit correspondre à l’ordre défini par l’administrateur. La conservation de cet ordre est assurée par la partie binaire de l’attribut binaire de nom unique, qui définit l’index de classement.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p127">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile. The type of this attribute is a DN binary. There is a one-to-many relationship between location profile and local normalization rules. The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator. The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="3e9d3-406">Lien avant : <strong>ID de lien 11034</strong></span><span class="sxs-lookup"><span data-stu-id="3e9d3-406">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="3e9d3-407">Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-LocationProfileBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-407">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-408">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-408">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-409">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-409">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-410">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="3e9d3-410">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-411">Cet attribut contient une liste d’options pour la règle de normalisation.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-411">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-412">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-412">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-413">msRTCSIP-LocationName (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-413">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p128">Cet attribut à valeur unique contient le nom convivial du profil d’emplacement qui indique l’emplacement représenté par le profil. Comme il peut exister plusieurs profils d’emplacement, l’administrateur doit être en mesure de les distinguer.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p128">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents. Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-416">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-416">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-417">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-417">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-418">msRTCSIP-locationProfileBL (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-418">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p129">Cet attribut gérant plusieurs valeurs contient la liste des noms uniques de profil d’emplacement. Il indique le lien arrière d’un ou plusieurs profils d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p129">This multi-valued attribute contains a list of location profile distinguished names. This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="3e9d3-421">Lien arrière : <strong>ID de lien 11035</strong></span><span class="sxs-lookup"><span data-stu-id="3e9d3-421">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="3e9d3-422">Cet attribut correspond au lien avant <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-422">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-423">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-423">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-424">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-424">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-425">msRTCSIP-LocationProfileData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-425">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-426">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-426">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-427">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-427">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-428">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-428">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-429">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="3e9d3-429">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-430">Cet attribut contient les options pour le profil d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-430">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-431">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-431">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-432">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="3e9d3-432">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-433">Cet attribut gérant plusieurs valeurs contient une liste de contacts d’application.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-433">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-434">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-434">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-435">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="3e9d3-435">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-436">Cet attribut gérant plusieurs valeurs contient une liste de profils d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-436">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-437">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-437">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-438">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-439">Cet attribut représente le nombre maximal de demandes de recherches actives par serveur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-439">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-440">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-440">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-441">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-442">Cet attribut représente le nombre maximal d’abonnements par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-442">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-443">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-443">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-444">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-445">Cet attribut représente le délai d’expiration maximal d’abonnement.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-445">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-446">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-446">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-447">msRTCSIP-MaxRegistrationsTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-447">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-448">Cet attribut représente le délai d’expiration maximal d’inscription.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-448">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-449">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-449">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-450">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-451">Cet attribut représente le délai d’expiration maximal d’abonnement aux données d’itinérance.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-451">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-452">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-452">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-453">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="3e9d3-453">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-454">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-454">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-455">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-455">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-456">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="3e9d3-456">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p130">Cet attribut est un attribut de point de contrôle du service sous la classe d’ordinateur qui définit un lien renvoyant à son répartiteur d’unité de contrôle multipoint (MCU) parent. Le point de contrôle du service et l’attribut sont créés pour chaque MCU Microsoft. Chaque MCU Microsoft doit trouver le serveur principal du pool auquel il appartient afin d’en extraire des paramètres de niveau pool.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p130">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs. This service control point and attribute is created for every Microsoft MCU. Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="3e9d3-p131">La valeur de cet attribut est le nom unique (DN) du répartiteur de MCU. Il s’agit d’un attribut à valeur unique identifié pour la réplication des catalogues globaux.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p131">The value of this attribute is the distinguished name (DN) of the MCU Factory. This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="3e9d3-462">Lien avant : <strong>ID de lien 11026</strong></span><span class="sxs-lookup"><span data-stu-id="3e9d3-462">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="3e9d3-463">Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-MCUServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-463">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-464">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-464">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-465">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="3e9d3-465">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p132">Il s’agit d’un attribut réservé de type chaîne gérant plusieurs valeurs. Les paramètres qui y sont stockés sont représentés par des paires nom=valeur. Les paires nom=valeur actuellement définies sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p132">This is a multi-string reserved attribute. Settings stored in this attribute are represented as name=value pairs. Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-469">FactoryURL = &lt;URL&gt;</span><span class="sxs-lookup"><span data-stu-id="3e9d3-469">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-470">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-470">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-471">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="3e9d3-471">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-472">Cet attribut à valeur unique contient le nom unique (DN) d’un répartiteur de MCU unique associé à un pool.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-472">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="3e9d3-473">Lien avant : <strong>ID de lien 11024</strong></span><span class="sxs-lookup"><span data-stu-id="3e9d3-473">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="3e9d3-474">Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-PoolAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-474">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-475">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-475">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-476">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="3e9d3-476">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-477">Cet attribut de type chaîne à valeur unique spécifie le GUID du fournisseur du répartiteur de MCU.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-477">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="3e9d3-478">Selon la valeur du GUID, le répartiteur de MCU détermine s’il doit traiter ce type de MCU.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-478">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="3e9d3-479">Si la valeur GUID est <strong>{F0810510-424F-46ef-84fe-6CC720DF1791}</strong>, le processus d’usine MCU (disponible par défaut dans Lync Server) le traitera.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-479">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="3e9d3-480">Dans le cas contraire, il ne traite pas le type de MCU.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-480">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-481">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-481">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-482">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="3e9d3-482">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p134">Cet attribut gérant plusieurs valeurs contient une liste de noms uniques (DN), à savoir la liste de tous les serveurs MCU de même type et fournisseur associés à ce répartiteur de MCU. Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p134">This attribute is a multi-valued list of distinguished names (DN). This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="3e9d3-486">Lien arrière : ID de lien 11027</span><span class="sxs-lookup"><span data-stu-id="3e9d3-486">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="3e9d3-487">Le lien avant correspondant à ce lien arrière est <strong>msRTCSIP-MCUFactoryAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-487">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-488">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-488">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-489">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="3e9d3-489">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-490">Cet attribut de type chaîne à valeur unique spécifie le support géré par le MCU.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-490">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="3e9d3-491">Les types de valeurs gérés sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-491">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-492">satisfaire</span><span class="sxs-lookup"><span data-stu-id="3e9d3-492">meeting</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-493">audio-vidéo</span><span class="sxs-lookup"><span data-stu-id="3e9d3-493">audio-video</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-494">conversation</span><span class="sxs-lookup"><span data-stu-id="3e9d3-494">chat</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-495">Téléphone-CONF</span><span class="sxs-lookup"><span data-stu-id="3e9d3-495">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-496">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-496">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-497">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="3e9d3-497">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p135">Cet attribut de type chaîne à valeur unique représente le nom d’un fournisseur de MCU. Pour tous les MCU Microsoft, cet attribut a la valeur <strong>Microsoft Corporation</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p135">This attribute is a single-valued string that specifies an MCU vendor’s name. All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-500">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-500">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-501">msRTCSIP-MeetingFlags (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-501">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p136">Cet attribut définit différentes options de réunion qui sont activées globalement pour tous les objets utilisateur ou contact. Sa valeur est un masque de bits de type nombre entier.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p136">This attribute defines different meeting options that are enabled globally for all users or contact objects. This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="3e9d3-504">Les valeurs (et les positions des bits associées) prises en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-504">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-505">0 : AllowOrganizeMeetingWithAnonymousParticipants a pour valeur Aucun (ne pas autoriser les utilisateurs à inviter des utilisateurs anonymes à des réunions) (aucun bit défini)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-505">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-506">4 : AllowOrganizeMeetingWithAnonymousParticipants a est tout le monde (autoriser tous les utilisateurs à inviter des utilisateurs anonymes à des réunions) (position de bit 2)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-506">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-507">8 : AllowOrganizeMeetingWithAnonymousParticipants a la valeur UsePerUserSetting (permet aux utilisateurs d’inviter des utilisateurs anonymes à des réunions en fonction du paramètre par utilisateur) (position de bit 3)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-507">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-508">16 : UserPerUserMeetingPolicy (la stratégie de réunion est définie par utilisateur) (position de bit 4)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-508">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-509">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-509">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-510">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-510">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-511">msRTCSIP-MeetingPolicy (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-511">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-512">Cet attribut définit le nom unique (DN) de la stratégie que l’administrateur a attribué à cet utilisateur sous la forme d’un attribut à valeur unique.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-512">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-513">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-513">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-514">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-514">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-515">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-516">Cet attribut représente le délai d’expiration minimal d’abonnement aux informations de présence.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-516">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-517">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-517">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-518">msRTCSIP-MinRegistrationTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-518">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-519">Cet attribut représente le délai d’expiration minimal d’inscription.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-519">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-520">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-520">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-521">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-521">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-522">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-523">Cet attribut représente le délai d’expiration minimal de l’abonnement aux données d’itinérance.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-523">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-524">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-524">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-525">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-525">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-526">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="3e9d3-526">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-527">Cet attribut est utilisé pour stocker le serveur principal SQL Server mis en miroir utilisé par le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-527">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-528">Nouveauté de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-528">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-529">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="3e9d3-529">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-530">Cet attribut contient des options et des indicateurs qui définissent les paramètres de mobilité.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-530">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-531">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-531">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-532">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="3e9d3-532">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-533">Cet attribut contient le nom unique pour un objet de stratégie de mobilité.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-533">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-534">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-534">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-535">msRTCSIP-NumDevicesPerUser (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-535">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-536">Cet attribut représente le nombre autorisé de périphériques sur lesquels un utilisateur peut s’inscrire pour les communications SIP et s’abonner aux données de présence.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-536">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-537">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-537">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-538">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-538">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-539">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="3e9d3-539">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p137">Cet attribut définit les options qui sont activées pour l’objet utilisateur ou contact. Sa valeur est un masque de bits de type nombre entier. Chaque option est représentée par un bit. Il est identifié pour la réplication des catalogues globaux.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p137">This attribute specifies the options that are enabled for the user or contact object. This attribute is a bit-mask value of type integer. Each option is represented by a bit. This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="3e9d3-544">Les valeurs (et les positions des bits associées) prises en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-544">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-545">1 : activé pour la solution PIC (position de bit 0)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-545">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-546">2 : réservé (position de bit 1)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-546">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-547">4 : réservé (position de bit 2)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-547">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-548">8 : réservé (position de bit 3)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-548">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-549">16 : Contrôle d’appel distant activé [Téléphonie] (position de bit 4)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-549">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-550">64 : AllowOrganizeMeetingWithAnonymousParticipants (permet d’inviter des utilisateurs anonymes à des réunions) (position de bit 6)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-550">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-551">128 : UCEnabled (active les utilisateurs pour les communications unifiées) (position de bit 7)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-551">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-552">256 : EnabledForEnhancedPresence (active l’utilisateur pour la solution PIC) (position de bit 8)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-552">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-553">512 : RemoteCallControlDualMode (position de bit 9)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-553">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-554">Nouveauté de Live Communications Server 2005 avec SP1.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-554">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-555">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="3e9d3-555">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-556">Cet attribut est utilisé dans les topologies à forêts de ressources et à forêt centrale pour activer l’authentification unique lorsque l’identificateur ObjectSID du compte principal Windows NT Server d’un utilisateur est copié dans ce même attribut de l’objet utilisateur ou contact correspondant dans la forêt de ressources ou la forêt centrale.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-556">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="3e9d3-557">Communicator Web Access recherche un utilisateur dans AD DS à l’aide de cet attribut ou de l’ObjectSID de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-557">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="3e9d3-558">Il est identifié pour la réplication des catalogues globaux.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-558">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-559">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="3e9d3-559">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-560">Cet attribut est l’URN (Uniform Resource Name) du propriétaire pour un contact d’application.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-560">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-561">Nouveauté de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-561">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-562">msRTCSIP-Pattern (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-562">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p139">Cet attribut de type chaîne à valeur unique contient un modèle de correspondance permettant de convertir les numéros à composer au format E.164. La conversion est appliquée à tout numéro correspondant au modèle.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p139">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format. If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-565">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-565">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-566">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-566">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-567">msRTCSIP-PhoneRouteBL (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-567">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p140">Cet attribut gérant plusieurs valeurs contient la liste des noms uniques (DN) d’itinéraires téléphoniques. Il indique le lien arrière d’un ou plusieurs itinéraires téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p140">This multi-valued attribute contains a list of phone route distinguished names (DN). This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="3e9d3-570">Lien arrière : <strong>ID de lien 11033</strong></span><span class="sxs-lookup"><span data-stu-id="3e9d3-570">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="3e9d3-571">Cet attribut correspond au lien avant <strong>msRTCSIP-RouteUsageLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-571">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-572">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-572">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-573">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-573">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-574">msRTCSIP-PhoneRouteData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-574">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-575">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-575">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-576">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-576">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-577">msRTCSIP-PhoneRouteName (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-577">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-578">Cet attribut de type chaîne UNICODE à valeur unique indique le nom convivial de l’itinéraire téléphonique, qui peut ainsi être facilement référencé par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-578">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-579">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-579">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-580">msRTCSIP-PhoneUsageData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-580">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-581">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-581">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-582">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-582">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-583">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-583">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-584">msRTCSIP-PolicyContent (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-584">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p141">Cet attribut de type chaîne UNICODE à valeur unique contient la définition de stratégie au format XML. La définition de schéma XML est commune à différents types de stratégies ; seuls les paramètres varient en fonction du type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p141">This attribute is a single-valued Unicode string. This string attribute contains the policy definition in XML format. The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="3e9d3-588">La définition de schéma XML (XSD) est définie de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-588">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="3e9d3-589">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-589">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-590">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-590">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-591">msRTCSIP-PolicyData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-591">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-592">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-592">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-593">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-593">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-594">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-594">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-595">msRTCSIP-PolicyType (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-595">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p142">Cet attribut de type chaîne Unicode à valeur unique contient le type de stratégie. Les types pris en charge sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p142">This single-valued Unicode string attribute contains the policy type. Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-598">satisfaire</span><span class="sxs-lookup"><span data-stu-id="3e9d3-598">meeting</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-599">téléphonie</span><span class="sxs-lookup"><span data-stu-id="3e9d3-599">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-600">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-600">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-601">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-601">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-602">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="3e9d3-602">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-603">Cet attribut spécifie un lien permettant de revenir au pool auquel appartient un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-603">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="3e9d3-604">Cet attribut est défini, que l’ordinateur utilise ou non la version Standard Edition ou Enterprise Edition de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-604">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="3e9d3-605">Il est identifié pour la réplication des catalogues globaux.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-605">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="3e9d3-606">La valeur correcte est le nom de domaine du pool.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-606">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="3e9d3-607">Lien avant : <strong>ID de lien 11022</strong></span><span class="sxs-lookup"><span data-stu-id="3e9d3-607">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="3e9d3-608">Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-FrontEndServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-608">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-609">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-609">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-610">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="3e9d3-610">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-611">Cet attribut gérant plusieurs valeurs contient la liste des noms uniques (DN) des pools auxquels le répartiteur de MCU est associé.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-611">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="3e9d3-612">Lien arrière : <strong>ID de lien 11025</strong></span><span class="sxs-lookup"><span data-stu-id="3e9d3-612">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="3e9d3-613">Le lien avant correspondant à ce lien arrière est <strong>msRTCSIP-MCUFactoryPath</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-613">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-614">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-614">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-615">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="3e9d3-615">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-616">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-616">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-617">Nouveauté de Live Communications Server 2005 avec SP1.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-617">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-618">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="3e9d3-618">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p144">Cet attribut définit le nom arbitraire d’un pool affiché par la console de gestion. Ce nom peut être modifié par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p144">This attribute specifies an arbitrary name for a pool that is displayed by the management console. This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="3e9d3-621">La valeur correcte est une chaîne représentant le nom d’un pool.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-621">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-622">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-622">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-623">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="3e9d3-623">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p145">Cet attribut est de type chaîne UNICODE à valeur unique. Lorsqu’elle est définie, la valeur de cet attribut représente le nom de domaine complet du pool si l’administrateur souhaite créer un pool frontal en lui attribuant un nom de domaine complet non conforme à la structure de domaines Active Directory dans lequel il créé le pool frontal (un espace de noms SIP dissocié de l’espace de noms DNS, par exemple).</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p145">This attribute is a single-valued string value. The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="3e9d3-p146">Nous vous recommandons de mapper le nom de domaine complet du pool frontal sur la partie de nom de domaine du domaine Active Directory dans lequel réside le pool. Par conséquent, quand la valeur de l’attribut n’est pas définie, le nom de domaine complet du pool frontal correspond par défaut à la structure des noms de domaine Active Directory, telle qu’indiquée par l’attribut <strong>dnsHostName</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p146">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides. Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-628">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-628">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-629">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="3e9d3-629">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-630">Liste à plusieurs valeurs des noms de domaine de tous les serveurs Lync Server, Enterprise Edition associés à un pool.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-630">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="3e9d3-631">Cet attribut de type nombre entier détermine si le pool prend en charge la messagerie instantanée et les données de présence, ainsi que les réunions.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-631">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="3e9d3-632">Les types de valeurs pris en charge sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-632">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-633">Non défini : messagerie instantanée et service de présence (Live Communications Server 2005 et 2003)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-633">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-634">1 : service de présence et de messagerie instantanée (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-634">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-635">2 : messagerie instantanée et service de présence et de réunion (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-635">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-636">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-636">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-637">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="3e9d3-637">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p148">Cet attribut indique si un pool de serveurs exécute Standard Edition Server ou Enterprise Edition Server. Sa valeur est un masque de bits de type nombre entier. Chaque option est représentée par un bit.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p148">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server. This attribute is a bit-mask value of type integer. Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="3e9d3-641">Les valeurs (et les positions des bits associées) prises en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-641">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-642">1 : Standard Edition Server, héberge des utilisateurs (position de bit 0)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-642">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-643">2 : Enterprise Edition Server, héberge des utilisateurs (position de bit 1)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-643">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-644">4 : Standard Edition Server, héberge des applications (position de bit 2)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-644">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-645">8 : Enterprise Edition Server, héberge des applications (position de bit 3)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-645">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="3e9d3-646">Étant donné que Lync Server ne prend pas en charge les pools qui hébergent uniquement les applications, les seules valeurs valides sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-646">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-647">5 : Standard Edition Server, héberge des utilisateurs et des applications (positions de bit 0 et 2)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-647">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-648">10 : Enterprise Edition Server, héberge des utilisateurs et des applications (positions de bit 1 et 3)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-648">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-649">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-649">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-650">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="3e9d3-650">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p149">Cet attribut définit la version du pool. Sa valeur est un entier incrémenté à chaque version majeure du produit.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p149">This attribute defines the pool version. It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="3e9d3-653">Les types de valeurs pris en charge sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-653">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-654">0 : Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="3e9d3-654">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-655">1 : Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="3e9d3-655">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-656">2 : Live Communications Server 2005 avec SP1</span><span class="sxs-lookup"><span data-stu-id="3e9d3-656">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-657">3 : Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="3e9d3-657">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-658">4 : Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3e9d3-658">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-659">5 : Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3e9d3-659">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-660">Live Communications Server 2005 avec SP1.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-660">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-661">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="3e9d3-661">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-662">Cet attribut contient des options et des indicateurs qui définissent les paramètres de présence.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-662">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-663">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-663">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-664">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="3e9d3-664">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-665">Cet attribut contient le nom unique pour un objet de stratégie de présence.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-665">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-666">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-666">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-667">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="3e9d3-667">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p150">Cet attribut permet d’activer un utilisateur ou un contact pour la messagerie SIP. Il est ajouté à la classe contact car dans la topologie à forêt centrale, les objets contact (et pas les objets utilisateur) sont activés pour SIP.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p150">This attribute enables a user or contact for SIP messaging. It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="3e9d3-670">La valeur correcte est le nom unique du serveur Standard Edition ou du pool frontal Enterprise Edition hébergeant un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-670">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-671">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-671">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-672">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="3e9d3-672">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-673">Cet attribut contient l’adresse SIP d’un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-673">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-674">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="3e9d3-674">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-675">Cet attribut contient l’ID de périphérique du périphérique de ligne privée.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-675">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-676">Nouveauté de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-676">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-677">msRTCSIP-routable</span><span class="sxs-lookup"><span data-stu-id="3e9d3-677">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-678">Cet attribut est un attribut booléen utilisé pour déterminer si Lync Server est autorisé à acheminer vers ce service à l’aide de son adresse GRUU.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-678">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="3e9d3-679">Si cette valeur est définie sur <strong>true</strong>, Lync Server est autorisé à acheminer vers ce service.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-679">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="3e9d3-680">Si cette valeur est définie sur <strong>false</strong>, Lync Server n’est pas autorisé à acheminer vers ce service.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-680">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-681">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-681">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-682">msRTCSIP-RouteUsageAttribute (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-682">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p152">Cet attribut de type chaîne UNICODE à valeur unique définit un attribut qualifiant l’utilisation d’un itinéraire téléphonique. La sélection d’un itinéraire téléphonique est déterminée en fonction de deux éléments : l’attribut d’utilisation affecté à l’itinéraire téléphonique et les attributs d’utilisation de la stratégie autorisée de l’appelant. Le premier itinéraire dont l’attribut d’utilisation correspond à l’utilisation autorisée de l’appelant est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p152">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route. Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes. The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-686">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-686">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-687">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-687">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-688">msRTCSIP-RouteUsageLinks (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-688">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-689">Cet attribut gérant plusieurs valeurs contient la liste des noms uniques (DN) d’utilisation d’itinéraire téléphonique.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-689">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="3e9d3-690">Lien avant : <strong>ID de lien 11032</strong></span><span class="sxs-lookup"><span data-stu-id="3e9d3-690">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="3e9d3-691">Cet attribut est un lien avant correspondant au lien arrière <strong>msRTCSIP-PhoneRouteBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-691">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-692">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-692">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-693">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="3e9d3-693">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-694">Cet attribut contient le nom unique pointant vers le pool par lequel doit transiter tout le trafic SIP destiné à ce MCU ou à ce service approuvé.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-694">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-695">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-695">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-696">msRTCSIP-RuleName (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-696">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-697">Cet attribut de type chaîne UNICODE à valeur unique indique le nom convivial de la règle de normalisation, qui peut ainsi être facilement référencée par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-697">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-698">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-698">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-699">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-699">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-700">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="3e9d3-700">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-701">Cet attribut représente la version du schéma actuellement déployée dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-701">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-702">msRTCSIP-SearchMaxRequests (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-702">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-703">Cet attribut limite le nombre de résultats de recherche à renvoyer à partir d’une recherche d’annuaire lorsqu’un utilisateur recherche un contact à l’aide de Communicator.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-703">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="3e9d3-704">Il remplace la valeur fournie par le client.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-704">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-705">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-705">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-706">msRTCSIP-SearchMaxResults (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-706">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-707">Cet attribut limite le nombre de demandes de recherche renvoyées.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-707">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-708">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-708">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-709">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="3e9d3-709">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p154">Cet attribut gérant plusieurs valeurs est un lien arrière qui contient une liste de noms uniques (DN). Ceux-ci pointent vers un pool ou un objet <strong>TrustedService</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p154">This multi-valued attribute is a back link that contains a list of distinguished names (DN). These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="3e9d3-712">Cet attribut correspond au lien avant <strong>msRTCSIP-TrustedServiceLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-712">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-713">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-713">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-714">msRTCSIP-Serverprotection</span><span class="sxs-lookup"><span data-stu-id="3e9d3-714">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-715">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-715">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-716">msRTCSIP-ServerReferenceBL (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-716">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p155">Cet attribut gérant plusieurs valeurs contient une liste de noms uniques. Ceux-ci sont des liens secondaires qui référencent d’autres objets Serveur auxquels il est possible d’attribuer un profil d’emplacement par défaut.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p155">This multi-valued attribute contains a list of distinguished names. These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="3e9d3-719">Lien arrière : <strong>ID de lien 11037</strong></span><span class="sxs-lookup"><span data-stu-id="3e9d3-719">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="3e9d3-720">Le lien avant correspondant à ce lien arrière est <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-720">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="3e9d3-721">Cet attribut de lien arrière référence uniquement des pools et des serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-721">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-722">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-722">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-723">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-723">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-724">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="3e9d3-724">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p156">Cet attribut définit la version du serveur. Ce numéro de version s’applique à tous les rôles serveurs. C’est un entier qui augmente de façon monotone et est incrémenté à chaque version officielle du produit.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p156">This attribute defines the version information of the server. This version number applies to all server roles. It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="3e9d3-728">Les valeurs prises en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-728">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-729">Non défini : Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="3e9d3-729">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="3e9d3-730">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="3e9d3-730">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="3e9d3-731">                 Live Communications Server 2005 avec SP1</span><span class="sxs-lookup"><span data-stu-id="3e9d3-731">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-732">3 : Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="3e9d3-732">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-733">4 : Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3e9d3-733">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-734">5 : Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3e9d3-734">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-735">6 : Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e9d3-735">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-736">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-736">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-737">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="3e9d3-737">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-738">Cet attribut à valeur unique de type entier définit le type d’objet vers lequel pointe <strong>msDS-SourceObjectDN</strong>, comme suit :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-738">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-739">null | 0x00000001 : représente un objet utilisateur principal Windows NT Server issu d’une autre forêt.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-739">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-740">Les attributs suivants représentent un type de groupe issu d’une autre forêt pour le développement des groupes de distribution :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-740">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-741">0x00000002 : ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="3e9d3-741">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-742">0x00000004 : ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="3e9d3-742">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-743">0x00000004 : ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="3e9d3-743">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-744">0x00000008 : ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="3e9d3-744">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-745">0x80000000 : ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="3e9d3-745">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-746">0x90000000 : représente un objet standard automatique ou accès abonné de la même forêt ou d’une autre forêt.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-746">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-747">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-747">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-748">msRTCSIP-SubscriptionAuthRequired (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-748">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3e9d3-749">Nouveauté de Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-749">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="3e9d3-750">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-750">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-751">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="3e9d3-751">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-752">Cet attribut vous permet de déplacer un utilisateur ou un contact d’un pool Lync Server vers un autre.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-752">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="3e9d3-753">Il est ajouté à la classe contact car dans la topologie à forêt centrale, les objets contact (et pas les objets utilisateur) sont activés pour SIP.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-753">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="3e9d3-754">La valeur correcte est le nom unique du serveur Standard Edition ou du pool frontal de destination vers lequel l’utilisateur doit être déplacé.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-754">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-755">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-755">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-756">msRTCSIP-TargetPhoneNumber (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-756">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-757">Cet attribut de type chaîne à valeur unique contient un modèle ou une plage de numéros de téléphone à acheminer vers les passerelles spécifiées, définies dans <strong>msRTCSIP-Gateways</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-757">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-758">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-758">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-759">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="3e9d3-759">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-760">Cet attribut stocke des paires nom-valeur pour les stratégies cibles pour les utilisateurs de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-760">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-761">Nouveauté de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-761">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-762">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="3e9d3-762">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-763">Cet attribut stocke l’identificateur unique d’un locataire.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-763">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-764">Nouveauté de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-764">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-765">msRTCSIP-Translation (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-765">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-766">Cet attribut est utilisé par la fonctionnalité voix de Lync Server et contient la chaîne de conversion à appliquer sur le numéro composé, si une correspondance est trouvée.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-766">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-767">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-767">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="3e9d3-768">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-768">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-769">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="3e9d3-769">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-770">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-770">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-771">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-771">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-772">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="3e9d3-772">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p158">Cet attribut de type chaîne contient le nom de domaine complet du MCU. Il gère une valeur unique. Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p158">This attribute is a string value that contains the FQDN of the MCU. This is a single-valued attribute. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-776">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-776">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-777">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="3e9d3-777">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-778">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-778">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-779">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-779">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-780">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="3e9d3-780">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p159">Cet attribut de type chaîne contient le nom de domaine complet du serveur exécutant le serveur proxy. Il gère une valeur unique. Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p159">This attribute is a string value that contains the FQDN of the server running Proxy Server. This attribute is single-valued. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-784">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-784">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-785">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="3e9d3-785">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-786">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-786">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-787">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="3e9d3-787">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-788">Cet attribut à valeur unique représente le nom de domaine complet d’un serveur approuvé.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-788">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-789">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-789">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-790">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="3e9d3-790">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-791">Cet attribut définit le numéro de version d’un serveur de la liste de serveurs approuvés.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-791">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="3e9d3-792">Les valeurs prises en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-792">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-793">NULL : Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="3e9d3-793">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-794">2 : Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="3e9d3-794">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-795">3 : Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="3e9d3-795">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-796">4 : Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3e9d3-796">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-797">5 : Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3e9d3-797">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-798">6 : Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e9d3-798">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-799">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-799">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-800">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="3e9d3-800">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-801">Cet attribut définit les options activées pour le service approuvé.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-801">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-802">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-802">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-803">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="3e9d3-803">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-804">Cet attribut gérant plusieurs valeurs contient une liste de noms uniques (DN) référençant un objet service approuvé, tel qu’un service d’authentification Media Relay.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-804">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="3e9d3-805">Un service d’authentification de serveur relais multimédia (colocalisé physiquement sur le serveur Edge exécutant le service de conférence A/V) doit être associé à un pool pour prendre en charge les scénarios audio pour les utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-805">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="3e9d3-806">Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-ServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-806">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-807">UC</span><span class="sxs-lookup"><span data-stu-id="3e9d3-807">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-808">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="3e9d3-808">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-809">Cet attribut est un entier qui définit le numéro de port permettant la connexion à ce service GRUU.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-809">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-810">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-810">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-811">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="3e9d3-811">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-812">Cet attribut de type chaîne définit le type de service GRUU qu’il représente.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-812">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="3e9d3-813">Les types de services GRUU pris en charge sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-813">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-814">MediationServer</span><span class="sxs-lookup"><span data-stu-id="3e9d3-814">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-815">Passerelle</span><span class="sxs-lookup"><span data-stu-id="3e9d3-815">Gateway</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-816">MRAS (Media Relay Authentication Service, service d’authentification Media Relay) ;</span><span class="sxs-lookup"><span data-stu-id="3e9d3-816">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-817">QoSM</span><span class="sxs-lookup"><span data-stu-id="3e9d3-817">QoSM</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-818">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="3e9d3-818">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-819">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-819">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-820">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="3e9d3-820">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-821">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-821">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-822">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-822">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-823">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="3e9d3-823">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-824">Cet attribut est une valeur de type String qui contient le nom de domaine complet du serveur IIS exécutant les services Web Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-824">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="3e9d3-825">Il gère une valeur unique.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-825">This is a single-valued attribute.</span></span> <span data-ttu-id="3e9d3-826">Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-826">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-827">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-827">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-828">msRTCSIP-UCFlags (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-828">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p162">Cet attribut définit différentes options relatives aux communications unifiées qui sont activées globalement pour tous les objets utilisateur ou contact. Sa valeur est un masque de bits de type nombre entier. Chaque option est représentée par un bit.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p162">This attribute defines different UC options that are enabled globally to all user or contact objects. This attribute is a bit-mask value of integer type. Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="3e9d3-832">Les valeurs (et les positions des bits associées) prises en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-832">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-833">4 : UsePerUserUCPolicy (position de bit 2)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-833">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="3e9d3-834">Lorsque ce bit est activé, la stratégie de communications unifiées est définie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-834">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-835">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-835">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-836">msRTCSIP-UCPolicy (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-836">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-837">Cet attribut à valeur unique contient le nom unique (DN) de la stratégie de communications unifiées que l’administrateur a attribué à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-837">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-838">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-838">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-839">msRTCSIP-UserDomainList (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-839">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p163">Cet attribut recense tous les domaines d’une forêt hébergeant des utilisateurs SIP. La liste est vide par défaut, ce qui indique que tous les domaines de la forêt sont activés pour SIP.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p163">This attribute provides a list of all the domains in a forest that host SIP-enabled users. The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="3e9d3-842">Les valeurs prises en charge sont plusieurs chaînes représentant les noms de domaine spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-842">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-843">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-843">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="3e9d3-844">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-844">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-845">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="3e9d3-845">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-846">Cet attribut détermine si l’utilisateur est actuellement activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-846">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-847">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="3e9d3-847">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-848">Cet attribut à valeurs multiples contient une liste de paires nom-valeur au format &quot;nom = valeur. &quot; Cet attribut est marqué pour la réplication de catalogue global.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-848">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-849">Nouveauté de Live Communications Server 2005 avec SP1.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-849">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-850">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="3e9d3-850">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-851">Cet attribut contient le nom unique (DN) pointant sur un objet de profil d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-851">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-852">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-852">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-853">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="3e9d3-853">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-854">Cet attribut permet de stocker les paires nom-valeur des stratégies utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-854">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-855">Nouveauté de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-855">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-856">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="3e9d3-856">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p164">Cet attribut gérant plusieurs valeurs contient une liste de noms uniques avec une partie binaire (DN_WITH_BINARY) pointant vers des stratégies utilisateur globales de différents types. La partie binaire indique le type de stratégie vers laquelle pointe la partie DN.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p164">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types. The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="3e9d3-859">Les valeurs binaires correctes sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-859">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-860">0x00000001 : stratégie de réunion</span><span class="sxs-lookup"><span data-stu-id="3e9d3-860">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-861">0x00000002 : stratégie de communications unifiées</span><span class="sxs-lookup"><span data-stu-id="3e9d3-861">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-862">0x00000005 : stratégie de présence</span><span class="sxs-lookup"><span data-stu-id="3e9d3-862">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-863">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-863">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-864">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="3e9d3-864">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p165">Cette valeur est l’ID de groupe de routage SIP. Les utilisateurs du même groupe s’inscrivent sur le même serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p165">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-867">Nouveauté de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-867">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-868">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="3e9d3-868">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p166">Cet attribut gère plusieurs valeurs. Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p166">This is a multi-valued attribute. This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-871">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-871">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-872">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="3e9d3-872">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-873">Cet attribut à valeur unique pointe vers le pool ou le serveur Standard Edition auquel appartiennent les composants web.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-873">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="3e9d3-874">Lien avant : <strong>ID de lien 11028</strong></span><span class="sxs-lookup"><span data-stu-id="3e9d3-874">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="3e9d3-875">Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-WebComponentsServer</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-875">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-876">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-876">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-877">msRTCSIP-Webcomponentsserver</span><span class="sxs-lookup"><span data-stu-id="3e9d3-877">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-p167">Cet attribut gérant plusieurs valeurs contient une liste de noms uniques répertoriant tous les serveurs web associés à ce pool.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-p167">This attribute is a multi-valued list of distinguished names. This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="3e9d3-880">Lien arrière : <strong>ID de lien 11029</strong></span><span class="sxs-lookup"><span data-stu-id="3e9d3-880">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="3e9d3-881">Le lien avant correspondant à ce lien arrière est <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-881">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-882">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-882">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-883">msRTCSIP-WMIInstanceId (obsolète)</span><span class="sxs-lookup"><span data-stu-id="3e9d3-883">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3e9d3-884">Nouveauté de Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-884">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="3e9d3-885">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-885">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-886">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="3e9d3-886">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-887">Cet attribut Active Directory existant est utilisé par la téléphonie pour spécifier la liste des autres adresses TCP/IP d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-887">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-888">Il s’agit d’une nouveauté du système d’exploitation Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="3e9d3-888">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-889">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="3e9d3-889">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-890">Cet attribut Active Directory existant est utilisé par les composants vocaux dans Lync Server, uniquement pour les objets contact, pour le routage des appels vers les numéros de standard automatique et d’accès abonné de la messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-890">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="3e9d3-891">L’adresse de transfert d’appel sans condition est stockée dans cet attribut à valeurs multiples.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-891">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="3e9d3-892">Ce compte est créé pour l’objectif spécifique du standard automatique et de l’accès abonné.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-892">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="3e9d3-893">Les attributs de ce compte ne doivent pas être modifiés par les administrateurs.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-893">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-894">Il s’agit d’une nouveauté du système d’exploitation Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-894">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e9d3-895">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="3e9d3-895">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-896">Cet attribut Active Directory existant qui gère plusieurs valeurs fait partie du schéma Active Directory de base introduit dans Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-896">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="3e9d3-897">Il contient les adresses électroniques X400, X500 et SMTP de la messagerie de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-897">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="3e9d3-898">Dans Live Communications Server 2003 et versions ultérieures, l’URI SIP de l’utilisateur est ajouté à cette liste &quot;à l'&quot; aide de la balise SIP :.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-898">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="3e9d3-899">Les applications suivantes utilisent cet attribut pour examiner l’URI SIP de l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="3e9d3-899">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e9d3-900">Client de messagerie et de collaboration Microsoft Office Outlook 2003</span><span class="sxs-lookup"><span data-stu-id="3e9d3-900">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="3e9d3-901">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="3e9d3-901">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3e9d3-902">Il s’agit d’une nouveauté du système d’exploitation Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-902">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e9d3-903">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="3e9d3-903">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-904">Cet attribut Active Directory existant contient le numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-904">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="3e9d3-905">Il s’agit d’une nouveauté du système d’exploitation Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="3e9d3-905">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

