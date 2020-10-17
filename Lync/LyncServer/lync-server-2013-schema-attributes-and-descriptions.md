---
title: 'Lync Server 2013 : attributs et descriptions de schéma'
description: 'Lync Server 2013 : attributs et descriptions de schéma.'
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
ms.openlocfilehash: 18888d20a772b3e84970e7d874bd6b6964affc75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557190"
---
# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a><span data-ttu-id="9d553-103">Attributs et descriptions de schéma dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d553-103">Schema attributes and descriptions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d553-104">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="9d553-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="9d553-105">Cette section décrit tous les attributs de schéma utilisés par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9d553-105">This section describes all the schema attributes used by Lync Server 2013.</span></span> <span data-ttu-id="9d553-106">Pour les classes associées aux attributs, consultez la rubrique [attributs de schéma par classe dans Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="9d553-106">For the classes associated with attributes, see [Schema attributes by class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).</span></span> <span data-ttu-id="9d553-107">Pour obtenir la liste des classes et des attributs qui sont nouveaux dans Lync Server 2013, consultez la rubrique [modifications de schéma dans Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="9d553-107">For a list of classes and attributes that are new in Lync Server 2013, see [Schema changes in Lync Server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).</span></span>

<span data-ttu-id="9d553-p102">Les attributs appartenant à des paires liées sont spécifiés en tant que liens avant ou liens arrière. Un attribut qui fait référence à un autre objet est un lien avant, tandis que l’attribut de l’objet cible qui fait référence au premier objet est un lien arrière. Les liens avant peuvent être mis à jour, contrairement aux liens arrière qui sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="9d553-p102">Attributes that are linked pairs are specified as forward links or back links. An attribute that refers to another object is a forward link; the attribute of the other object that refers back to the first object is a back link. Forward links are updatable, while back links are read-only.</span></span>

