---
title: 'Lync Server 2013 : paramètres nouveaux et modifiés pour Lync 2013'
description: 'Lync Server 2013 : paramètres nouveaux et modifiés pour Lync 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bf744e1bae774904733390ec624be523ad32bc1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561390"
---
# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="8d75d-103">Paramètres nouveaux et modifiés pour Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8d75d-103">New and changed settings for Lync 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d75d-104">_**Dernière modification de la rubrique :** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="8d75d-104">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="8d75d-105">Cette rubrique traite des modifications apportées aux applets de commande Lync Server Management Shell qui sont directement liées à la gestion des clients.</span><span class="sxs-lookup"><span data-stu-id="8d75d-105">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="8d75d-106">Lync Server 2013 introduit plusieurs nouveaux paramètres et déprécie les paramètres des fonctionnalités qui peuvent être configurées par d’autres moyens.</span><span class="sxs-lookup"><span data-stu-id="8d75d-106">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="8d75d-107">Nouveau paramètres de gestion des clients</span><span class="sxs-lookup"><span data-stu-id="8d75d-107">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d75d-108">Nouveau</span><span class="sxs-lookup"><span data-stu-id="8d75d-108">New</span></span></th>
<th><span data-ttu-id="8d75d-109">Cmdlet Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8d75d-109">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="8d75d-110">Description</span><span class="sxs-lookup"><span data-stu-id="8d75d-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d75d-111">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="8d75d-111">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="8d75d-112">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="8d75d-112">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="8d75d-113">Lorsque ce paramètre est défini sur true, le suivi de logiciel est activé dans Lync ; Lorsque la valeur est false, le suivi de logiciel est désactivé.</span><span class="sxs-lookup"><span data-stu-id="8d75d-113">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="8d75d-114">Le suivi des logiciels implique de conserver un enregistrement détaillé de tous les éléments qu’un programme effectue (y compris les appels d’API de suivi).</span><span class="sxs-lookup"><span data-stu-id="8d75d-114">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="8d75d-115">Le suivi est principalement utile aux développeurs et au personnel de support des applications. Ce paramètre équivaut au paramètre de stratégie de groupe Communications Server 2007 R2 &quot; activer le suivi pour Communicator. &quot; Les paramètres sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="8d75d-115">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="8d75d-116">Off = Le suivi est désactivé et l’utilisateur ne peut pas modifier le paramètre.</span><span class="sxs-lookup"><span data-stu-id="8d75d-116">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="8d75d-117">Light = Un suivi minimal est assuré et l’utilisateur ne peut pas modifier ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="8d75d-117">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="8d75d-118">On = Un suivi documenté est assuré et l’utilisateur ne peut pas modifier ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="8d75d-118">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="8d75d-p103">Par défaut, TracingLevel a la valeur null. Cela signifie qu’un suivi minimal est assuré, mais que l’utilisateur peut activer ou désactiver ce suivi minimal.</span><span class="sxs-lookup"><span data-stu-id="8d75d-p103">By default TracingLevel is set to a null value. That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d75d-121">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="8d75d-121">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="8d75d-122">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="8d75d-122">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="8d75d-p104">Lorsque la valeur est True ($True), les flux audio et vidéo peuvent être isolés du reste du trafic réseau. Les périphériques clients peuvent alors les coder et les décoder localement. La redirection de médias se traduit généralement par une moindre utilisation de la bande passante, une plus grande extensibilité du serveur et une expérience utilisateur optimisée par rapport aux techniques similaires telles que l’accès à distance des périphériques ou la compression codec.</span><span class="sxs-lookup"><span data-stu-id="8d75d-p104">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally. Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d75d-125">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="8d75d-125">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="8d75d-126">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="8d75d-126">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="8d75d-127">Lorsque la valeur est true, toutes les réunions Lync sont traitées comme des &quot; grandes réunions. &quot; Avec une grande réunion, des restrictions sont placées sur le nombre de notifications envoyées aux participants, en plus de la taille de la liste de réunions qui est transmise par défaut.</span><span class="sxs-lookup"><span data-stu-id="8d75d-127">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d75d-128">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="8d75d-128">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="8d75d-129">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="8d75d-129">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="8d75d-p105">Quand la valeur est True ($True), les utilisateurs ne sont pas en mesure d’ajouter des annotations à des diapositives PowerPoint utilisées dans une conférence. Cependant, (en fonction de la valeur de la propriété AllowAnnotations), les utilisateurs ont toujours accès aux autres fonctionnalités de tableau blanc. La valeur par défaut est False, ce qui signifie que les annotations PowerPoint sont autorisées.</span><span class="sxs-lookup"><span data-stu-id="8d75d-p105">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference. However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features. The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d75d-133">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="8d75d-133">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="8d75d-134">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="8d75d-134">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="8d75d-135">Quand la valeur est True (valeur par défaut), tout bloc-notes OneNote ouvert lié à la conférence est automatiquement mis à jour avec des informations telles que les participants à la conférence et les détails sur le contenu partagé pendant la conférence.</span><span class="sxs-lookup"><span data-stu-id="8d75d-135">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d75d-136">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="8d75d-136">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="8d75d-137">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d75d-137">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="8d75d-138">Utilisé avec les autres nouveaux paramètres CsMeetingConfiguration pour personnaliser les invitations aux réunions générées par le complément de réunion en ligne pour Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8d75d-138">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d75d-139">LogoURL</span><span class="sxs-lookup"><span data-stu-id="8d75d-139">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="8d75d-140">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d75d-140">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="8d75d-141">Ajoute le logo de votre organisation à toutes les invitations générées par le complément de réunion en ligne pour Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8d75d-141">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="8d75d-142">Vous spécifiez l’URL d’une image GIF ou JPG.</span><span class="sxs-lookup"><span data-stu-id="8d75d-142">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d75d-143">HelpURL</span><span class="sxs-lookup"><span data-stu-id="8d75d-143">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="8d75d-144">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d75d-144">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="8d75d-145">Ajoute l’URL d’aide ou de support de votre organisation à toutes les invitations générées par le complément de réunion en ligne pour Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8d75d-145">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d75d-146">LegalURL</span><span class="sxs-lookup"><span data-stu-id="8d75d-146">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="8d75d-147">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d75d-147">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="8d75d-148">Ajoute du texte légal ou du texte de la clause d’exclusion de responsabilité à toutes les invitations générées par le complément de réunion en ligne pour Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8d75d-148">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="8d75d-149">Vous spécifiez l’URL de l’emplacement de ce texte.</span><span class="sxs-lookup"><span data-stu-id="8d75d-149">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d75d-150">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="8d75d-150">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="8d75d-151">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8d75d-151">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="8d75d-152">Ajoute un pied de page personnalisé à toutes les invitations générées par le complément de réunion en ligne pour Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8d75d-152">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="8d75d-153">Vous spécifiez l’URL de l’emplacement du texte du pied de page personnalisé.</span><span class="sxs-lookup"><span data-stu-id="8d75d-153">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="8d75d-154">Paramètres de gestion des clients supprimés</span><span class="sxs-lookup"><span data-stu-id="8d75d-154">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d75d-155">Paramètre</span><span class="sxs-lookup"><span data-stu-id="8d75d-155">Parameter</span></span></th>
<th><span data-ttu-id="8d75d-156">Cmdlet Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8d75d-156">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="8d75d-157">Description</span><span class="sxs-lookup"><span data-stu-id="8d75d-157">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d75d-158">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="8d75d-158">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="8d75d-159">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="8d75d-159">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="8d75d-160">Ce paramètre est déconseillé pour une utilisation avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d75d-160">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="8d75d-161">Lorsqu’il est utilisé avec EnableEnterpriseCustomizedHelp, ce paramètre a permis à une organisation de spécifier une URL de manière à ce que, lorsque les utilisateurs cliquent sur le menu aide dans Lync, l’aide personnalisée s’affiche.</span><span class="sxs-lookup"><span data-stu-id="8d75d-161">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d75d-162">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="8d75d-162">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="8d75d-163">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="8d75d-163">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="8d75d-164">Ce paramètre est déconseillé pour une utilisation avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d75d-164">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="8d75d-165">Lorsqu’il est utilisé avec CustomizedHelpUrl, ce paramètre permet aux organisations d’afficher l’aide personnalisée.</span><span class="sxs-lookup"><span data-stu-id="8d75d-165">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d75d-166">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="8d75d-166">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="8d75d-167">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="8d75d-167">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="8d75d-168">Le paramètre EnableSQMData de la cmdlet Set-CSClientPolicy a été supprimé dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d75d-168">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="8d75d-169">À la place, vous pouvez utiliser le paramètre de stratégie de groupe des données de Gestion de la qualité logicielle (SQM, Software Quality Management) pour déterminer l’interface utilisateur de l’option d’amélioration de l’expérience utilisateur dans la page d’options Général du client Lync :</span><span class="sxs-lookup"><span data-stu-id="8d75d-169">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="8d75d-170">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="8d75d-170">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="8d75d-171">Value</span><span class="sxs-lookup"><span data-stu-id="8d75d-171">Values:</span></span></p>
<p><span data-ttu-id="8d75d-172">1 = Afficher et activer la case à cocher (l’utilisateur peut désactiver cette case à cocher)</span><span class="sxs-lookup"><span data-stu-id="8d75d-172">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="8d75d-173">0 = Désactiver la case à cocher (l’utilisateur ne peut pas remplacer cette valeur)</span><span class="sxs-lookup"><span data-stu-id="8d75d-173">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="8d75d-174">Null = La valeur est déterminée par le programme d’installation d’Office, et la case à cocher est affichée pour que les utilisateurs la définissent à leur guise</span><span class="sxs-lookup"><span data-stu-id="8d75d-174">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d75d-175">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="8d75d-175">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="8d75d-176">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="8d75d-176">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="8d75d-177">Ce paramètre est supprimé.</span><span class="sxs-lookup"><span data-stu-id="8d75d-177">This parameter has been removed.</span></span> <span data-ttu-id="8d75d-178">Au lieu de cela, lorsque vous déployez Lync Server 2013 et que vous publiez la topologie, le magasin de contacts unifié est activé par défaut pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8d75d-178">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="8d75d-179">Cela signifie que tous les contacts d’un utilisateur sont conservés dans Exchange et sont disponibles dans Lync, Outlook et Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="8d75d-179">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="8d75d-180">Vous pouvez utiliser l’applet de commande Set-CsUserServicesPolicy pour personnaliser les utilisateurs qui ont un magasin de contacts unifié disponible.</span><span class="sxs-lookup"><span data-stu-id="8d75d-180">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="8d75d-181">Vous pouvez activer les utilisateurs globalement, par site, par locataire, ou par personne ou groupe de personnes.</span><span class="sxs-lookup"><span data-stu-id="8d75d-181">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="8d75d-182">Pour plus d’informations, consultez la rubrique <a href="lync-server-2013-enable-users-for-unified-contact-store.md">activation des utilisateurs pour le magasin de contacts unifié dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8d75d-182">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d75d-183">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="8d75d-183">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="8d75d-184">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="8d75d-184">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="8d75d-185">Ce paramètre n’est pas utilisé par Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8d75d-185">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="8d75d-186">Dans les précédentes versions, il spécifiait la fréquence à laquelle le client récupérait des données MAPI à partir de dossiers publics Exchange.</span><span class="sxs-lookup"><span data-stu-id="8d75d-186">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d75d-187">DisableICE</span><span class="sxs-lookup"><span data-stu-id="8d75d-187">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="8d75d-188">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="8d75d-188">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="8d75d-189">Ce paramètre a été déconseillé dans Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8d75d-189">This parameter was deprecated in Lync 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