<span data-ttu-id="9d553-p103">Certains attributs ont une valeur masque de bits. Pour ces attributs, chaque paramètre est représenté par un bit et la valeur décimale affichée représente la position du bit. Les positions des bits commencent par le bit 0. 1 (binaire) correspond au bit 0 défini et 10000 (binaire) au bit 4 défini. Chaque bit représente une propriété. Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="9d553-p103">Some attributes have a bit-mask value. For these attributes, each setting is represented by a bit, and the displayed decimal value represents the bit position. Bit positions start with bit 0. For example, 1 (binary) is bit 0 set and 10000 (binary) is bit 4 set. Each bit represents a property. The following are some examples:</span></span>

  - <span data-ttu-id="9d553-117">10000 (binaire) a une valeur décimale de 16 (le bit 4 est défini).</span><span class="sxs-lookup"><span data-stu-id="9d553-117">10000 (binary) has a decimal value of 16 (that is, bit 4 is set).</span></span>

  - <span data-ttu-id="9d553-118">100000000 (binaire) a une valeur décimale de 256 (le bit 8 est défini).</span><span class="sxs-lookup"><span data-stu-id="9d553-118">100000000 (binary) has a decimal value of 256 (that is, bit 8 is set).</span></span>

  - <span data-ttu-id="9d553-119">1100 (binaire) a une valeur décimale de 12 (les bits 2 et 3 sont définis ; les propriétés représentées par les deux bits sont activées).</span><span class="sxs-lookup"><span data-stu-id="9d553-119">1100 (binary) has a decimal value of 12 (that is, bits 2 and 3 are set; properties represented by both bits are enabled).</span></span>

  - <span data-ttu-id="9d553-120">1111000001 (binaire) a une valeur décimale de 961 (les bits 0, 6, 7, 8 et 9 sont définis ; les propriétés pour chacun de ces bits sont activées).</span><span class="sxs-lookup"><span data-stu-id="9d553-120">1111000001 (binary) has a decimal value of 961 (that is, bits 0, 6, 7, 8, and 9 are set; properties for each of these bits are enabled).</span></span>

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a><span data-ttu-id="9d553-121">Attributs de schéma pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d553-121">Schema Attributes for Lync Server 2013</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d553-122">Attribut</span><span class="sxs-lookup"><span data-stu-id="9d553-122">Attribute</span></span></th>
<th><span data-ttu-id="9d553-123">Description</span><span class="sxs-lookup"><span data-stu-id="9d553-123">Description</span></span></th>
<th><span data-ttu-id="9d553-124">Comments</span><span class="sxs-lookup"><span data-stu-id="9d553-124">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d553-125">dnsHostName</span><span class="sxs-lookup"><span data-stu-id="9d553-125">dnsHostName</span></span></p></td>
<td><p><span data-ttu-id="9d553-126">Attribut existant dans les services de domaine Active Directory qui est désormais associé aux classes <strong>msRTCSIP-pool</strong> et <strong>msRTCSIP-MonitoringServer</strong> .</span><span class="sxs-lookup"><span data-stu-id="9d553-126">An existing attribute in Active Directory Domain Services that is now associated with the <strong>msRTCSIP-Pool</strong> and <strong>msRTCSIP-MonitoringServer</strong> classes.</span></span> <span data-ttu-id="9d553-127">Cet attribut spécifie le nom de domaine complet (FQDN) d’un pool ou d’un serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="9d553-127">This attribute specifies the fully qualified domain name (FQDN) of a pool or Monitoring Server.</span></span></p>
<p><span data-ttu-id="9d553-128">Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="9d553-128">A valid value for each segment is 63 characters; a valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="9d553-129">Nouveauté de Microsoft Office Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-129">New in Microsoft Office Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-130">msDS-SourceObjectDN</span><span class="sxs-lookup"><span data-stu-id="9d553-130">msDS-SourceObjectDN</span></span></p></td>
<td><p><span data-ttu-id="9d553-p105">Cet attribut contient la représentation sous forme de chaîne du nom unique (DN) de l’objet, situé dans une autre forêt, qui correspond à cet objet. Cet attribut est utilisé pour le développement des groupes de distribution et le standard automatique. Il est défini dans le schéma Active Directory par défaut de Windows Server 2003 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-p105">This attribute contains the string representation of the distinguished name (DN) of the object in another forest that corresponds to this object. This attribute is used for distribution group expansion and auto attendance. This attribute is defined in the default Active Directory schema for Windows Server 2003 R2.</span></span></p>
<p><span data-ttu-id="9d553-134">Pour éviter la nécessité d’une mise à niveau des services de domaine Active Directory vers Windows Server 2003 R2, la procédure de préparation du schéma Active Directory étend le schéma Windows Server 2003 à l’aide de cette définition d’attribut.</span><span class="sxs-lookup"><span data-stu-id="9d553-134">To avoid requiring an upgrade of AD DS to Windows Server 2003 R2, Active Directory schema preparation extends the Windows Server 2003 schema with this attribute definition.</span></span></p></td>
<td><p><span data-ttu-id="9d553-135">Nouveauté de Microsoft Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-135">New in Microsoft Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-136">msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="9d553-136">msExchUCVoiceMailSettings</span></span></p></td>
<td><p><span data-ttu-id="9d553-137">Cet attribut qui gère plusieurs valeurs contient les paramètres de messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="9d553-137">This multi-valued attribute holds voice mail settings.</span></span> <span data-ttu-id="9d553-138">Cet attribut est partagé avec la messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="9d553-138">This attribute is shared with Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="9d553-139">Nouveauté de Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-139">New in Microsoft Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-140">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="9d553-140">msExchUserHoldPolicies</span></span></p></td>
<td><p><span data-ttu-id="9d553-141">Cet attribut à valeurs multiples contient les stratégies d’archive qui s’appliquent à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d553-141">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="9d553-142">Les stratégies d’archive conservent les éléments de boîte aux lettres de l’utilisateur pendant la durée de la suspension.</span><span class="sxs-lookup"><span data-stu-id="9d553-142">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="9d553-143">Cet attribut est partagé avec Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="9d553-143">This attribute is shared with Exchange 2013.</span></span></p></td>
<td><p><span data-ttu-id="9d553-144">Nouveauté de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9d553-144">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-145">msRTCSIP-AcpInfo</span><span class="sxs-lookup"><span data-stu-id="9d553-145">msRTCSIP-AcpInfo</span></span></p></td>
<td><p><span data-ttu-id="9d553-146">Cet attribut stocke les informations sur les fournisseurs de services d’audioconférence pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d553-146">This attribute stores audio conferencing provider information for a user.</span></span></p></td>
<td><p><span data-ttu-id="9d553-147">Nouveauté de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-147">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-148">msRTCSIP-ApplicationDestination</span><span class="sxs-lookup"><span data-stu-id="9d553-148">msRTCSIP-ApplicationDestination</span></span></p></td>
<td><p><span data-ttu-id="9d553-149">Cet attribut pointe sur l’entrée de service approuvé pour le contact d’application.</span><span class="sxs-lookup"><span data-stu-id="9d553-149">This attribute points to the trusted service entry for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="9d553-150">Nouveauté de Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-150">New in Microsoft Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-151">msRTCSIP-ApplicationList</span><span class="sxs-lookup"><span data-stu-id="9d553-151">msRTCSIP-ApplicationList</span></span></p></td>
<td><p><span data-ttu-id="9d553-152">Cet attribut contient une liste des applications hébergées sur le serveur d’applications.</span><span class="sxs-lookup"><span data-stu-id="9d553-152">This attribute contains a list of hosted applications on the application server.</span></span></p></td>
<td><p><span data-ttu-id="9d553-153">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-153">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-154">msRTCSIP-ApplicationOptions</span><span class="sxs-lookup"><span data-stu-id="9d553-154">msRTCSIP-ApplicationOptions</span></span></p></td>
<td><p><span data-ttu-id="9d553-155">Cet attribut spécifie les options pour le contact d’application.</span><span class="sxs-lookup"><span data-stu-id="9d553-155">This attribute specifies the options for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="9d553-156">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-156">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-157">msRTCSIP-ApplicationPrimaryLanguage</span><span class="sxs-lookup"><span data-stu-id="9d553-157">msRTCSIP-ApplicationPrimaryLanguage</span></span></p></td>
<td><p><span data-ttu-id="9d553-158">Cet attribut contient la langue principale pour le contact d’application.</span><span class="sxs-lookup"><span data-stu-id="9d553-158">This attribute contains the primary language for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="9d553-159">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-159">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-160">msRTCSIP-ApplicationSecondaryLanguages</span><span class="sxs-lookup"><span data-stu-id="9d553-160">msRTCSIP-ApplicationSecondaryLanguages</span></span></p></td>
<td><p><span data-ttu-id="9d553-161">Cet attribut gérant plusieurs valeurs contient les langues secondaires pour le contact d’application.</span><span class="sxs-lookup"><span data-stu-id="9d553-161">This multiple value attribute contains the secondary languages for the application contact.</span></span></p></td>
<td><p><span data-ttu-id="9d553-162">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-162">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-163">msRTCSIP-ApplicationServerBL</span><span class="sxs-lookup"><span data-stu-id="9d553-163">msRTCSIP-ApplicationServerBL</span></span></p></td>
<td><p><span data-ttu-id="9d553-p108">Cet attribut contient une liste de serveurs d’applications appartenant à ce pool. Le lien avant correspondant à cet attribut de lien arrière est <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-p108">This attribute contains a list of application servers that belong to this pool. The corresponding forward link to this back link attribute is <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-166">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-166">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-167">msRTCSIP-ApplicationServerPoolLink</span><span class="sxs-lookup"><span data-stu-id="9d553-167">msRTCSIP-ApplicationServerPoolLink</span></span></p></td>
<td><p><span data-ttu-id="9d553-168">Cet attribut pointe vers le pool auquel appartient ce serveur d’applications.</span><span class="sxs-lookup"><span data-stu-id="9d553-168">This attribute points to the pool to which this application server belongs.</span></span> <span data-ttu-id="9d553-169">Il s’agit du lien avant.</span><span class="sxs-lookup"><span data-stu-id="9d553-169">This is the forward link.</span></span> <span data-ttu-id="9d553-170">Le lien arrière correspondant est <strong>msRTCSIP-ApplicationServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-170">The corresponding backward link is <strong>msRTCSIP-ApplicationServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-171">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-171">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-172">msRTCSIP-ArchiveDefault (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-172">msRTCSIP-ArchiveDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="9d553-173">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-173">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="9d553-174">Obsolète dans Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-174">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-175">msRTCSIP-ArchiveDefaultFlags (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-175">msRTCSIP-ArchiveDefaultFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p110">Cet attribut spécifie la valeur par défaut globale, dans les limites de la forêt, déterminant si les communications de tous les utilisateurs doivent être archivées ou non. Il est appliqué par la couche de l’agent d’archivage. Les valeurs prises en charge pour cet attribut sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d553-p110">This attribute specifies the global default within the forest boundary for archiving all user communications. This is enforced by the archiving agent layer. The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-179"><strong>TRUE</strong> : archiver tous les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9d553-179"><strong>TRUE</strong>: Archive all users</span></span></p></li>
<li><p><span data-ttu-id="9d553-180"><strong>FALSE</strong> : ne pas archiver tous les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="9d553-180"><strong>FALSE</strong>: Do not archive all users</span></span></p></li>
</ul>
<p><span data-ttu-id="9d553-181">Cet attribut permet de vérifier globalement, dans les limites de la forêt, le mode d’archivage des communications des utilisateurs d’un réseau interne.</span><span class="sxs-lookup"><span data-stu-id="9d553-181">This attribute globally controls, within the forest boundary, how user communications within an internal network are archived.</span></span></p>
<p><span data-ttu-id="9d553-182"><strong>Comportement de Live Communications Server 2005 (obsolète)</strong></span><span class="sxs-lookup"><span data-stu-id="9d553-182"><strong>Live Communications Server 2005 behavior (now retired)</strong></span></span></p>
<p><span data-ttu-id="9d553-183">Les valeurs prises en charge pour cet attribut sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d553-183">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-184">0 : archiver le corps du message [bit 0]</span><span class="sxs-lookup"><span data-stu-id="9d553-184">0: Archive the message body [bit 0]</span></span></p></li>
<li><p><span data-ttu-id="9d553-185">1 : ne pas archiver le corps du message [bit 0]</span><span class="sxs-lookup"><span data-stu-id="9d553-185">1: Do not archive the message body [bit 0]</span></span></p></li>
</ul>
<p><span data-ttu-id="9d553-186"><strong>Comportement d’Office Communications Server 2007</strong></span><span class="sxs-lookup"><span data-stu-id="9d553-186"><strong>Office Communications Server 2007 behavior</strong></span></span></p>
<p><span data-ttu-id="9d553-187">Les valeurs prises en charge pour cet attribut sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d553-187">The range of values for this attribute is as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-188">0 : ArchiveFederationDefaultWithoutBody (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-188">0: ArchiveFederationDefaultWithoutBody (retired)</span></span></p></li>
<li><p><span data-ttu-id="9d553-189">1-2 : ArchiveInternalCommunications</span><span class="sxs-lookup"><span data-stu-id="9d553-189">1-2: ArchiveInternalCommunications</span></span></p></li>
<li><p><span data-ttu-id="9d553-190">3-4 : ArchiveFederatedCommunications</span><span class="sxs-lookup"><span data-stu-id="9d553-190">3-4: ArchiveFederatedCommunications</span></span></p></li>
<li><p><span data-ttu-id="9d553-191">5 : RecordPresenceRegistrations</span><span class="sxs-lookup"><span data-stu-id="9d553-191">5: RecordPresenceRegistrations</span></span></p></li>
<li><p><span data-ttu-id="9d553-192">6 : RecordIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="9d553-192">6: RecordIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="9d553-193">7 : RecordGroupIMCallDetails</span><span class="sxs-lookup"><span data-stu-id="9d553-193">7: RecordGroupIMCallDetails</span></span></p></li>
<li><p><span data-ttu-id="9d553-194">8 : RecordFileTransferInstances</span><span class="sxs-lookup"><span data-stu-id="9d553-194">8: RecordFileTransferInstances</span></span></p></li>
<li><p><span data-ttu-id="9d553-195">9 : RecordAudioCallDetails</span><span class="sxs-lookup"><span data-stu-id="9d553-195">9: RecordAudioCallDetails</span></span></p></li>
<li><p><span data-ttu-id="9d553-196">10 : RecordVideoCallDetails</span><span class="sxs-lookup"><span data-stu-id="9d553-196">10: RecordVideoCallDetails</span></span></p></li>
<li><p><span data-ttu-id="9d553-197">11 : RecordRemoteAssistanceCallDetails</span><span class="sxs-lookup"><span data-stu-id="9d553-197">11: RecordRemoteAssistanceCallDetails</span></span></p></li>
<li><p><span data-ttu-id="9d553-198">12 : RecordApplicationSharingDetails</span><span class="sxs-lookup"><span data-stu-id="9d553-198">12: RecordApplicationSharingDetails</span></span></p></li>
<li><p><span data-ttu-id="9d553-199">13 : RecordMeetingInstantiations</span><span class="sxs-lookup"><span data-stu-id="9d553-199">13: RecordMeetingInstantiations</span></span></p></li>
<li><p><span data-ttu-id="9d553-200">14 : RecordMeetingJoins</span><span class="sxs-lookup"><span data-stu-id="9d553-200">14: RecordMeetingJoins</span></span></p></li>
<li><p><span data-ttu-id="9d553-201">15 : RecordDataJoins</span><span class="sxs-lookup"><span data-stu-id="9d553-201">15: RecordDataJoins</span></span></p></li>
<li><p><span data-ttu-id="9d553-202">16 : RecordAVJoins</span><span class="sxs-lookup"><span data-stu-id="9d553-202">16: RecordAVJoins</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9d553-203">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-203">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="9d553-204">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-204">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-205">msRTCSIP-ArchiveFederationDefault (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-205">msRTCSIP-ArchiveFederationDefault (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="9d553-206">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-206">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="9d553-207">Obsolète dans Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-207">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-208">msRTCSIP-ArchiveFederationDefaultFlags (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-208">msRTCSIP-ArchiveFederationDefaultFlags (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="9d553-209">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-209">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="9d553-210">Obsolète dans Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-210">Obsolete in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-211">msRTCSIP-ArchivingEnabled</span><span class="sxs-lookup"><span data-stu-id="9d553-211">msRTCSIP-ArchivingEnabled</span></span></p></td>
<td><p><span data-ttu-id="9d553-p111">Cet attribut est un entier utilisé comme champ bit pour contrôler si les communications d’un utilisateur sont archivées. Ce contrôle est appliqué par la couche de l’agent d’archivage. Il est identifié pour la réplication des catalogues globaux.</span><span class="sxs-lookup"><span data-stu-id="9d553-p111">This attribute is an integer used as a bit field to control whether a single user’s communications are to be archived. This control is enforced by the archiving agent layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="9d553-215">Cet attribut est spécifique à un utilisateur ou contact unique.</span><span class="sxs-lookup"><span data-stu-id="9d553-215">The scope of this attribute is specific to a single user or contact.</span></span> <span data-ttu-id="9d553-216">Les valeurs valides (et les positions de bits associées) dans Lync Server sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d553-216">The valid values (and associated bit positions) in Lync Server are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-217">0 : ne pas archiver (aucun bit défini)</span><span class="sxs-lookup"><span data-stu-id="9d553-217">0: Do not archive (no bit set)</span></span></p></li>
<li><p><span data-ttu-id="9d553-218">1 : obsolète (position de bit 0)</span><span class="sxs-lookup"><span data-stu-id="9d553-218">1: Retired (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="9d553-219">2 : obsolète (position de bit 1)</span><span class="sxs-lookup"><span data-stu-id="9d553-219">2: Retired (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="9d553-220">4 : archiver les communications internes (position de bit 2)</span><span class="sxs-lookup"><span data-stu-id="9d553-220">4: Archive internal communications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="9d553-221">8 : archiver les communications fédérées (position de bit 3)</span><span class="sxs-lookup"><span data-stu-id="9d553-221">8: Archive federated communications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="9d553-222">Les valeurs valides précédemment dans Live Communications Server 2005 sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d553-222">Previously valid values in Live Communications Server 2005 are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-223">0 : utiliser la valeur par défaut définie par <strong>msRTCSIP-ArchiveDefault</strong> et <strong>msRTCSIP-ArchiveFederation</strong> dans cet ordre de priorité :</span><span class="sxs-lookup"><span data-stu-id="9d553-223">0:Use the default value defined by <strong>msRTCSIP-ArchiveDefault</strong> and <strong>msRTCSIP-ArchiveFederation</strong> in this order of precedence:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-224">1 : archiver</span><span class="sxs-lookup"><span data-stu-id="9d553-224">1: Archive</span></span></p></li>
<li><p><span data-ttu-id="9d553-225">2 : ne pas archiver</span><span class="sxs-lookup"><span data-stu-id="9d553-225">2: Do not archive</span></span></p></li>
<li><p><span data-ttu-id="9d553-226">3 : archiver sans le corps du message</span><span class="sxs-lookup"><span data-stu-id="9d553-226">3: Archive without the message body</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="9d553-227">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-227">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-228">msRTCSIP-ArchivingServerData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-228">msRTCSIP-ArchivingServerData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-229">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-229">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="9d553-230">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-230">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-231">msRTCSIP-ArchivingServerVersion (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-231">msRTCSIP-ArchivingServerVersion (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p113">Cet attribut définit la version du service d’archivage. C’est un entier qui augmente de façon monotone et est incrémenté à chaque version officielle du produit. Les valeurs prises en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d553-p113">This attribute defines the version of the Archiving service. This attribute is a monotonously increasing integer type that increments with each official product release. The possible valid values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-235">Non défini : Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="9d553-235">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="9d553-236">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="9d553-236">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="9d553-237">                 Live Communications Server 2005 avec SP1</span><span class="sxs-lookup"><span data-stu-id="9d553-237">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="9d553-238">3 : Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="9d553-238">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="9d553-239">4 : Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9d553-239">4: Office Communications Server 2007 R2</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9d553-240">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-240">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-241">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-241">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-242">msRTCSIP-BackEndServer</span><span class="sxs-lookup"><span data-stu-id="9d553-242">msRTCSIP-BackEndServer</span></span></p></td>
<td><p><span data-ttu-id="9d553-p114">Cet attribut indique le nom de domaine complet du serveur principal du pool. Étant donné qu’il ne peut exister qu’un serveur principal par pool, il s’agit d’un attribut à valeur unique.</span><span class="sxs-lookup"><span data-stu-id="9d553-p114">This attribute specifies the FQDN of the Back End Server of the pool. Because there can only be a single Back End Server per pool, this is a single-valued attribute.</span></span></p>
<p><span data-ttu-id="9d553-245">Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="9d553-245">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="9d553-246">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-246">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-247">msRTCSIP-ConferenceDirectoryHomePool</span><span class="sxs-lookup"><span data-stu-id="9d553-247">msRTCSIP-ConferenceDirectoryHomePool</span></span></p></td>
<td><p><span data-ttu-id="9d553-248">Cet attribut contient l’identificateur du pool qui héberge l’annuaire de conférences.</span><span class="sxs-lookup"><span data-stu-id="9d553-248">This attribute contains the identifier of the pool that hosts the conference directory.</span></span></p></td>
<td><p><span data-ttu-id="9d553-249">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-249">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-250">msRTCSIP-ConferenceDirectoryId</span><span class="sxs-lookup"><span data-stu-id="9d553-250">msRTCSIP-ConferenceDirectoryId</span></span></p></td>
<td><p><span data-ttu-id="9d553-251">Cet attribut contient l’identificateur d’un annuaire de conférences.</span><span class="sxs-lookup"><span data-stu-id="9d553-251">This attribute contains the identifier of a conference directory.</span></span></p></td>
<td><p><span data-ttu-id="9d553-252">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-252">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-253">msRTCSIP-ConferenceDirectoryTargetPool</span><span class="sxs-lookup"><span data-stu-id="9d553-253">msRTCSIP-ConferenceDirectoryTargetPool</span></span></p></td>
<td><p><span data-ttu-id="9d553-254">Cet attribut contient l’identificateur du pool vers lequel l’annuaire de conférences est déplacé.</span><span class="sxs-lookup"><span data-stu-id="9d553-254">This attribute contains the identifier of the pool to which the conference directory is being moved.</span></span></p></td>
<td><p><span data-ttu-id="9d553-255">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-255">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-256">msRTCSIP-default</span><span class="sxs-lookup"><span data-stu-id="9d553-256">msRTCSIP-Default</span></span></p></td>
<td><p><span data-ttu-id="9d553-257">Cet attribut booléen définit si l’utilisation téléphonique est une utilisation par défaut.</span><span class="sxs-lookup"><span data-stu-id="9d553-257">This Boolean attribute defines whether the phone usage is a default usage.</span></span> <span data-ttu-id="9d553-258">Si la valeur est <strong>TRUE</strong>, l’utilisation téléphonique est une utilisation par défaut et ne peut pas être supprimée par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="9d553-258">If this attribute is set to <strong>TRUE</strong>, the phone usage is a default usage and cannot be deleted by the administrator.</span></span> <span data-ttu-id="9d553-259">Si la valeur est <strong>FALSE</strong>, l’utilisation peut être supprimée.</span><span class="sxs-lookup"><span data-stu-id="9d553-259">If this attribute is set to <strong>FALSE</strong>, the usage can be deleted.</span></span></p></td>
<td><p><span data-ttu-id="9d553-260">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-260">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-261">msRTCSIP-DefaultCWAExternalURL</span><span class="sxs-lookup"><span data-stu-id="9d553-261">msRTCSIP-DefaultCWAExternalURL</span></span></p></td>
<td><p><span data-ttu-id="9d553-262">Cet attribut identifie l’URL d’Office Communicator Web Access pour les utilisateurs qui se trouvent à l’extérieur de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="9d553-262">This attribute identifies the Communicator Web Access URL for users who are outside the organization.</span></span></p></td>
<td><p><span data-ttu-id="9d553-263">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-263">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-264">msRTCSIP-DefaultCWAInternalURL</span><span class="sxs-lookup"><span data-stu-id="9d553-264">msRTCSIP-DefaultCWAInternalURL</span></span></p></td>
<td><p><span data-ttu-id="9d553-265">Cet attribut identifie l’URL d’Office Communicator Web Access pour les utilisateurs qui se trouvent à l’intérieur de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="9d553-265">This attribute identifies the Communicator Web Access URL for users who are inside the organization.</span></span></p></td>
<td><p><span data-ttu-id="9d553-266">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-266">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-267">msRTCSIP-DefaultLocationProfileLink (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-267">msRTCSIP-DefaultLocationProfileLink (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-268">Cet attribut à valeur unique contient le nom unique (DN) d’un objet de classe de profil d’emplacement qui lui est affecté.</span><span class="sxs-lookup"><span data-stu-id="9d553-268">This single-valued attribute contains the distinguished name (DN) of a location profile class object assigned to it.</span></span></p>
<p><span data-ttu-id="9d553-269">Lien avant : <strong>ID de lien 11036</strong></span><span class="sxs-lookup"><span data-stu-id="9d553-269">Forward link: <strong>Link ID 11036</strong></span></span></p>
<p><span data-ttu-id="9d553-270">Le lien arrière correspondant est <strong>msRTCSIP-ServerReferenceBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-270">The corresponding backward link is <strong>msRTCSIP-ServerReferenceBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-271">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-271">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-272">msRTCSIP-DefaultPolicy (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-272">msRTCSIP-DefaultPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-273">Cet attribut booléen indique si la stratégie est une stratégie par défaut.</span><span class="sxs-lookup"><span data-stu-id="9d553-273">This Boolean attribute specifies whether the policy is a default policy.</span></span> <span data-ttu-id="9d553-274">C’est le cas lorsque l’attribut a la valeur <strong>TRUE</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-274">The policy is a default policy when set to <strong>TRUE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-275">Nouveauté d’Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="9d553-275">New in Office Communications Server 2007</span></span></p>
<p><span data-ttu-id="9d553-276">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-276">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-277">msRTCSIP-DefaultRouteToEdgeProxy (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-277">msRTCSIP-DefaultRouteToEdgeProxy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-278">Cet attribut spécifie le nom de domaine complet (FQDN) du serveur Edge exécutant le service Edge d’accès, s’il est accessible directement, ou du programme d’équilibrage de la charge matérielle pour un pool de serveurs exécutant le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="9d553-278">This attribute specifies the FQDN of either the Edge Server running the Access Edge service, if it can be accessed directly, or of the hardware load balancer for a pool of servers running Access Edge service.</span></span> <span data-ttu-id="9d553-279">Si les serveurs exécutant le service Edge d’accès sont accessibles uniquement par le biais d’un ou de plusieurs directeurs, cet attribut spécifie le nom de domaine complet (FQDN) et éventuellement le numéro de port du directeur ou du programme d’équilibrage de la charge matérielle servant de pool directeur.</span><span class="sxs-lookup"><span data-stu-id="9d553-279">If the servers running Access Edge service can be accessed only through one or more Directors, this attribute specifies the FQDN and, optionally, the port number of the Director or of the hardware load balancer serving a Director pool.</span></span></p>
<p><span data-ttu-id="9d553-280">Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="9d553-280">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="9d553-281">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-281">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="9d553-282">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-282">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-283">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-283">msRTCSIP-DefaultRouteToEdgeProxyPort (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-284">Cet attribut représente le numéro de port qui doit être utilisé pour se connecter au serveur exécutant le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="9d553-284">This attribute represents the port number that should be used to connect to the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="9d553-285">La valeur correcte est un nombre entier spécifiant le port à utiliser.</span><span class="sxs-lookup"><span data-stu-id="9d553-285">The valid value is an integer value specifying the port to be used.</span></span> <span data-ttu-id="9d553-286">La valeur par défaut est 5061.</span><span class="sxs-lookup"><span data-stu-id="9d553-286">The default value is 5061.</span></span></p></td>
<td><p><span data-ttu-id="9d553-287">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-287">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="9d553-288">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-288">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-289">msRTCSIP-DefPresenceSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-289">msRTCSIP-DefPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-290">Cet attribut représente le délai d’expiration par défaut de l’abonnement aux informations de présence.</span><span class="sxs-lookup"><span data-stu-id="9d553-290">This attribute represents the default presence subscription time-out period.</span></span></p></td>
<td><p><span data-ttu-id="9d553-291">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-291">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-292">msRTCSIP-DefRegistrationTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-292">msRTCSIP-DefRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-293">Cet attribut représente le délai d’expiration d’inscription par défaut.</span><span class="sxs-lookup"><span data-stu-id="9d553-293">This attribute represents the default registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="9d553-294">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-294">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-295">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-295">msRTCSIP-DefRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-296">Cet attribut représente le délai d’expiration par défaut de l’abonnement aux données d’itinérance.</span><span class="sxs-lookup"><span data-stu-id="9d553-296">This attribute represents the default roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="9d553-297">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-297">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-298">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="9d553-298">msRTCSIP-DeploymentLocator</span></span></p></td>
<td><p><span data-ttu-id="9d553-299">Cet attribut est utilisé dans une topologie de domaine fractionné et contient un nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="9d553-299">This attribute is used in a split domain topology and contains a fully qualified domain name (FQDN).</span></span></p></td>
<td><p><span data-ttu-id="9d553-300">Nouveauté de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-300">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-301">msRTCSIP-Description (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-301">msRTCSIP-Description (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-302">Cet attribut de type chaîne UNICODE à valeur unique contient une description conviviale de cet itinéraire téléphonique ou de cette règle de normalisation.</span><span class="sxs-lookup"><span data-stu-id="9d553-302">This single-valued UNICODE string attribute contains a friendly description of this phone route or normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="9d553-303">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-303">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-304">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-304">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-305">msRTCSIP-DomainData</span><span class="sxs-lookup"><span data-stu-id="9d553-305">msRTCSIP-DomainData</span></span></p></td>
<td><p><span data-ttu-id="9d553-306">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-306">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-307">msRTCSIP-DomainName</span><span class="sxs-lookup"><span data-stu-id="9d553-307">msRTCSIP-DomainName</span></span></p></td>
<td><p><span data-ttu-id="9d553-308">Cet attribut représente un domaine configuré pour le serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="9d553-308">This attribute represents a domain configured for the Registrar.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-309">msRTCSIP-EdgeProxyData</span><span class="sxs-lookup"><span data-stu-id="9d553-309">msRTCSIP-EdgeProxyData</span></span></p></td>
<td><p><span data-ttu-id="9d553-310">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-310">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="9d553-311">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-311">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-312">msRTCSIP-EdgeProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="9d553-312">msRTCSIP-EdgeProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="9d553-313">Cet attribut indique le nom de domaine complet du serveur exécutant le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="9d553-313">This attribute specifies the FQDN of the server running Access Edge service.</span></span></p>
<p><span data-ttu-id="9d553-314">Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="9d553-314">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="9d553-315">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-315">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-316">msRTCSIP-EnableBestEffortNotify (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-316">msRTCSIP-EnableBestEffortNotify (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p119">Cet attribut détermine si un serveur génère une demande BENOTIFY (Best Effort NOTIFY), plutôt qu’une demande NOTIFY, en réponse à la demande SUBSCRIBE envoyée par un client. BENOTIFY est une extension d’amélioration des performances du protocole de transfert de notification de l’inscription dans laquelle le serveur génère des demandes BENOTIFY, plutôt que des demandes NOTIFY normales. Les performances sont améliorées dans la mesure où une demande BENOTIFY ne nécessite pas de réponse 200 OK d’un client, contrairement à la demande NOTIFY.</span><span class="sxs-lookup"><span data-stu-id="9d553-p119">This attribute controls whether a server generates a Best Effort NOTIFY (BENOTIFY) request, instead of a NOTIFY request, in response to a SUBSCRIBE request from a client. BENOTIFY is a performance-enhancing extension to the subscribe notification handshake where the server generates BENOTIFY requests, instead of regular NOTIFY requests. The performance benefit is that a BENOTIFY request does not require a 200 OK response from the client as the NOTIFY request does.</span></span></p>
<p><span data-ttu-id="9d553-320">La valeur correcte est <strong>TRUE</strong> ou <strong>FALSE</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-320">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="9d553-321">Live Communications Server 2003 ne prend pas en charge les demandes BENOTIFY.</span><span class="sxs-lookup"><span data-stu-id="9d553-321">Live Communications Server 2003 does not support BENOTIFY requests.</span></span> <span data-ttu-id="9d553-322">Pour interagir avec les applications serveur écrites avec l’API serveur de Live Communications Server 2003 exécutée sur Live Communications Server 2005 et les serveurs tiers, les demandes BENOTIFY peuvent être désactivées en définissant sa valeur sur <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9d553-322">To interoperate with server applications written with the Live Communications Server 2003 server API running on Live Communications Server 2005 and third-party servers, BENOTIFY requests can be disabled by setting its value to <STRONG>FALSE</STRONG>.</span></span> <span data-ttu-id="9d553-323">Actuellement, cette fonction ne fait pas partie du processus de standardisation SIP IETF (Internet Engineering Task Force).</span><span class="sxs-lookup"><span data-stu-id="9d553-323">BENOTIFY is not currently part of the IETF (Internet Engineering Task Force) SIP standardization process.</span></span>


</div></td>
<td><p><span data-ttu-id="9d553-324">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-324">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="9d553-325">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-325">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-326">msRTCSIP-EnableFederation (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-326">msRTCSIP-EnableFederation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p121">Cet attribut est un commutateur global utilisé par les administrateurs informatiques pour déterminer si les utilisateurs sont autorisés ou non à communiquer avec ceux d’autres organisations. Il permet à un administrateur de remplacer l’attribut <strong>FederationEnabled</strong> d’un utilisateur. Cet attribut peut être utile pour protéger le réseau interne contre les attaques en provenance d’Internet pouvant être causées par des vers ou des virus, ou encore contre les attaques ciblées contre la société.</span><span class="sxs-lookup"><span data-stu-id="9d553-p121">This attribute is a global switch that IT administrators use to configure whether users are allowed to communicate with users from other organizations. It enables an administrator to overwrite an individual user’s <strong>FederationEnabled</strong> attribute. This attribute can be useful to help protect the internal network from Internet attacks that may be caused by worms, viruses, or targeted attacks on the company.</span></span></p>
<p><span data-ttu-id="9d553-330">Les valeurs (et les positions des bits associées) prises en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d553-330">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-331">1 : activé pour la solution PIC (position de bit 0)</span><span class="sxs-lookup"><span data-stu-id="9d553-331">1: Enabled for public IM connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="9d553-332">2 : réservé (position de bit 1)</span><span class="sxs-lookup"><span data-stu-id="9d553-332">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="9d553-333">4 : réservé (position de bit 2)</span><span class="sxs-lookup"><span data-stu-id="9d553-333">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="9d553-334">8 : réservé (position de bit 3)</span><span class="sxs-lookup"><span data-stu-id="9d553-334">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="9d553-335">16 : Contrôle d’appel distant activé [Téléphonie] (position de bit 4)</span><span class="sxs-lookup"><span data-stu-id="9d553-335">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="9d553-336">64 : AllowOrganizeMeetingWithAnonymousParticipants (permet d’inviter des utilisateurs anonymes à des réunions) (position de bit 6)</span><span class="sxs-lookup"><span data-stu-id="9d553-336">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="9d553-337">128 : UCEnabled (active les utilisateurs pour les communications unifiées) (position de bit 7)</span><span class="sxs-lookup"><span data-stu-id="9d553-337">128: UCEnabled (enable users for unified communications) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="9d553-338">256 : EnabledForEnhancedPresence (active l’utilisateur pour la solution PIC) (position de bit 8)</span><span class="sxs-lookup"><span data-stu-id="9d553-338">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="9d553-339">512 : RemoteCallControlDualMode (position de bit 9)</span><span class="sxs-lookup"><span data-stu-id="9d553-339">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9d553-340">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-340">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="9d553-341">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-341">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-342">msRTCSIP-EnterpriseServices</span><span class="sxs-lookup"><span data-stu-id="9d553-342">msRTCSIP-EnterpriseServices</span></span></p></td>
<td><p><span data-ttu-id="9d553-343">Cet attribut indique si les services d’entreprise sont chargés sur un serveur donné.</span><span class="sxs-lookup"><span data-stu-id="9d553-343">This attribute indicates whether the Enterprise Services are loaded on the given server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-344">msRTCSIP-ExtensionData</span><span class="sxs-lookup"><span data-stu-id="9d553-344">msRTCSIP-ExtensionData</span></span></p></td>
<td><p><span data-ttu-id="9d553-345">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-345">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-346">msRTCSIP-ExternalAccessCode</span><span class="sxs-lookup"><span data-stu-id="9d553-346">msRTCSIP-ExternalAccessCode</span></span></p></td>
<td><p><span data-ttu-id="9d553-347">Cet attribut contient l’indicatif pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="9d553-347">This attribute contains the dial code for external access.</span></span></p></td>
<td><p><span data-ttu-id="9d553-348">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-348">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-349">msRTCSIP-FederationEnabled</span><span class="sxs-lookup"><span data-stu-id="9d553-349">msRTCSIP-FederationEnabled</span></span></p></td>
<td><p><span data-ttu-id="9d553-p122">Cet attribut permet de contrôler si un utilisateur unique est activé pour la fédération. Il est appliqué par la couche Services d’entreprise. Il est identifié pour la réplication des catalogues globaux.</span><span class="sxs-lookup"><span data-stu-id="9d553-p122">This attribute controls whether a single user is enabled for federation. It is enforced by the Enterprise Services layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="9d553-353">La valeur correcte est <strong>TRUE</strong> ou <strong>FALSE</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-353">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-354">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-354">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-355">msRTCSIP-FrontEndServers</span><span class="sxs-lookup"><span data-stu-id="9d553-355">msRTCSIP-FrontEndServers</span></span></p></td>
<td><p><span data-ttu-id="9d553-356">Cet attribut gérant plusieurs valeurs contient les noms de domaines de tous les serveurs Enterprise Edition associés à un pool.</span><span class="sxs-lookup"><span data-stu-id="9d553-356">This attribute is a multi-valued list of the domain names of all Enterprise Edition servers associated with a pool.</span></span></p>
<p><span data-ttu-id="9d553-357">Lien arrière : <strong>ID de lien 11023</strong></span><span class="sxs-lookup"><span data-stu-id="9d553-357">Back link: <strong>Link ID 11023</strong></span></span></p>
<p><span data-ttu-id="9d553-358">Le lien avant correspondant à ce lien arrière est <strong>msRTCSIP-PoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-358">The corresponding forward link to this back link is <strong>msRTCSIP-PoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-359">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-359">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-360">msRTCSIP-Gateways (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-360">msRTCSIP-Gateways (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-361">Cet attribut de type chaîne gérant plusieurs valeurs contient une liste de passerelles et de ports (par passerelle).</span><span class="sxs-lookup"><span data-stu-id="9d553-361">This multi-valued string attribute contains a list of gateways and ports (per gateway).</span></span></p></td>
<td><p><span data-ttu-id="9d553-362">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-362">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-363">msRTCSIP-GlobalSettingsData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-363">msRTCSIP-GlobalSettingsData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p123">Cet attribut permet de stocker les paires nom:valeur. La paire nom:valeur déjà définie correspond au paramètre <strong>autoriser l’interrogation de présence</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-p123">This attribute stores name:value pairs. The already-defined name:value pair is for the <strong>allow polling for presence</strong> setting.</span></span></p></td>
<td><p><span data-ttu-id="9d553-366">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-366">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-367">msRTCSIP-GroupingID</span><span class="sxs-lookup"><span data-stu-id="9d553-367">msRTCSIP-GroupingID</span></span></p></td>
<td><p><span data-ttu-id="9d553-368">Cet attribut est un identificateur unique d’un groupe utilisé pour regrouper les entrées de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="9d553-368">This attribute is a unique identifier of a group that is used to group address book entries.</span></span></p></td>
<td><p><span data-ttu-id="9d553-369">Nouveauté de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-369">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-370">msRTCSIP-HomeServer (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-370">msRTCSIP-HomeServer (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="9d553-371">Nouveauté de Live Communications Server 2003 (non utilisé).</span><span class="sxs-lookup"><span data-stu-id="9d553-371">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="9d553-372">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-372">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-373">msRTCSIP-HomeServerString (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-373">msRTCSIP-HomeServerString (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="9d553-374">Nouveauté de Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="9d553-374">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="9d553-375">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-375">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-376">msRTCSIP-HomeUsers (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-376">msRTCSIP-HomeUsers (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="9d553-377">Nouveauté de Live Communications Server 2003 (non utilisé).</span><span class="sxs-lookup"><span data-stu-id="9d553-377">New in Live Communications Server 2003 (not used).</span></span></p>
<p><span data-ttu-id="9d553-378">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-378">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-379">msRTCSIP-InternetAccessEnabled</span><span class="sxs-lookup"><span data-stu-id="9d553-379">msRTCSIP-InternetAccessEnabled</span></span></p></td>
<td><p><span data-ttu-id="9d553-p124">Cet attribut permet de contrôler si un utilisateur unique est activé pour l’accès des utilisateurs extérieurs. Il est appliqué par la couche Services d’entreprise. Il est identifié pour la réplication des catalogues globaux.</span><span class="sxs-lookup"><span data-stu-id="9d553-p124">This attribute controls whether a single user is enabled for outside user access. It is enforced by the Enterprise Services layer. It is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="9d553-383">La valeur correcte est <strong>TRUE</strong> ou <strong>FALSE</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-383">The valid values are <strong>TRUE</strong> or <strong>FALSE</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-384">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-384">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-385">msRTCSIP-IsMaster (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-385">msRTCSIP-IsMaster (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="9d553-386">Nouveauté de Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="9d553-386">New in Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="9d553-387">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-387">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-388">msRTCSIP-Line</span><span class="sxs-lookup"><span data-stu-id="9d553-388">msRTCSIP-Line</span></span></p></td>
<td><p><span data-ttu-id="9d553-389">Cet attribut à valeur unique contient l’ID de périphérique (l’URI SIP ou l’URI TEL du téléphone que les contrôles utilisateur) utilisent dans Lync pour la téléphonie.</span><span class="sxs-lookup"><span data-stu-id="9d553-389">This single-valued attribute contains the device ID (either the SIP URI or the TEL URI of the phone the user controls) used by Lync for telephony.</span></span> <span data-ttu-id="9d553-390">Il est identifié pour la réplication des catalogues globaux et est indexé.</span><span class="sxs-lookup"><span data-stu-id="9d553-390">This attribute is marked for Global Catalog replication and is indexed.</span></span> <span data-ttu-id="9d553-391">Si un utilisateur est activé pour Voix Entreprise, cet attribut stocke la version normalisée E.164 du numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d553-391">If a user is enabled for Enterprise Voice, this attribute stores the E.164 normalized version of the user’s phone number.</span></span></p></td>
<td><p><span data-ttu-id="9d553-392">Nouveauté de Microsoft Office Live Communications Server 2005 avec SP1</span><span class="sxs-lookup"><span data-stu-id="9d553-392">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-393">msRTCSIP-LineServer</span><span class="sxs-lookup"><span data-stu-id="9d553-393">msRTCSIP-LineServer</span></span></p></td>
<td><p><span data-ttu-id="9d553-p126">Cet attribut à valeur unique contient l’URI SIP du serveur de passerelle CSTA-SIP. Il est identifié pour la réplication des catalogues globaux mais n’est pas indexé.</span><span class="sxs-lookup"><span data-stu-id="9d553-p126">This single-valued attribute contains the SIP URI of the CSTA-SIP gateway server. This attribute is marked for Global Catalog replication but is not indexed.</span></span></p></td>
<td><p><span data-ttu-id="9d553-396">Nouveauté de Microsoft Office Live Communications Server 2005 avec SP1</span><span class="sxs-lookup"><span data-stu-id="9d553-396">New in Microsoft Office Live Communications Server 2005 with SP1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-397">msRTCSIP-LocalNormalizationData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-397">msRTCSIP-LocalNormalizationData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-398">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-398">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="9d553-399">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-399">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-400">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-400">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-401">msRTCSIP-LocalNormalizationLinks (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-401">msRTCSIP-LocalNormalizationLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p127">Cet attribut gérant plusieurs valeurs contient la liste des noms uniques (DN) des règles de normalisation locales associés à ce profil d’emplacement. Ce type d’attribut est un attribut binaire de nom unique. Il existe une relation un à plusieurs entre le profil d’emplacement et les règles de normalisation locales. L’ordre des noms uniques des règles de normalisation locales doit correspondre à l’ordre défini par l’administrateur. La conservation de cet ordre est assurée par la partie binaire de l’attribut binaire de nom unique, qui définit l’index de classement.</span><span class="sxs-lookup"><span data-stu-id="9d553-p127">This multi-valued attribute contains a list of local normalization distinguished names (DN) associated with this location profile. The type of this attribute is a DN binary. There is a one-to-many relationship between location profile and local normalization rules. The ordering of the list of local normalization DNs must be maintained in the order specified by the administrator. The preservation of order is maintained by the binary portion of the DN binary, which specifies the order index.</span></span></p>
<p><span data-ttu-id="9d553-407">Lien avant : <strong>ID de lien 11034</strong></span><span class="sxs-lookup"><span data-stu-id="9d553-407">Forward link: <strong>Link ID 11034</strong></span></span></p>
<p><span data-ttu-id="9d553-408">Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-LocationProfileBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-408">The corresponding back link to this forward link attribute is <strong>msRTCSIP-LocationProfileBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-409">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-409">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-410">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-410">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-411">msRTCSIP-LocalNormalizationOptions</span><span class="sxs-lookup"><span data-stu-id="9d553-411">msRTCSIP-LocalNormalizationOptions</span></span></p></td>
<td><p><span data-ttu-id="9d553-412">Cet attribut contient une liste d’options pour la règle de normalisation.</span><span class="sxs-lookup"><span data-stu-id="9d553-412">This attribute contains a list of options for the normalization rule.</span></span></p></td>
<td><p><span data-ttu-id="9d553-413">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-413">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-414">msRTCSIP-LocationName (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-414">msRTCSIP-LocationName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p128">Cet attribut à valeur unique contient le nom convivial du profil d’emplacement qui indique l’emplacement représenté par le profil. Comme il peut exister plusieurs profils d’emplacement, l’administrateur doit être en mesure de les distinguer.</span><span class="sxs-lookup"><span data-stu-id="9d553-p128">This single-valued attribute contains a friendly name for the location profile that indicates which location this profile represents. Because there can be multiple location profiles, the administrator needs a way to distinguish between different profiles.</span></span></p></td>
<td><p><span data-ttu-id="9d553-417">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-417">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-418">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-418">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-419">msRTCSIP-locationProfileBL (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-419">msRTCSIP-locationProfileBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p129">Cet attribut gérant plusieurs valeurs contient la liste des noms uniques de profil d’emplacement. Il indique le lien arrière d’un ou plusieurs profils d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="9d553-p129">This multi-valued attribute contains a list of location profile distinguished names. This attribute specifies the back link to one or more location profiles.</span></span></p>
<p><span data-ttu-id="9d553-422">Lien arrière : <strong>ID de lien 11035</strong></span><span class="sxs-lookup"><span data-stu-id="9d553-422">Back link: <strong>Link ID 11035</strong></span></span></p>
<p><span data-ttu-id="9d553-423">Cet attribut correspond au lien avant <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-423">This attribute corresponds to the forward link <strong>msRTCSIP-LocalNormalizationLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-424">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-424">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-425">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-425">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-426">msRTCSIP-LocationProfileData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-426">msRTCSIP-LocationProfileData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-427">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-427">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="9d553-428">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-428">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-429">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-429">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-430">msRTCSIP-LocationProfileOptions</span><span class="sxs-lookup"><span data-stu-id="9d553-430">msRTCSIP-LocationProfileOptions</span></span></p></td>
<td><p><span data-ttu-id="9d553-431">Cet attribut contient les options pour le profil d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="9d553-431">This attribute contains the options for the location profile.</span></span></p></td>
<td><p><span data-ttu-id="9d553-432">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-432">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-433">msRTCSIP-MappingContact</span><span class="sxs-lookup"><span data-stu-id="9d553-433">msRTCSIP-MappingContact</span></span></p></td>
<td><p><span data-ttu-id="9d553-434">Cet attribut gérant plusieurs valeurs contient une liste de contacts d’application.</span><span class="sxs-lookup"><span data-stu-id="9d553-434">This multiple-value attribute holds a list of application contacts.</span></span></p></td>
<td><p><span data-ttu-id="9d553-435">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-435">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-436">msRTCSIP-MappingLocation</span><span class="sxs-lookup"><span data-stu-id="9d553-436">msRTCSIP-MappingLocation</span></span></p></td>
<td><p><span data-ttu-id="9d553-437">Cet attribut gérant plusieurs valeurs contient une liste de profils d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="9d553-437">This multiple-value attribute holds a list of location profiles.</span></span></p></td>
<td><p><span data-ttu-id="9d553-438">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-438">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-439">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-439">msRTCSIP-MaxNumOutstandingSearchPerServer (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-440">Cet attribut représente le nombre maximal de demandes de recherches actives par serveur.</span><span class="sxs-lookup"><span data-stu-id="9d553-440">This attribute represents the maximum number of outstanding search requests per server.</span></span></p></td>
<td><p><span data-ttu-id="9d553-441">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-441">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-442">msRTCSIP-MaxNumSubscriptionsPerUser (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-442">msRTCSIP-MaxNumSubscriptionsPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-443">Cet attribut représente le nombre maximal d’abonnements par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d553-443">The attribute represents the maximum number of subscriptions per user.</span></span></p></td>
<td><p><span data-ttu-id="9d553-444">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-444">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-445">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-445">msRTCSIP-MaxPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-446">Cet attribut représente le délai d’expiration maximal d’abonnement.</span><span class="sxs-lookup"><span data-stu-id="9d553-446">This attribute represents the maximum subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="9d553-447">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-447">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-448">msRTCSIP-MaxRegistrationsTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-448">msRTCSIP-MaxRegistrationsTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-449">Cet attribut représente le délai d’expiration maximal d’inscription.</span><span class="sxs-lookup"><span data-stu-id="9d553-449">This attribute represents the maximum registrations time-out window.</span></span></p></td>
<td><p><span data-ttu-id="9d553-450">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-450">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-451">msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-452">Cet attribut représente le délai d’expiration maximal d’abonnement aux données d’itinérance.</span><span class="sxs-lookup"><span data-stu-id="9d553-452">This attribute represents the maximum roaming data subscriptions time-out window.</span></span></p></td>
<td><p><span data-ttu-id="9d553-453">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-453">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-454">msRTCSIP-MCUData</span><span class="sxs-lookup"><span data-stu-id="9d553-454">msRTCSIP-MCUData</span></span></p></td>
<td><p><span data-ttu-id="9d553-455">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-455">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="9d553-456">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-456">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-457">msRTCSIP-MCUFactoryAddress</span><span class="sxs-lookup"><span data-stu-id="9d553-457">msRTCSIP-MCUFactoryAddress</span></span></p></td>
<td><p><span data-ttu-id="9d553-p130">Cet attribut est un attribut de point de contrôle du service sous la classe d’ordinateur qui définit un lien renvoyant à son répartiteur d’unité de contrôle multipoint (MCU) parent. Le point de contrôle du service et l’attribut sont créés pour chaque MCU Microsoft. Chaque MCU Microsoft doit trouver le serveur principal du pool auquel il appartient afin d’en extraire des paramètres de niveau pool.</span><span class="sxs-lookup"><span data-stu-id="9d553-p130">This attribute is a service control point attribute under the computer class that specifies a link back to the multipoint control unit (MCU) Factory to which it belongs. This service control point and attribute is created for every Microsoft MCU. Each Microsoft MCU must find the Back End Server of the pool to which it belongs, in order to retrieve pool-level settings from it.</span></span></p>
<p><span data-ttu-id="9d553-p131">La valeur de cet attribut est le nom unique (DN) du répartiteur de MCU. Il s’agit d’un attribut à valeur unique identifié pour la réplication des catalogues globaux.</span><span class="sxs-lookup"><span data-stu-id="9d553-p131">The value of this attribute is the distinguished name (DN) of the MCU Factory. This is a single-valued attribute and marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="9d553-463">Lien avant : <strong>ID de lien 11026</strong></span><span class="sxs-lookup"><span data-stu-id="9d553-463">Forward link: <strong>Link ID 11026</strong></span></span></p>
<p><span data-ttu-id="9d553-464">Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-MCUServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-464">The corresponding back link to this forward link attribute is <strong>msRTCSIP-MCUServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-465">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-465">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-466">msRTCSIP-MCUFactoryData</span><span class="sxs-lookup"><span data-stu-id="9d553-466">msRTCSIP-MCUFactoryData</span></span></p></td>
<td><p><span data-ttu-id="9d553-p132">Il s’agit d’un attribut réservé de type chaîne gérant plusieurs valeurs. Les paramètres qui y sont stockés sont représentés par des paires nom=valeur. Les paires nom=valeur actuellement définies sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d553-p132">This is a multi-string reserved attribute. Settings stored in this attribute are represented as name=value pairs. Currently defined name=value pairs are:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-470">FactoryURL = &lt; URL&gt;</span><span class="sxs-lookup"><span data-stu-id="9d553-470">FactoryURL = &lt;URL&gt;</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9d553-471">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-471">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-472">msRTCSIP-MCUFactoryPath</span><span class="sxs-lookup"><span data-stu-id="9d553-472">msRTCSIP-MCUFactoryPath</span></span></p></td>
<td><p><span data-ttu-id="9d553-473">Cet attribut à valeur unique contient le nom unique (DN) d’un répartiteur de MCU unique associé à un pool.</span><span class="sxs-lookup"><span data-stu-id="9d553-473">This is a single-valued attribute that contains the distinguished name (DN) of a single MCU factory associated with a pool.</span></span></p>
<p><span data-ttu-id="9d553-474">Lien avant : <strong>ID de lien 11024</strong></span><span class="sxs-lookup"><span data-stu-id="9d553-474">Forward link: <strong>Link ID 11024</strong></span></span></p>
<p><span data-ttu-id="9d553-475">Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-PoolAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-475">The corresponding back link to this forward link attribute is <strong>msRTCSIP-PoolAddresses</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-476">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-476">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-477">msRTCSIP-MCUFactoryProviderID</span><span class="sxs-lookup"><span data-stu-id="9d553-477">msRTCSIP-MCUFactoryProviderID</span></span></p></td>
<td><p><span data-ttu-id="9d553-478">Cet attribut de type chaîne à valeur unique spécifie le GUID du fournisseur du répartiteur de MCU.</span><span class="sxs-lookup"><span data-stu-id="9d553-478">This attribute is a single-valued string that specifies the GUID of the MCU factory provider.</span></span> <span data-ttu-id="9d553-479">Selon la valeur du GUID, le répartiteur de MCU détermine s’il doit traiter ce type de MCU.</span><span class="sxs-lookup"><span data-stu-id="9d553-479">Based on the GUID value, the MCU factory process determines whether to service this MCU type.</span></span> <span data-ttu-id="9d553-480">Si la valeur GUID est <strong>{F0810510-424F-46ef-84fe-6CC720DF1791}</strong>, le processus d’usine MCU (disponible par défaut dans Lync Server) le traitera.</span><span class="sxs-lookup"><span data-stu-id="9d553-480">If the GUID value is <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>, then the MCU factory process (available by default in Lync Server) will process it.</span></span> <span data-ttu-id="9d553-481">Dans le cas contraire, il ne traite pas le type de MCU.</span><span class="sxs-lookup"><span data-stu-id="9d553-481">For any other GUID value, the MCU factory process will not service the MCU type.</span></span></p></td>
<td><p><span data-ttu-id="9d553-482">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-482">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-483">msRTCSIP-MCUServers</span><span class="sxs-lookup"><span data-stu-id="9d553-483">msRTCSIP-MCUServers</span></span></p></td>
<td><p><span data-ttu-id="9d553-p134">Cet attribut gérant plusieurs valeurs contient une liste de noms uniques (DN), à savoir la liste de tous les serveurs MCU de même type et fournisseur associés à ce répartiteur de MCU. Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="9d553-p134">This attribute is a multi-valued list of distinguished names (DN). This attribute contains a list of all MCU servers of the same type and vendor associated with this MCU factory. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p>
<p><span data-ttu-id="9d553-487">Lien arrière : ID de lien 11027</span><span class="sxs-lookup"><span data-stu-id="9d553-487">Back link: Link ID 11027</span></span></p>
<p><span data-ttu-id="9d553-488">Le lien avant correspondant à ce lien arrière est <strong>msRTCSIP-MCUFactoryAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-488">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-489">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-489">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-490">msRTCSIP-MCUType</span><span class="sxs-lookup"><span data-stu-id="9d553-490">msRTCSIP-MCUType</span></span></p></td>
<td><p><span data-ttu-id="9d553-491">Cet attribut de type chaîne à valeur unique spécifie le support géré par le MCU.</span><span class="sxs-lookup"><span data-stu-id="9d553-491">This attribute is a single-valued string that specifies the medium the MCU can handle.</span></span></p>
<p><span data-ttu-id="9d553-492">Les types de valeurs gérés sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="9d553-492">Supported valid types are:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-493">satisfaire</span><span class="sxs-lookup"><span data-stu-id="9d553-493">meeting</span></span></p></li>
<li><p><span data-ttu-id="9d553-494">audio-vidéo</span><span class="sxs-lookup"><span data-stu-id="9d553-494">audio-video</span></span></p></li>
<li><p><span data-ttu-id="9d553-495">conversation</span><span class="sxs-lookup"><span data-stu-id="9d553-495">chat</span></span></p></li>
<li><p><span data-ttu-id="9d553-496">Téléphone-CONF</span><span class="sxs-lookup"><span data-stu-id="9d553-496">phone-conf</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9d553-497">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-497">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-498">msRTCSIP-MCUVendor</span><span class="sxs-lookup"><span data-stu-id="9d553-498">msRTCSIP-MCUVendor</span></span></p></td>
<td><p><span data-ttu-id="9d553-p135">Cet attribut de type chaîne à valeur unique représente le nom d’un fournisseur de MCU. Pour tous les MCU Microsoft, cet attribut a la valeur <strong>Microsoft Corporation</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-p135">This attribute is a single-valued string that specifies an MCU vendor’s name. All Microsoft MCUs will specify this attribute to be <strong>Microsoft Corporation</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-501">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-501">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-502">msRTCSIP-MeetingFlags (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-502">msRTCSIP-MeetingFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p136">Cet attribut définit différentes options de réunion qui sont activées globalement pour tous les objets utilisateur ou contact. Sa valeur est un masque de bits de type nombre entier.</span><span class="sxs-lookup"><span data-stu-id="9d553-p136">This attribute defines different meeting options that are enabled globally for all users or contact objects. This attribute is a bit-mask value of integer type.</span></span></p>
<p><span data-ttu-id="9d553-505">Les valeurs (et les positions des bits associées) prises en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d553-505">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-506">0 : AllowOrganizeMeetingWithAnonymousParticipants a pour valeur Aucun (ne pas autoriser les utilisateurs à inviter des utilisateurs anonymes à des réunions) (aucun bit défini)</span><span class="sxs-lookup"><span data-stu-id="9d553-506">0: AllowOrganizeMeetingWithAnonymousParticipants is None (do not allow users to invite anonymous users to meetings) (no bits set)</span></span></p></li>
<li><p><span data-ttu-id="9d553-507">4 : AllowOrganizeMeetingWithAnonymousParticipants a est tout le monde (autoriser tous les utilisateurs à inviter des utilisateurs anonymes à des réunions) (position de bit 2)</span><span class="sxs-lookup"><span data-stu-id="9d553-507">4: AllowOrganizeMeetingWithAnonymousParticipants is Everyone (allow all users to invite anonymous users to meetings) (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="9d553-508">8 : AllowOrganizeMeetingWithAnonymousParticipants a la valeur UsePerUserSetting (permet aux utilisateurs d’inviter des utilisateurs anonymes à des réunions en fonction du paramètre par utilisateur) (position de bit 3)</span><span class="sxs-lookup"><span data-stu-id="9d553-508">8: AllowOrganizeMeetingWithAnonymousParticipants is UsePerUserSetting (allow users to invite anonymous users to meetings based on per user setting) (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="9d553-509">16 : UserPerUserMeetingPolicy (la stratégie de réunion est définie par utilisateur) (position de bit 4)</span><span class="sxs-lookup"><span data-stu-id="9d553-509">16: UserPerUserMeetingPolicy (meeting policy is defined per user) (bit position 4)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9d553-510">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-510">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-511">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-511">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-512">msRTCSIP-MeetingPolicy (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-512">msRTCSIP-MeetingPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-513">Cet attribut définit le nom unique (DN) de la stratégie que l’administrateur a attribué à cet utilisateur sous la forme d’un attribut à valeur unique.</span><span class="sxs-lookup"><span data-stu-id="9d553-513">This attribute specifies the distinguished name (DN) of the policy the administrator has assigned for this user as a single-valued attribute.</span></span></p></td>
<td><p><span data-ttu-id="9d553-514">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-514">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-515">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-515">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-516">msRTCSIP-MinPresenceSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-516">msRTCSIP-MinPresenceSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-517">Cet attribut représente le délai d’expiration minimal d’abonnement aux informations de présence.</span><span class="sxs-lookup"><span data-stu-id="9d553-517">This attribute represents the minimum presence subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="9d553-518">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-518">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-519">msRTCSIP-MinRegistrationTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-519">msRTCSIP-MinRegistrationTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-520">Cet attribut représente le délai d’expiration minimal d’inscription.</span><span class="sxs-lookup"><span data-stu-id="9d553-520">This attribute represents the minimum registration time-out window.</span></span></p></td>
<td><p><span data-ttu-id="9d553-521">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-521">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-522">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-522">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-523">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-523">msRTCSIP-MinRoamingDataSubscriptionTimeout (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-524">Cet attribut représente le délai d’expiration minimal de l’abonnement aux données d’itinérance.</span><span class="sxs-lookup"><span data-stu-id="9d553-524">This attribute represents the minimum roaming data subscription time-out window.</span></span></p></td>
<td><p><span data-ttu-id="9d553-525">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-525">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-526">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-526">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-527">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="9d553-527">msRTCSIP-MirrorBackEndServer</span></span></p></td>
<td><p><span data-ttu-id="9d553-528">Cet attribut est utilisé pour stocker le serveur principal SQL Server mis en miroir utilisé par le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="9d553-528">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span></p></td>
<td><p><span data-ttu-id="9d553-529">Nouveauté de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9d553-529">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-530">msRTCSIP-MobilityFlags</span><span class="sxs-lookup"><span data-stu-id="9d553-530">msRTCSIP-MobilityFlags</span></span></p></td>
<td><p><span data-ttu-id="9d553-531">Cet attribut contient des options et des indicateurs qui définissent les paramètres de mobilité.</span><span class="sxs-lookup"><span data-stu-id="9d553-531">This attribute contains options and flags that define mobility settings.</span></span></p></td>
<td><p><span data-ttu-id="9d553-532">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-532">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-533">msRTCSIP-MobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="9d553-533">msRTCSIP-MobilityPolicy</span></span></p></td>
<td><p><span data-ttu-id="9d553-534">Cet attribut contient le nom unique pour un objet de stratégie de mobilité.</span><span class="sxs-lookup"><span data-stu-id="9d553-534">This attribute contains the DN for a mobility policy object.</span></span></p></td>
<td><p><span data-ttu-id="9d553-535">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-535">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-536">msRTCSIP-NumDevicesPerUser (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-536">msRTCSIP-NumDevicesPerUser (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-537">Cet attribut représente le nombre autorisé de périphériques sur lesquels un utilisateur peut s’inscrire pour les communications SIP et s’abonner aux données de présence.</span><span class="sxs-lookup"><span data-stu-id="9d553-537">This attribute represents the allowed number of devices on which a user can register for SIP communications and subscribe to presence.</span></span></p></td>
<td><p><span data-ttu-id="9d553-538">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-538">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-539">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-539">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-540">msRTCSIP-OptionFlags</span><span class="sxs-lookup"><span data-stu-id="9d553-540">msRTCSIP-OptionFlags</span></span></p></td>
<td><p><span data-ttu-id="9d553-p137">Cet attribut définit les options qui sont activées pour l’objet utilisateur ou contact. Sa valeur est un masque de bits de type nombre entier. Chaque option est représentée par un bit. Il est identifié pour la réplication des catalogues globaux.</span><span class="sxs-lookup"><span data-stu-id="9d553-p137">This attribute specifies the options that are enabled for the user or contact object. This attribute is a bit-mask value of type integer. Each option is represented by a bit. This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="9d553-545">Les valeurs (et les positions des bits associées) prises en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d553-545">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-546">1 : activé pour la solution PIC (position de bit 0)</span><span class="sxs-lookup"><span data-stu-id="9d553-546">1: Enabled for public instant messaging (IM) connectivity (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="9d553-547">2 : réservé (position de bit 1)</span><span class="sxs-lookup"><span data-stu-id="9d553-547">2: Reserved (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="9d553-548">4 : réservé (position de bit 2)</span><span class="sxs-lookup"><span data-stu-id="9d553-548">4: Reserved (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="9d553-549">8 : réservé (position de bit 3)</span><span class="sxs-lookup"><span data-stu-id="9d553-549">8: Reserved (bit position 3)</span></span></p></li>
<li><p><span data-ttu-id="9d553-550">16 : Contrôle d’appel distant activé [Téléphonie] (position de bit 4)</span><span class="sxs-lookup"><span data-stu-id="9d553-550">16: Remote call control Enabled [Telephony] (bit position 4)</span></span></p></li>
<li><p><span data-ttu-id="9d553-551">64 : AllowOrganizeMeetingWithAnonymousParticipants (permet d’inviter des utilisateurs anonymes à des réunions) (position de bit 6)</span><span class="sxs-lookup"><span data-stu-id="9d553-551">64: AllowOrganizeMeetingWithAnonymousParticipants (allow users to invite anonymous users to meetings (bit position 6)</span></span></p></li>
<li><p><span data-ttu-id="9d553-552">128 : UCEnabled (active les utilisateurs pour les communications unifiées) (position de bit 7)</span><span class="sxs-lookup"><span data-stu-id="9d553-552">128: UCEnabled (enable users for UC) (bit position 7)</span></span></p></li>
<li><p><span data-ttu-id="9d553-553">256 : EnabledForEnhancedPresence (active l’utilisateur pour la solution PIC) (position de bit 8)</span><span class="sxs-lookup"><span data-stu-id="9d553-553">256: EnabledForEnhancedPresence (enable user for public IM connectivity) (bit position 8)</span></span></p></li>
<li><p><span data-ttu-id="9d553-554">512 : RemoteCallControlDualMode (position de bit 9)</span><span class="sxs-lookup"><span data-stu-id="9d553-554">512: RemoteCallControlDualMode (bit position 9)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9d553-555">Nouveauté de Live Communications Server 2005 avec SP1.</span><span class="sxs-lookup"><span data-stu-id="9d553-555">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-556">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="9d553-556">msRTCSIP-OriginatorSID</span></span></p></td>
<td><p><span data-ttu-id="9d553-557">Cet attribut est utilisé dans les topologies à forêts de ressources et à forêt centrale pour activer l’authentification unique lorsque l’identificateur ObjectSID du compte principal Windows NT Server d’un utilisateur est copié dans ce même attribut de l’objet utilisateur ou contact correspondant dans la forêt de ressources ou la forêt centrale.</span><span class="sxs-lookup"><span data-stu-id="9d553-557">This attribute is used in resource and central forest topologies to enable single sign-on when a user’s ObjectSID from the Windows NT Server principal account is copied into this attribute of the corresponding user or contact object in the resource or central forest.</span></span> <span data-ttu-id="9d553-558">Communicator Web Access recherche un utilisateur dans AD DS à l’aide de cet attribut ou de l’ObjectSID de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d553-558">Communicator Web Access searches for a user in AD DS using this attribute or the user’s ObjectSID.</span></span> <span data-ttu-id="9d553-559">Il est identifié pour la réplication des catalogues globaux.</span><span class="sxs-lookup"><span data-stu-id="9d553-559">This attribute is marked for global catalog replication.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-560">msRTCSIP-OwnerUrn</span><span class="sxs-lookup"><span data-stu-id="9d553-560">msRTCSIP-OwnerUrn</span></span></p></td>
<td><p><span data-ttu-id="9d553-561">Cet attribut est l’URN (Uniform Resource Name) du propriétaire pour un contact d’application.</span><span class="sxs-lookup"><span data-stu-id="9d553-561">This attribute is the Uniform Resource Name (URN) of the owner for an application contact.</span></span></p></td>
<td><p><span data-ttu-id="9d553-562">Nouveauté de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-562">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-563">msRTCSIP-Pattern (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-563">msRTCSIP-Pattern (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p139">Cet attribut de type chaîne à valeur unique contient un modèle de correspondance permettant de convertir les numéros à composer au format E.164. La conversion est appliquée à tout numéro correspondant au modèle.</span><span class="sxs-lookup"><span data-stu-id="9d553-p139">This single-valued string attribute contains a pattern used for matching dial numbers into E.164 format. If the dial number matches this pattern, the translation is applied to the dialed number.</span></span></p></td>
<td><p><span data-ttu-id="9d553-566">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-566">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-567">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-567">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-568">msRTCSIP-PhoneRouteBL (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-568">msRTCSIP-PhoneRouteBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p140">Cet attribut gérant plusieurs valeurs contient la liste des noms uniques (DN) d’itinéraires téléphoniques. Il indique le lien arrière d’un ou plusieurs itinéraires téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="9d553-p140">This multi-valued attribute contains a list of phone route distinguished names (DN). This attribute specifies the back link to one or more phone routes.</span></span></p>
<p><span data-ttu-id="9d553-571">Lien arrière : <strong>ID de lien 11033</strong></span><span class="sxs-lookup"><span data-stu-id="9d553-571">Back link: <strong>Link ID 11033</strong></span></span></p>
<p><span data-ttu-id="9d553-572">Cet attribut correspond au lien avant <strong>msRTCSIP-RouteUsageLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-572">This attribute corresponds to the forward link <strong>msRTCSIP-RouteUsageLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-573">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-573">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-574">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-574">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-575">msRTCSIP-PhoneRouteData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-575">msRTCSIP-PhoneRouteData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-576">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-576">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="9d553-577">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-577">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-578">msRTCSIP-PhoneRouteName (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-578">msRTCSIP-PhoneRouteName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-579">Cet attribut de type chaîne UNICODE à valeur unique indique le nom convivial de l’itinéraire téléphonique, qui peut ainsi être facilement référencé par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="9d553-579">This single valued UNICODE string attribute specifies the friendly name of the phone route, so it can easily be referenced by the administrator.</span></span></p></td>
<td><p><span data-ttu-id="9d553-580">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-580">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-581">msRTCSIP-PhoneUsageData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-581">msRTCSIP-PhoneUsageData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-582">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-582">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="9d553-583">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-583">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-584">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-584">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-585">msRTCSIP-PolicyContent (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-585">msRTCSIP-PolicyContent (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p141">Cet attribut de type chaîne UNICODE à valeur unique contient la définition de stratégie au format XML. La définition de schéma XML est commune à différents types de stratégies ; seuls les paramètres varient en fonction du type de stratégie.</span><span class="sxs-lookup"><span data-stu-id="9d553-p141">This attribute is a single-valued Unicode string. This string attribute contains the policy definition in XML format. The XML schema definition is common across different policy types, only the settings are different for each policy type.</span></span></p>
<p><span data-ttu-id="9d553-589">La définition de schéma XML (XSD) est définie de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="9d553-589">The XML schema definition (XSD) is defined as follows:</span></span></p>
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
<td><p><span data-ttu-id="9d553-590">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-590">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-591">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-591">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-592">msRTCSIP-PolicyData (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-592">msRTCSIP-PolicyData (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-593">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-593">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="9d553-594">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-594">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-595">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-595">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-596">msRTCSIP-PolicyType (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-596">msRTCSIP-PolicyType (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p142">Cet attribut de type chaîne Unicode à valeur unique contient le type de stratégie. Les types pris en charge sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="9d553-p142">This single-valued Unicode string attribute contains the policy type. Valid policy types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-599">satisfaire</span><span class="sxs-lookup"><span data-stu-id="9d553-599">meeting</span></span></p></li>
<li><p><span data-ttu-id="9d553-600">téléphonie</span><span class="sxs-lookup"><span data-stu-id="9d553-600">telephony</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9d553-601">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-601">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-602">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-602">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-603">msRTCSIP-PoolAddress</span><span class="sxs-lookup"><span data-stu-id="9d553-603">msRTCSIP-PoolAddress</span></span></p></td>
<td><p><span data-ttu-id="9d553-604">Cet attribut spécifie un lien permettant de revenir au pool auquel appartient un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="9d553-604">This attribute specifies a link back to the pool to which a computer belongs.</span></span> <span data-ttu-id="9d553-605">Cet attribut est défini, que l’ordinateur utilise ou non la version Standard Edition ou Enterprise Edition de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9d553-605">This attribute is set regardless of whether the computer is running the Standard Edition or the Enterprise Edition of Lync Server.</span></span> <span data-ttu-id="9d553-606">Il est identifié pour la réplication des catalogues globaux.</span><span class="sxs-lookup"><span data-stu-id="9d553-606">This attribute is marked for global catalog replication.</span></span></p>
<p><span data-ttu-id="9d553-607">La valeur correcte est le nom de domaine du pool.</span><span class="sxs-lookup"><span data-stu-id="9d553-607">The valid value is the domain name of the pool.</span></span></p>
<p><span data-ttu-id="9d553-608">Lien avant : <strong>ID de lien 11022</strong></span><span class="sxs-lookup"><span data-stu-id="9d553-608">Forward link: <strong>Link ID 11022</strong></span></span></p>
<p><span data-ttu-id="9d553-609">Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-FrontEndServers</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-609">The corresponding back link to this forward link attribute is <strong>msRTCSIP-FrontEndServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-610">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-610">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-611">msRTCSIP-PoolAddresses</span><span class="sxs-lookup"><span data-stu-id="9d553-611">msRTCSIP-PoolAddresses</span></span></p></td>
<td><p><span data-ttu-id="9d553-612">Cet attribut gérant plusieurs valeurs contient la liste des noms uniques (DN) des pools auxquels le répartiteur de MCU est associé.</span><span class="sxs-lookup"><span data-stu-id="9d553-612">This is a multi-valued attribute that contains a list of the distinguished names (DN) of pools with which the MCU factory is associated.</span></span></p>
<p><span data-ttu-id="9d553-613">Lien arrière : <strong>ID de lien 11025</strong></span><span class="sxs-lookup"><span data-stu-id="9d553-613">Back link: <strong>Link ID 11025</strong></span></span></p>
<p><span data-ttu-id="9d553-614">Le lien avant correspondant à ce lien arrière est <strong>msRTCSIP-MCUFactoryPath</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-614">The corresponding forward link to this back link is <strong>msRTCSIP-MCUFactoryPath</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-615">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-615">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-616">msRTCSIP-PoolData</span><span class="sxs-lookup"><span data-stu-id="9d553-616">msRTCSIP-PoolData</span></span></p></td>
<td><p><span data-ttu-id="9d553-617">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-617">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="9d553-618">Nouveauté de Live Communications Server 2005 avec SP1.</span><span class="sxs-lookup"><span data-stu-id="9d553-618">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-619">msRTCSIP-PoolDisplayName</span><span class="sxs-lookup"><span data-stu-id="9d553-619">msRTCSIP-PoolDisplayName</span></span></p></td>
<td><p><span data-ttu-id="9d553-p144">Cet attribut définit le nom arbitraire d’un pool affiché par la console de gestion. Ce nom peut être modifié par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="9d553-p144">This attribute specifies an arbitrary name for a pool that is displayed by the management console. This name can be changed by the administrator.</span></span></p>
<p><span data-ttu-id="9d553-622">La valeur correcte est une chaîne représentant le nom d’un pool.</span><span class="sxs-lookup"><span data-stu-id="9d553-622">The valid value is a string representing the name of a pool.</span></span></p></td>
<td><p><span data-ttu-id="9d553-623">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-623">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-624">msRTCSIP-PoolDomainFQDN</span><span class="sxs-lookup"><span data-stu-id="9d553-624">msRTCSIP-PoolDomainFQDN</span></span></p></td>
<td><p><span data-ttu-id="9d553-p145">Cet attribut est de type chaîne UNICODE à valeur unique. Lorsqu’elle est définie, la valeur de cet attribut représente le nom de domaine complet du pool si l’administrateur souhaite créer un pool frontal en lui attribuant un nom de domaine complet non conforme à la structure de domaines Active Directory dans lequel il créé le pool frontal (un espace de noms SIP dissocié de l’espace de noms DNS, par exemple).</span><span class="sxs-lookup"><span data-stu-id="9d553-p145">This attribute is a single-valued string value. The value of this attribute, when present, represents the pool’s domain FQDN if the administrator wants to create a Front End pool with an FQDN that does not conform to the Active Directory domain structure in which the Front End pool is created (for example, a SIP namespace disjoined from Domain Name System (DNS) namespace).</span></span></p>
<p><span data-ttu-id="9d553-p146">Nous vous recommandons de mapper le nom de domaine complet du pool frontal sur la partie de nom de domaine du domaine Active Directory dans lequel réside le pool. Par conséquent, quand la valeur de l’attribut n’est pas définie, le nom de domaine complet du pool frontal correspond par défaut à la structure des noms de domaine Active Directory, telle qu’indiquée par l’attribut <strong>dnsHostName</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-p146">We recommend that you map the Front End pool domain FQDN to the domain name portion as the Active Directory domain in which the pool resides. Therefore, when no value is present in this attribute, the Front End pool FQDN will default to the Active Directory domain name structure, as denoted by the <strong>dnsHostName</strong> attribute.</span></span></p></td>
<td><p><span data-ttu-id="9d553-629">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-629">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-630">msRTCSIP-PoolFunctionality</span><span class="sxs-lookup"><span data-stu-id="9d553-630">msRTCSIP-PoolFunctionality</span></span></p></td>
<td><p><span data-ttu-id="9d553-631">Liste à plusieurs valeurs des noms de domaine de tous les serveurs Lync Server, Enterprise Edition associés à un pool.</span><span class="sxs-lookup"><span data-stu-id="9d553-631">A multi-valued list of the domain names of all Lync Server, Enterprise Edition servers associated with a pool.</span></span> <span data-ttu-id="9d553-632">Cet attribut de type nombre entier détermine si le pool prend en charge la messagerie instantanée et les données de présence, ainsi que les réunions.</span><span class="sxs-lookup"><span data-stu-id="9d553-632">This attribute of type integer defines whether the pool is capable of instant messaging (IM) and presence, and meetings.</span></span></p>
<p><span data-ttu-id="9d553-633">Les types de valeurs pris en charge sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="9d553-633">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-634">Non défini : messagerie instantanée et service de présence (Live Communications Server 2005 et 2003)</span><span class="sxs-lookup"><span data-stu-id="9d553-634">Undefined: IM and Presence Service (Live Communications Server 2005 and 2003)</span></span></p></li>
<li><p><span data-ttu-id="9d553-635">1 : service de présence et de messagerie instantanée (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="9d553-635">1: IM and Presence Service (Lync Server)</span></span></p></li>
<li><p><span data-ttu-id="9d553-636">2 : messagerie instantanée et service de présence et de réunion (Lync Server)</span><span class="sxs-lookup"><span data-stu-id="9d553-636">2: IM and Presence and Meeting Service (Lync Server)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9d553-637">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-637">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-638">msRTCSIP-PoolType</span><span class="sxs-lookup"><span data-stu-id="9d553-638">msRTCSIP-PoolType</span></span></p></td>
<td><p><span data-ttu-id="9d553-p148">Cet attribut indique si un pool de serveurs exécute Standard Edition Server ou Enterprise Edition Server. Sa valeur est un masque de bits de type nombre entier. Chaque option est représentée par un bit.</span><span class="sxs-lookup"><span data-stu-id="9d553-p148">This attribute specifies whether a server pool is running Standard Edition server or Enterprise Edition server. This attribute is a bit-mask value of type integer. Each option is represented by a bit.</span></span></p>
<p><span data-ttu-id="9d553-642">Les valeurs (et les positions des bits associées) prises en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d553-642">The valid values (and associated bit positions) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-643">1 : Standard Edition Server, héberge des utilisateurs (position de bit 0)</span><span class="sxs-lookup"><span data-stu-id="9d553-643">1: Standard Edition server, hosts users (bit position 0)</span></span></p></li>
<li><p><span data-ttu-id="9d553-644">2 : Enterprise Edition Server, héberge des utilisateurs (position de bit 1)</span><span class="sxs-lookup"><span data-stu-id="9d553-644">2: Enterprise Edition server, hosts users (bit position 1)</span></span></p></li>
<li><p><span data-ttu-id="9d553-645">4 : Standard Edition Server, héberge des applications (position de bit 2)</span><span class="sxs-lookup"><span data-stu-id="9d553-645">4: Standard Edition server, hosts applications (bit position 2)</span></span></p></li>
<li><p><span data-ttu-id="9d553-646">8 : Enterprise Edition Server, héberge des applications (position de bit 3)</span><span class="sxs-lookup"><span data-stu-id="9d553-646">8: Enterprise Edition server, hosts applications (bit position 3)</span></span></p></li>
</ul>
<p><span data-ttu-id="9d553-647">Étant donné que Lync Server ne prend pas en charge les pools qui hébergent uniquement les applications, les seules valeurs valides sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d553-647">Because Lync Server does not support pools that host only applications, the only valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-648">5 : Standard Edition Server, héberge des utilisateurs et des applications (positions de bit 0 et 2)</span><span class="sxs-lookup"><span data-stu-id="9d553-648">5: Standard Edition server, hosts users and applications (bit positions 0 and 2)</span></span></p></li>
<li><p><span data-ttu-id="9d553-649">10 : Enterprise Edition Server, héberge des utilisateurs et des applications (positions de bit 1 et 3)</span><span class="sxs-lookup"><span data-stu-id="9d553-649">10: Enterprise Edition server, hosts users and applications (bit positions 1 and 3)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9d553-650">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-650">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-651">msRTCSIP-PoolVersion</span><span class="sxs-lookup"><span data-stu-id="9d553-651">msRTCSIP-PoolVersion</span></span></p></td>
<td><p><span data-ttu-id="9d553-p149">Cet attribut définit la version du pool. Sa valeur est un entier incrémenté à chaque version majeure du produit.</span><span class="sxs-lookup"><span data-stu-id="9d553-p149">This attribute defines the pool version. It is an integer type that is incremented with each major product release.</span></span></p>
<p><span data-ttu-id="9d553-654">Les types de valeurs pris en charge sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="9d553-654">The possible valid value types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-655">0 : Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="9d553-655">0: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="9d553-656">1 : Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="9d553-656">1: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="9d553-657">2 : Live Communications Server 2005 avec SP1</span><span class="sxs-lookup"><span data-stu-id="9d553-657">2: Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="9d553-658">3 : Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="9d553-658">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="9d553-659">4 : Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9d553-659">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="9d553-660">5 : Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9d553-660">5: Lync Server 2010</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9d553-661">Live Communications Server 2005 avec SP1.</span><span class="sxs-lookup"><span data-stu-id="9d553-661">Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-662">msRTCSIP-PresenceFlags</span><span class="sxs-lookup"><span data-stu-id="9d553-662">msRTCSIP-PresenceFlags</span></span></p></td>
<td><p><span data-ttu-id="9d553-663">Cet attribut contient des options et des indicateurs qui définissent les paramètres de présence.</span><span class="sxs-lookup"><span data-stu-id="9d553-663">This attribute contains options and flags that define presence settings.</span></span></p></td>
<td><p><span data-ttu-id="9d553-664">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-664">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-665">msRTCSIP-PresencePolicy</span><span class="sxs-lookup"><span data-stu-id="9d553-665">msRTCSIP-PresencePolicy</span></span></p></td>
<td><p><span data-ttu-id="9d553-666">Cet attribut contient le nom unique pour un objet de stratégie de présence.</span><span class="sxs-lookup"><span data-stu-id="9d553-666">This attribute contains the DN for a presence policy object.</span></span></p></td>
<td><p><span data-ttu-id="9d553-667">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-667">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-668">msRTCSIP-PrimaryHomeServer</span><span class="sxs-lookup"><span data-stu-id="9d553-668">msRTCSIP-PrimaryHomeServer</span></span></p></td>
<td><p><span data-ttu-id="9d553-p150">Cet attribut permet d’activer un utilisateur ou un contact pour la messagerie SIP. Il est ajouté à la classe contact car dans la topologie à forêt centrale, les objets contact (et pas les objets utilisateur) sont activés pour SIP.</span><span class="sxs-lookup"><span data-stu-id="9d553-p150">This attribute enables a user or contact for SIP messaging. It is added to the contact class because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="9d553-671">La valeur correcte est le nom unique du serveur Standard Edition ou du pool frontal Enterprise Edition hébergeant un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d553-671">The valid value is the DN of the Standard Edition server or Enterprise Edition Front End pool where a user is homed.</span></span></p></td>
<td><p><span data-ttu-id="9d553-672">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-672">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-673">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="9d553-673">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="9d553-674">Cet attribut contient l’adresse SIP d’un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="9d553-674">This attribute contains the SIP address of a given user.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-675">msRTCSIP-PrivateLine</span><span class="sxs-lookup"><span data-stu-id="9d553-675">msRTCSIP-PrivateLine</span></span></p></td>
<td><p><span data-ttu-id="9d553-676">Cet attribut contient l’ID de périphérique du périphérique de ligne privée.</span><span class="sxs-lookup"><span data-stu-id="9d553-676">This attribute contains the device ID of the private line device.</span></span></p></td>
<td><p><span data-ttu-id="9d553-677">Nouveauté de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-677">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-678">msRTCSIP-routable</span><span class="sxs-lookup"><span data-stu-id="9d553-678">msRTCSIP-Routable</span></span></p></td>
<td><p><span data-ttu-id="9d553-679">Cet attribut est un attribut booléen utilisé pour déterminer si Lync Server est autorisé à acheminer vers ce service à l’aide de son adresse GRUU.</span><span class="sxs-lookup"><span data-stu-id="9d553-679">This attribute is a Boolean attribute used to determine whether Lync Server is authorized to route to this service using its GRUU address.</span></span> <span data-ttu-id="9d553-680">Si cette valeur est définie sur <strong>true</strong>, Lync Server est autorisé à acheminer vers ce service.</span><span class="sxs-lookup"><span data-stu-id="9d553-680">If this value is set to <strong>TRUE</strong>, Lync Server is authorized to route to this service.</span></span> <span data-ttu-id="9d553-681">Si cette valeur est définie sur <strong>false</strong>, Lync Server n’est pas autorisé à acheminer vers ce service.</span><span class="sxs-lookup"><span data-stu-id="9d553-681">If this value is set to <strong>FALSE</strong>, Lync Server is not authorized to route to this service.</span></span></p></td>
<td><p><span data-ttu-id="9d553-682">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-682">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-683">msRTCSIP-RouteUsageAttribute (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-683">msRTCSIP-RouteUsageAttribute (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p152">Cet attribut de type chaîne UNICODE à valeur unique définit un attribut qualifiant l’utilisation d’un itinéraire téléphonique. La sélection d’un itinéraire téléphonique est déterminée en fonction de deux éléments : l’attribut d’utilisation affecté à l’itinéraire téléphonique et les attributs d’utilisation de la stratégie autorisée de l’appelant. Le premier itinéraire dont l’attribut d’utilisation correspond à l’utilisation autorisée de l’appelant est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9d553-p152">This single-valued UNICODE string attribute defines an attribute that qualifies the usage for a phone route. Selection of a phone route is determined based on two elements: the usage attribute assigned to the phone route and the caller’s allowed policy usage attributes. The first phone route with a usage attribute that matches the caller’s allowed usage is selected.</span></span></p></td>
<td><p><span data-ttu-id="9d553-687">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-687">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-688">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-688">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-689">msRTCSIP-RouteUsageLinks (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-689">msRTCSIP-RouteUsageLinks (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-690">Cet attribut gérant plusieurs valeurs contient la liste des noms uniques (DN) d’utilisation d’itinéraire téléphonique.</span><span class="sxs-lookup"><span data-stu-id="9d553-690">This multi-valued distinguished name (DN) attribute contains a list of route usage distinguished names.</span></span></p>
<p><span data-ttu-id="9d553-691">Lien avant : <strong>ID de lien 11032</strong></span><span class="sxs-lookup"><span data-stu-id="9d553-691">Forward link: <strong>Link ID 11032</strong></span></span></p>
<p><span data-ttu-id="9d553-692">Cet attribut est un lien avant correspondant au lien arrière <strong>msRTCSIP-PhoneRouteBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-692">This attribute is a forward link to the corresponding back link <strong>msRTCSIP-PhoneRouteBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-693">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-693">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-694">msRTCSIP-RoutingPoolDN</span><span class="sxs-lookup"><span data-stu-id="9d553-694">msRTCSIP-RoutingPoolDN</span></span></p></td>
<td><p><span data-ttu-id="9d553-695">Cet attribut contient le nom unique pointant vers le pool par lequel doit transiter tout le trafic SIP destiné à ce MCU ou à ce service approuvé.</span><span class="sxs-lookup"><span data-stu-id="9d553-695">This attribute contains the DN that points to the pool that all SIP traffic addressed to this MCU or Trusted Service must go through.</span></span></p></td>
<td><p><span data-ttu-id="9d553-696">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-696">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-697">msRTCSIP-RuleName (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-697">msRTCSIP-RuleName (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-698">Cet attribut de type chaîne UNICODE à valeur unique indique le nom convivial de la règle de normalisation, qui peut ainsi être facilement référencée par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="9d553-698">This single-valued UNICODE string attribute specifies the friendly name of the normalization rule, so it can easily be referenced by an administrator.</span></span></p></td>
<td><p><span data-ttu-id="9d553-699">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-699">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-700">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-700">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-701">msRTCSIP-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="9d553-701">msRTCSIP-SchemaVersion</span></span></p></td>
<td><p><span data-ttu-id="9d553-702">Cet attribut représente la version du schéma actuellement déployée dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="9d553-702">This attribute represents the schema version currently deployed in the organization.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-703">msRTCSIP-SearchMaxRequests (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-703">msRTCSIP-SearchMaxRequests (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-704">Cet attribut limite le nombre de résultats de recherche à renvoyer à partir d’une recherche d’annuaire lorsqu’un utilisateur recherche un contact à l’aide de Communicator.</span><span class="sxs-lookup"><span data-stu-id="9d553-704">This attribute limits the number of search results to be returned from a directory search when a user searches for a contact using Communicator.</span></span> <span data-ttu-id="9d553-705">Il remplace la valeur fournie par le client.</span><span class="sxs-lookup"><span data-stu-id="9d553-705">This attribute will override the value provided by the client.</span></span></p></td>
<td><p><span data-ttu-id="9d553-706">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-706">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-707">msRTCSIP-SearchMaxResults (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-707">msRTCSIP-SearchMaxResults (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-708">Cet attribut limite le nombre de demandes de recherche renvoyées.</span><span class="sxs-lookup"><span data-stu-id="9d553-708">This attribute limits the number of search requests returned.</span></span></p></td>
<td><p><span data-ttu-id="9d553-709">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-709">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-710">msRTCSIP-ServerBL</span><span class="sxs-lookup"><span data-stu-id="9d553-710">msRTCSIP-ServerBL</span></span></p></td>
<td><p><span data-ttu-id="9d553-p154">Cet attribut gérant plusieurs valeurs est un lien arrière qui contient une liste de noms uniques (DN). Ceux-ci pointent vers un pool ou un objet <strong>TrustedService</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-p154">This multi-valued attribute is a back link that contains a list of distinguished names (DN). These DNs point to a pool or <strong>TrustedService</strong> object.</span></span></p>
<p><span data-ttu-id="9d553-713">Cet attribut correspond au lien avant <strong>msRTCSIP-TrustedServiceLinks</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-713">This attribute corresponds to the forward link <strong>msRTCSIP-TrustedServiceLinks</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-714">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-714">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-715">msRTCSIP-Serverprotection</span><span class="sxs-lookup"><span data-stu-id="9d553-715">msRTCSIP-ServerData</span></span></p></td>
<td><p><span data-ttu-id="9d553-716">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-716">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-717">msRTCSIP-ServerReferenceBL (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-717">msRTCSIP-ServerReferenceBL (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p155">Cet attribut gérant plusieurs valeurs contient une liste de noms uniques. Ceux-ci sont des liens secondaires qui référencent d’autres objets Serveur auxquels il est possible d’attribuer un profil d’emplacement par défaut.</span><span class="sxs-lookup"><span data-stu-id="9d553-p155">This multi-valued attribute contains a list of distinguished names. These distinguished names are back links that reference other server objects that can be assigned a default location profile.</span></span></p>
<p><span data-ttu-id="9d553-720">Lien arrière : <strong>ID de lien 11037</strong></span><span class="sxs-lookup"><span data-stu-id="9d553-720">Back link: <strong>Link ID 11037</strong></span></span></p>
<p><span data-ttu-id="9d553-721">Le lien avant correspondant à ce lien arrière est <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-721">The corresponding forward link to this back link is <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</span></span></p>
<p><span data-ttu-id="9d553-722">Cet attribut de lien arrière référence uniquement des pools et des serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="9d553-722">This back link attribute references pools and Mediation Servers only.</span></span></p></td>
<td><p><span data-ttu-id="9d553-723">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-723">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-724">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-724">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-725">msRTCSIP-ServerVersion</span><span class="sxs-lookup"><span data-stu-id="9d553-725">msRTCSIP-ServerVersion</span></span></p></td>
<td><p><span data-ttu-id="9d553-p156">Cet attribut définit la version du serveur. Ce numéro de version s’applique à tous les rôles serveurs. C’est un entier qui augmente de façon monotone et est incrémenté à chaque version officielle du produit.</span><span class="sxs-lookup"><span data-stu-id="9d553-p156">This attribute defines the version information of the server. This version number applies to all server roles. It is a monotonously increasing integer that increments with each official product release.</span></span></p>
<p><span data-ttu-id="9d553-729">Les valeurs prises en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d553-729">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-730">Non défini : Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="9d553-730">Undefined: Live Communications Server 2003</span></span></p>
<p><span data-ttu-id="9d553-731">                 Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="9d553-731">                 Live Communications Server 2005</span></span></p>
<p><span data-ttu-id="9d553-732">                 Live Communications Server 2005 avec SP1</span><span class="sxs-lookup"><span data-stu-id="9d553-732">                 Live Communications Server 2005 with SP1</span></span></p></li>
<li><p><span data-ttu-id="9d553-733">3 : Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="9d553-733">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="9d553-734">4 : Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9d553-734">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="9d553-735">5 : Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9d553-735">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="9d553-736">6 : Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d553-736">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9d553-737">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-737">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-738">msRTCSIP-SourceObjectType</span><span class="sxs-lookup"><span data-stu-id="9d553-738">msRTCSIP-SourceObjectType</span></span></p></td>
<td><p><span data-ttu-id="9d553-739">Cet attribut à valeur unique de type entier définit le type d’objet vers lequel pointe <strong>msDS-SourceObjectDN</strong>, comme suit :</span><span class="sxs-lookup"><span data-stu-id="9d553-739">This single-valued attribute of integer type specifies the type of object the <strong>msDS-SourceObjectDN</strong> points to, as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-740">null | 0x00000001 : représente un objet utilisateur principal Windows NT Server issu d’une autre forêt.</span><span class="sxs-lookup"><span data-stu-id="9d553-740">null | 0x00000001: Represents a Windows NT Server principal user object from a different forest</span></span></p></li>
<li><p><span data-ttu-id="9d553-741">Les attributs suivants représentent un type de groupe issu d’une autre forêt pour le développement des groupes de distribution :</span><span class="sxs-lookup"><span data-stu-id="9d553-741">The following attributes represent a group type from a different forest for distribution group expansion:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-742">0x00000002 : ADS_GROUP_TYPE_GLOBAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="9d553-742">0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="9d553-743">0x00000004 : ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="9d553-743">0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="9d553-744">0x00000004 : ADS_GROUP_TYPE_LOCAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="9d553-744">0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="9d553-745">0x00000008 : ADS_GROUP_TYPE_UNIVERSAL_GROUP</span><span class="sxs-lookup"><span data-stu-id="9d553-745">0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</span></span></p></li>
<li><p><span data-ttu-id="9d553-746">0x80000000 : ADS_GROUP_TYPE_SECURITY_ENABLED</span><span class="sxs-lookup"><span data-stu-id="9d553-746">0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</span></span></p></li>
<li><p><span data-ttu-id="9d553-747">0x90000000 : représente un objet standard automatique ou accès abonné de la même forêt ou d’une autre forêt.</span><span class="sxs-lookup"><span data-stu-id="9d553-747">0x90000000: Represents an Auto-Attendant or subscriber access object from the same forest or a different forest</span></span></p></li>
</ul></li>
</ul></td>
<td><p><span data-ttu-id="9d553-748">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-748">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-749">msRTCSIP-SubscriptionAuthRequired (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-749">msRTCSIP-SubscriptionAuthRequired (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="9d553-750">Nouveauté de Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="9d553-750">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="9d553-751">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-751">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-752">msRTCSIP-TargetHomeServer</span><span class="sxs-lookup"><span data-stu-id="9d553-752">msRTCSIP-TargetHomeServer</span></span></p></td>
<td><p><span data-ttu-id="9d553-753">Cet attribut vous permet de déplacer un utilisateur ou un contact d’un pool Lync Server vers un autre.</span><span class="sxs-lookup"><span data-stu-id="9d553-753">This attribute enables you to move a user or contact object from one Lync Server pool to another.</span></span> <span data-ttu-id="9d553-754">Il est ajouté à la classe contact car dans la topologie à forêt centrale, les objets contact (et pas les objets utilisateur) sont activés pour SIP.</span><span class="sxs-lookup"><span data-stu-id="9d553-754">This attribute is added to the contact class, because in the central forest topology, contact objects, not user objects, are SIP enabled.</span></span></p>
<p><span data-ttu-id="9d553-755">La valeur correcte est le nom unique du serveur Standard Edition ou du pool frontal de destination vers lequel l’utilisateur doit être déplacé.</span><span class="sxs-lookup"><span data-stu-id="9d553-755">The valid value is the DN of the destination Standard Edition server or Front End pool to which a user is to be moved.</span></span></p></td>
<td><p><span data-ttu-id="9d553-756">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-756">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-757">msRTCSIP-TargetPhoneNumber (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-757">msRTCSIP-TargetPhoneNumber (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-758">Cet attribut de type chaîne à valeur unique contient un modèle ou une plage de numéros de téléphone à acheminer vers les passerelles spécifiées, définies dans <strong>msRTCSIP-Gateways</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-758">This single-valued string attribute contains a phone number pattern or range to route to the specified gateways defined in <strong>msRTCSIP-Gateways</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-759">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-759">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-760">msRTCSIP-TargetUserPolicies</span><span class="sxs-lookup"><span data-stu-id="9d553-760">msRTCSIP-TargetUserPolicies</span></span></p></td>
<td><p><span data-ttu-id="9d553-761">Cet attribut stocke des paires nom-valeur pour les stratégies cibles pour les utilisateurs de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9d553-761">This attribute stores name-value pairs for target policies for Lync Server users.</span></span></p></td>
<td><p><span data-ttu-id="9d553-762">Nouveauté de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-762">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-763">msRTCSIP-TenantId</span><span class="sxs-lookup"><span data-stu-id="9d553-763">msRTCSIP-TenantId</span></span></p></td>
<td><p><span data-ttu-id="9d553-764">Cet attribut stocke l’identificateur unique d’un locataire.</span><span class="sxs-lookup"><span data-stu-id="9d553-764">This attribute stores the unique identifier for a tenant.</span></span></p></td>
<td><p><span data-ttu-id="9d553-765">Nouveauté de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-765">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-766">msRTCSIP-Translation (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-766">msRTCSIP-Translation (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-767">Cet attribut est utilisé par la fonctionnalité voix de Lync Server et contient la chaîne de conversion à appliquer sur le numéro composé, si une correspondance est trouvée.</span><span class="sxs-lookup"><span data-stu-id="9d553-767">This attribute is used by the voice feature of Lync Server and contains the translation string to apply on the dialed number, if a match is found.</span></span></p></td>
<td><p><span data-ttu-id="9d553-768">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-768">New in Office Communications Server 2007.</span></span></p>
<p><span data-ttu-id="9d553-769">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-769">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-770">msRTCSIP-TrustedMCUData</span><span class="sxs-lookup"><span data-stu-id="9d553-770">msRTCSIP-TrustedMCUData</span></span></p></td>
<td><p><span data-ttu-id="9d553-771">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-771">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="9d553-772">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-772">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-773">msRTCSIP-TrustedMCUFQDN</span><span class="sxs-lookup"><span data-stu-id="9d553-773">msRTCSIP-TrustedMCUFQDN</span></span></p></td>
<td><p><span data-ttu-id="9d553-p158">Cet attribut de type chaîne contient le nom de domaine complet du MCU. Il gère une valeur unique. Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="9d553-p158">This attribute is a string value that contains the FQDN of the MCU. This is a single-valued attribute. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="9d553-777">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-777">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-778">msRTCSIP-TrustedProxyData</span><span class="sxs-lookup"><span data-stu-id="9d553-778">msRTCSIP-TrustedProxyData</span></span></p></td>
<td><p><span data-ttu-id="9d553-779">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-779">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="9d553-780">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-780">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-781">msRTCSIP-TrustedProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="9d553-781">msRTCSIP-TrustedProxyFQDN</span></span></p></td>
<td><p><span data-ttu-id="9d553-p159">Cet attribut de type chaîne contient le nom de domaine complet du serveur exécutant le serveur proxy. Il gère une valeur unique. Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="9d553-p159">This attribute is a string value that contains the FQDN of the server running Proxy Server. This attribute is single-valued. The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="9d553-785">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-785">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-786">msRTCSIP-TrustedServerData</span><span class="sxs-lookup"><span data-stu-id="9d553-786">msRTCSIP-TrustedServerData</span></span></p></td>
<td><p><span data-ttu-id="9d553-787">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-787">This attribute is reserved for future use.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-788">msRTCSIP-TrustedServerFQDN</span><span class="sxs-lookup"><span data-stu-id="9d553-788">msRTCSIP-TrustedServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="9d553-789">Cet attribut à valeur unique représente le nom de domaine complet d’un serveur approuvé.</span><span class="sxs-lookup"><span data-stu-id="9d553-789">This attribute is a single-valued attribute that represents the FQDN of a trusted server.</span></span></p></td>
<td><p><span data-ttu-id="9d553-790">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-790">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-791">msRTCSIP-TrustedServerVersion</span><span class="sxs-lookup"><span data-stu-id="9d553-791">msRTCSIP-TrustedServerVersion</span></span></p></td>
<td><p><span data-ttu-id="9d553-792">Cet attribut définit le numéro de version d’un serveur de la liste de serveurs approuvés.</span><span class="sxs-lookup"><span data-stu-id="9d553-792">This attribute specifies the version number of a server in the trusted server list.</span></span></p>
<p><span data-ttu-id="9d553-793">Les valeurs prises en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d553-793">The possible valid values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-794">NULL : Live Communications Server 2003</span><span class="sxs-lookup"><span data-stu-id="9d553-794">NULL: Live Communications Server 2003</span></span></p></li>
<li><p><span data-ttu-id="9d553-795">2 : Live Communications Server 2005</span><span class="sxs-lookup"><span data-stu-id="9d553-795">2: Live Communications Server 2005</span></span></p></li>
<li><p><span data-ttu-id="9d553-796">3 : Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="9d553-796">3: Office Communications Server 2007</span></span></p></li>
<li><p><span data-ttu-id="9d553-797">4 : Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9d553-797">4: Office Communications Server 2007 R2</span></span></p></li>
<li><p><span data-ttu-id="9d553-798">5 : Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9d553-798">5: Lync Server 2010</span></span></p></li>
<li><p><span data-ttu-id="9d553-799">6 : Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d553-799">6: Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9d553-800">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-800">New in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-801">msRTCSIP-TrustedServiceFlags</span><span class="sxs-lookup"><span data-stu-id="9d553-801">msRTCSIP-TrustedServiceFlags</span></span></p></td>
<td><p><span data-ttu-id="9d553-802">Cet attribut définit les options activées pour le service approuvé.</span><span class="sxs-lookup"><span data-stu-id="9d553-802">This attribute defines the options that are enabled for the trusted service.</span></span></p></td>
<td><p><span data-ttu-id="9d553-803">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-803">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-804">msRTCSIP-TrustedServiceLinks</span><span class="sxs-lookup"><span data-stu-id="9d553-804">msRTCSIP-TrustedServiceLinks</span></span></p></td>
<td><p><span data-ttu-id="9d553-805">Cet attribut gérant plusieurs valeurs contient une liste de noms uniques (DN) référençant un objet service approuvé, tel qu’un service d’authentification Media Relay.</span><span class="sxs-lookup"><span data-stu-id="9d553-805">This multi-valued attribute contains a list of distinguished names (DN) that reference a trusted service object, such as a Media Relay Authentication Service.</span></span> <span data-ttu-id="9d553-806">Un service d’authentification de serveur relais multimédia (colocalisé physiquement sur le serveur Edge exécutant le service de conférence A/V) doit être associé à un pool pour prendre en charge les scénarios audio pour les utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="9d553-806">A Media Relay Authentication Service (physically collocated on the Edge Server running the A/V Conferencing service) must be associated with a pool to support audio scenarios for remote users.</span></span></p>
<p><span data-ttu-id="9d553-807">Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-ServerBL</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-807">The corresponding back link to this forward link attribute is <strong>msRTCSIP-ServerBL</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-808">UC</span><span class="sxs-lookup"><span data-stu-id="9d553-808">UC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-809">msRTCSIP-TrustedServicePort</span><span class="sxs-lookup"><span data-stu-id="9d553-809">msRTCSIP-TrustedServicePort</span></span></p></td>
<td><p><span data-ttu-id="9d553-810">Cet attribut est un entier qui définit le numéro de port permettant la connexion à ce service GRUU.</span><span class="sxs-lookup"><span data-stu-id="9d553-810">This attribute is an integer that defines the port number used to connect to this GRUU service.</span></span></p></td>
<td><p><span data-ttu-id="9d553-811">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-811">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-812">msRTCSIP-TrustedServiceType</span><span class="sxs-lookup"><span data-stu-id="9d553-812">msRTCSIP-TrustedServiceType</span></span></p></td>
<td><p><span data-ttu-id="9d553-813">Cet attribut de type chaîne définit le type de service GRUU qu’il représente.</span><span class="sxs-lookup"><span data-stu-id="9d553-813">This attribute is a string value that defines the type of GRUU service it represents.</span></span></p>
<p><span data-ttu-id="9d553-814">Les types de services GRUU pris en charge sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="9d553-814">The valid GRUU service types are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-815">MediationServer</span><span class="sxs-lookup"><span data-stu-id="9d553-815">MediationServer</span></span></p></li>
<li><p><span data-ttu-id="9d553-816">Passerelle</span><span class="sxs-lookup"><span data-stu-id="9d553-816">Gateway</span></span></p></li>
<li><p><span data-ttu-id="9d553-817">MRAS (Media Relay Authentication Service, service d’authentification Media Relay) ;</span><span class="sxs-lookup"><span data-stu-id="9d553-817">Media Relay Authentication Service (MRAS)</span></span></p></li>
<li><p><span data-ttu-id="9d553-818">QoSM</span><span class="sxs-lookup"><span data-stu-id="9d553-818">QoSM</span></span></p></li>
<li><p><span data-ttu-id="9d553-819">msRTCSIP-UserExtension CWA</span><span class="sxs-lookup"><span data-stu-id="9d553-819">msRTCSIP-UserExtension CWA</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9d553-820">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-820">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-821">msRTCSIP-TrustedWebComponentsServerData</span><span class="sxs-lookup"><span data-stu-id="9d553-821">msRTCSIP-TrustedWebComponentsServerData</span></span></p></td>
<td><p><span data-ttu-id="9d553-822">Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-822">This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="9d553-823">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-823">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-824">msRTCSIP-TrustedWebComponentsServerFQDN</span><span class="sxs-lookup"><span data-stu-id="9d553-824">msRTCSIP-TrustedWebComponentsServerFQDN</span></span></p></td>
<td><p><span data-ttu-id="9d553-825">Cet attribut est une valeur de type String qui contient le nom de domaine complet du serveur IIS exécutant les services Web Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9d553-825">This attribute is a string value that contains the FQDN of the IIS running Lync Server Web Services.</span></span> <span data-ttu-id="9d553-826">Il gère une valeur unique.</span><span class="sxs-lookup"><span data-stu-id="9d553-826">This is a single-valued attribute.</span></span> <span data-ttu-id="9d553-827">Pour chaque segment, la valeur correcte est de 63 caractères et, pour tout le nom de domaine complet, de 255 caractères.</span><span class="sxs-lookup"><span data-stu-id="9d553-827">The valid value for each segment is 63 characters; the valid value for the entire FQDN is 255 characters.</span></span></p></td>
<td><p><span data-ttu-id="9d553-828">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-828">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-829">msRTCSIP-UCFlags (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-829">msRTCSIP-UCFlags (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p162">Cet attribut définit différentes options relatives aux communications unifiées qui sont activées globalement pour tous les objets utilisateur ou contact. Sa valeur est un masque de bits de type nombre entier. Chaque option est représentée par un bit.</span><span class="sxs-lookup"><span data-stu-id="9d553-p162">This attribute defines different UC options that are enabled globally to all user or contact objects. This attribute is a bit-mask value of integer type. Each option is represented by the presence of a bit.</span></span></p>
<p><span data-ttu-id="9d553-833">Les valeurs (et les positions des bits associées) prises en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d553-833">The possible valid value (and associated bit position) are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-834">4 : UsePerUserUCPolicy (position de bit 2)</span><span class="sxs-lookup"><span data-stu-id="9d553-834">4: UsePerUserUCPolicy (bit position 2)</span></span></p></li>
</ul>
<p><span data-ttu-id="9d553-835">Lorsque ce bit est activé, la stratégie de communications unifiées est définie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d553-835">When this bit is set, the UC policy is defined per user.</span></span></p></td>
<td><p><span data-ttu-id="9d553-836">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-836">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-837">msRTCSIP-UCPolicy (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-837">msRTCSIP-UCPolicy (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-838">Cet attribut à valeur unique contient le nom unique (DN) de la stratégie de communications unifiées que l’administrateur a attribué à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d553-838">This single-valued attribute contains the distinguished name (DN) of the UC policy that the administrator has assigned for this user.</span></span></p></td>
<td><p><span data-ttu-id="9d553-839">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-839">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-840">msRTCSIP-UserDomainList (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-840">msRTCSIP-UserDomainList (obsolete)</span></span></p></td>
<td><p><span data-ttu-id="9d553-p163">Cet attribut recense tous les domaines d’une forêt hébergeant des utilisateurs SIP. La liste est vide par défaut, ce qui indique que tous les domaines de la forêt sont activés pour SIP.</span><span class="sxs-lookup"><span data-stu-id="9d553-p163">This attribute provides a list of all the domains in a forest that host SIP-enabled users. The default is an empty list, indicating that all domains in the forest are SIP-enabled.</span></span></p>
<p><span data-ttu-id="9d553-843">Les valeurs prises en charge sont plusieurs chaînes représentant les noms de domaine spécifiques.</span><span class="sxs-lookup"><span data-stu-id="9d553-843">Valid values are multiple strings representing the domain names of individual domains.</span></span></p></td>
<td><p><span data-ttu-id="9d553-844">Nouveauté de Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-844">New in Live Communications Server 2005.</span></span></p>
<p><span data-ttu-id="9d553-845">Obsolète dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-845">Obsolete in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-846">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="9d553-846">msRTCSIP-UserEnabled</span></span></p></td>
<td><p><span data-ttu-id="9d553-847">Cet attribut détermine si l’utilisateur est actuellement activé pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9d553-847">This attribute determines whether the user is currently enabled for Lync Server.</span></span></p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-848">msRTCSIP-UserExtension</span><span class="sxs-lookup"><span data-stu-id="9d553-848">msRTCSIP-UserExtension</span></span></p></td>
<td><p><span data-ttu-id="9d553-849">Cet attribut à valeurs multiples contient une liste de paires nom-valeur au format &quot; nom = valeur. &quot; Cet attribut est marqué pour la réplication de catalogue global.</span><span class="sxs-lookup"><span data-stu-id="9d553-849">This multi-valued attribute contains a list of name-value pairs in the format of &quot;name=value.&quot; This attribute is marked for global catalog replication.</span></span></p></td>
<td><p><span data-ttu-id="9d553-850">Nouveauté de Live Communications Server 2005 avec SP1.</span><span class="sxs-lookup"><span data-stu-id="9d553-850">New in Live Communications Server 2005 with SP1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-851">msRTCSIP-UserLocationProfile</span><span class="sxs-lookup"><span data-stu-id="9d553-851">msRTCSIP-UserLocationProfile</span></span></p></td>
<td><p><span data-ttu-id="9d553-852">Cet attribut contient le nom unique (DN) pointant sur un objet de profil d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="9d553-852">This attribute contains the distinguished name (DN) that points to a location profile object.</span></span></p></td>
<td><p><span data-ttu-id="9d553-853">Nouveauté d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9d553-853">New in Office Communications Server 2007 R2.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-854">msRTCSIP-UserPolicies</span><span class="sxs-lookup"><span data-stu-id="9d553-854">msRTCSIP-UserPolicies</span></span></p></td>
<td><p><span data-ttu-id="9d553-855">Cet attribut permet de stocker les paires nom-valeur des stratégies utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d553-855">This attribute stores name-value pairs for user policies.</span></span></p></td>
<td><p><span data-ttu-id="9d553-856">Nouveauté de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9d553-856">New in Lync Server 2010.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-857">msRTCSIP-UserPolicy</span><span class="sxs-lookup"><span data-stu-id="9d553-857">msRTCSIP-UserPolicy</span></span></p></td>
<td><p><span data-ttu-id="9d553-p164">Cet attribut gérant plusieurs valeurs contient une liste de noms uniques avec une partie binaire (DN_WITH_BINARY) pointant vers des stratégies utilisateur globales de différents types. La partie binaire indique le type de stratégie vers laquelle pointe la partie DN.</span><span class="sxs-lookup"><span data-stu-id="9d553-p164">This is a multi-valued attribute containing a list of distinguished names with binary (DN_WITH_BINARY) pointing to global user policies of different types. The binary part indicates the type of policy to which the DN portion points.</span></span></p>
<p><span data-ttu-id="9d553-860">Les valeurs binaires correctes sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d553-860">The valid binary values are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-861">0x00000001 : stratégie de réunion</span><span class="sxs-lookup"><span data-stu-id="9d553-861">0x00000001: Meeting policy</span></span></p></li>
<li><p><span data-ttu-id="9d553-862">0x00000002 : stratégie de communications unifiées</span><span class="sxs-lookup"><span data-stu-id="9d553-862">0x00000002: UC policy</span></span></p></li>
<li><p><span data-ttu-id="9d553-863">0x00000005 : stratégie de présence</span><span class="sxs-lookup"><span data-stu-id="9d553-863">0x00000005: Presence policy</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9d553-864">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-864">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-865">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="9d553-865">msRTCSIP-UserRoutingGroupId</span></span></p></td>
<td><p><span data-ttu-id="9d553-p165">Cette valeur est l’ID de groupe de routage SIP. Les utilisateurs du même groupe s’inscrivent sur le même serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="9d553-p165">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span></p></td>
<td><p><span data-ttu-id="9d553-868">Nouveauté de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9d553-868">New in Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-869">msRTCSIP-WebComponentsData</span><span class="sxs-lookup"><span data-stu-id="9d553-869">msRTCSIP-WebComponentsData</span></span></p></td>
<td><p><span data-ttu-id="9d553-p166">Cet attribut gère plusieurs valeurs. Cet attribut est réservé à un usage ultérieur.</span><span class="sxs-lookup"><span data-stu-id="9d553-p166">This is a multi-valued attribute. This attribute is reserved for future use.</span></span></p></td>
<td><p><span data-ttu-id="9d553-872">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-872">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-873">msRTCSIP-WebComponentsPoolAddress</span><span class="sxs-lookup"><span data-stu-id="9d553-873">msRTCSIP-WebComponentsPoolAddress</span></span></p></td>
<td><p><span data-ttu-id="9d553-874">Cet attribut à valeur unique pointe vers le pool ou le serveur Standard Edition auquel appartiennent les composants web.</span><span class="sxs-lookup"><span data-stu-id="9d553-874">This single-valued attribute points to the pool or Standard Edition server to which the web components belong.</span></span></p>
<p><span data-ttu-id="9d553-875">Lien avant : <strong>ID de lien 11028</strong></span><span class="sxs-lookup"><span data-stu-id="9d553-875">Forward link: <strong>Link ID 11028</strong></span></span></p>
<p><span data-ttu-id="9d553-876">Le lien arrière correspondant à cet attribut de lien avant est <strong>msRTCSIP-WebComponentsServer</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-876">The corresponding back link to this forward link attribute is <strong>msRTCSIP-WebComponentsServers</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-877">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-877">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-878">msRTCSIP-Webcomponentsserver</span><span class="sxs-lookup"><span data-stu-id="9d553-878">msRTCSIP-WebComponentsServers</span></span></p></td>
<td><p><span data-ttu-id="9d553-p167">Cet attribut gérant plusieurs valeurs contient une liste de noms uniques répertoriant tous les serveurs web associés à ce pool.</span><span class="sxs-lookup"><span data-stu-id="9d553-p167">This attribute is a multi-valued list of distinguished names. This attribute contains a list of all Web servers associated with this pool.</span></span></p>
<p><span data-ttu-id="9d553-881">Lien arrière : <strong>ID de lien 11029</strong></span><span class="sxs-lookup"><span data-stu-id="9d553-881">Back link: <strong>Link ID 11029</strong></span></span></p>
<p><span data-ttu-id="9d553-882">Le lien avant correspondant à ce lien arrière est <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span><span class="sxs-lookup"><span data-stu-id="9d553-882">The corresponding forward link to this back link is <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</span></span></p></td>
<td><p><span data-ttu-id="9d553-883">Nouveauté d’Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9d553-883">New in Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-884">msRTCSIP-WMIInstanceId (obsolète)</span><span class="sxs-lookup"><span data-stu-id="9d553-884">msRTCSIP-WMIInstanceId (obsolete)</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="9d553-885">Nouveauté de Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="9d553-885">New in Live Communications Server 2003.</span></span></p>
<p><span data-ttu-id="9d553-886">Obsolète dans Live Communications Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9d553-886">Obsolete in Live Communications Server 2005.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-887">OtherIPPhone</span><span class="sxs-lookup"><span data-stu-id="9d553-887">OtherIPPhone</span></span></p></td>
<td><p><span data-ttu-id="9d553-888">Cet attribut Active Directory existant est utilisé par la téléphonie pour spécifier la liste des autres adresses TCP/IP d’un téléphone.</span><span class="sxs-lookup"><span data-stu-id="9d553-888">This existing Active Directory attribute is used by telephony to specify the list of alternate TCP/IP addresses for a phone.</span></span></p></td>
<td><p><span data-ttu-id="9d553-889">Il s’agit d’une nouveauté du système d’exploitation Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="9d553-889">New in Windows Server 2008 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-890">PhoneOfficeOther</span><span class="sxs-lookup"><span data-stu-id="9d553-890">PhoneOfficeOther</span></span></p></td>
<td><p><span data-ttu-id="9d553-891">Cet attribut Active Directory existant est utilisé par les composants vocaux dans Lync Server, uniquement pour les objets contact, pour le routage des appels vers les numéros de standard automatique et d’accès abonné de la messagerie unifiée.</span><span class="sxs-lookup"><span data-stu-id="9d553-891">This existing Active Directory attribute is used by the voice components in Lync Server, for contact objects only, for the purpose of routing calls to the unified messaging auto-attendant and subscriber access numbers.</span></span> <span data-ttu-id="9d553-892">L’adresse de transfert d’appel sans condition est stockée dans cet attribut à valeurs multiples.</span><span class="sxs-lookup"><span data-stu-id="9d553-892">The unconditional call forwarding address is stored in this multi-valued attribute.</span></span> <span data-ttu-id="9d553-893">Ce compte est créé pour l’objectif spécifique du standard automatique et de l’accès abonné.</span><span class="sxs-lookup"><span data-stu-id="9d553-893">This account is created for the specific purpose of auto-attendant and subscriber access.</span></span> <span data-ttu-id="9d553-894">Les attributs de ce compte ne doivent pas être modifiés par les administrateurs.</span><span class="sxs-lookup"><span data-stu-id="9d553-894">This account’s attributes should not be modified by administrators.</span></span></p></td>
<td><p><span data-ttu-id="9d553-895">Il s’agit d’une nouveauté du système d’exploitation Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="9d553-895">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d553-896">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="9d553-896">ProxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="9d553-897">Cet attribut Active Directory existant qui gère plusieurs valeurs fait partie du schéma Active Directory de base introduit dans Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="9d553-897">This existing Active Directory multi-valued attribute is part of the base Active Directory schema introduced in Windows 2000.</span></span> <span data-ttu-id="9d553-898">Il contient les adresses électroniques X400, X500 et SMTP de la messagerie de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d553-898">This attribute contains the various X400, X500, and SMTP addresses of the user’s email.</span></span> <span data-ttu-id="9d553-899">Dans Live Communications Server 2003 et versions ultérieures, l’URI SIP de l’utilisateur est ajouté à cette liste à l’aide de la &quot; &quot; balise SIP :.</span><span class="sxs-lookup"><span data-stu-id="9d553-899">In Live Communications Server 2003 and later, the user’s SIP URI is added to this list, using the &quot;sip:&quot; tag.</span></span></p>
<p><span data-ttu-id="9d553-900">Les applications suivantes utilisent cet attribut pour examiner l’URI SIP de l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="9d553-900">The following applications search the user’s SIP URI from this attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="9d553-901">Client de messagerie et de collaboration Microsoft Office Outlook 2003</span><span class="sxs-lookup"><span data-stu-id="9d553-901">Microsoft Office Outlook 2003 messaging and collaboration client</span></span></p></li>
<li><p><span data-ttu-id="9d553-902">Microsoft Office SharePoint Server 2007</span><span class="sxs-lookup"><span data-stu-id="9d553-902">Microsoft Office SharePoint Server 2007</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9d553-903">Il s’agit d’une nouveauté du système d’exploitation Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="9d553-903">New in Windows 2000 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d553-904">TelephoneNumber</span><span class="sxs-lookup"><span data-stu-id="9d553-904">TelephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="9d553-905">Cet attribut Active Directory existant contient le numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9d553-905">This existing Active Directory attribute contains the telephone number for the user.</span></span></p></td>
<td><p><span data-ttu-id="9d553-906">Il s’agit d’une nouveauté du système d’exploitation Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="9d553-906">New in Windows 2000 operating system.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

