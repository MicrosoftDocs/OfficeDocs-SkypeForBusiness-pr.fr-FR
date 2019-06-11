---
title: 'Lync Server 2013: paramètres nouveaux et modifiés pour Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675997e815dc80ec173e75ca68358ef23c12f380
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="05cef-102">Paramètres nouveaux et modifiés pour Lync 2013</span><span class="sxs-lookup"><span data-stu-id="05cef-102">New and changed settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05cef-103">_**Dernière modification de la rubrique:** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="05cef-103">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="05cef-104">Cette rubrique traite des modifications apportées aux applets de applet Lync Server Management Shell qui sont associées directement à la gestion des clients.</span><span class="sxs-lookup"><span data-stu-id="05cef-104">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="05cef-105">Lync Server 2013 introduit plusieurs nouveaux paramètres et déprécie les paramètres des fonctionnalités qui peuvent être configurées par le biais d’autres moyens.</span><span class="sxs-lookup"><span data-stu-id="05cef-105">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="05cef-106">Nouveaux paramètres de gestion des clients</span><span class="sxs-lookup"><span data-stu-id="05cef-106">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05cef-107">Nouveau</span><span class="sxs-lookup"><span data-stu-id="05cef-107">New</span></span></th>
<th><span data-ttu-id="05cef-108">Cmdlet Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="05cef-108">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="05cef-109">Description</span><span class="sxs-lookup"><span data-stu-id="05cef-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05cef-110">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="05cef-110">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="05cef-111">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="05cef-111">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="05cef-112">Lorsque cette propriété est définie sur true, le suivi logiciel est activé dans Lync; Lorsque la valeur est définie sur false, le suivi logiciel est désactivé.</span><span class="sxs-lookup"><span data-stu-id="05cef-112">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="05cef-113">Le suivi logiciel implique de maintenir un enregistrement détaillé de tout ce qu’un programme effectue (y compris les appels d’API de suivi).</span><span class="sxs-lookup"><span data-stu-id="05cef-113">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="05cef-114">Le suivi est particulièrement utile pour les développeurs et pour le personnel de support de l’application. Ce paramètre est équivalent au paramètre &quot;de stratégie de groupe Communications Server 2007 R2 activez le suivi pour Communicator. &quot; Les paramètres sont les suivants:</span><span class="sxs-lookup"><span data-stu-id="05cef-114">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="05cef-115">Désactivé = le suivi est désactivé et l’utilisateur ne peut pas modifier ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="05cef-115">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="05cef-116">Clair = le suivi minimal est effectué et l’utilisateur ne peut pas modifier ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="05cef-116">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="05cef-117">On = suivi détaillé est effectué et l’utilisateur ne peut pas modifier ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="05cef-117">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="05cef-118">Par défaut, TracingLevel est défini sur une valeur null.</span><span class="sxs-lookup"><span data-stu-id="05cef-118">By default TracingLevel is set to a null value.</span></span> <span data-ttu-id="05cef-119">Cela signifie qu’un suivi minimal est effectué, mais que l’utilisateur peut activer ou désactiver ce suivi minimal.</span><span class="sxs-lookup"><span data-stu-id="05cef-119">That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05cef-120">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="05cef-120">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="05cef-121">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="05cef-121">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="05cef-122">Lorsque ce paramètre est défini sur true ($True) autorise la séparation des flux audio et vidéo à partir du trafic réseau, cela permet aux appareils clients de procéder au codage et au décodage de l’audio et de la vidéo localement.</span><span class="sxs-lookup"><span data-stu-id="05cef-122">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally.</span></span> <span data-ttu-id="05cef-123">La redirection de média entraîne généralement une utilisation plus lente de la bande passante, une extensibilité du serveur plus élevée et une meilleure interface utilisateur par rapport aux techniques similaires, telles que l’accès à l’appareil distant ou la compression du codec.</span><span class="sxs-lookup"><span data-stu-id="05cef-123">Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05cef-124">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="05cef-124">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="05cef-125">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="05cef-125">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="05cef-126">Lorsque cette propriété est définie sur true, toutes les réunions &quot;Lync sont considérées comme des réunions de grande taille. &quot; Dans une grande réunion, des restrictions sont placées sur le nombre de notifications envoyées aux participants, en plus de la taille de la liste de la réunion qui est transmise par défaut.</span><span class="sxs-lookup"><span data-stu-id="05cef-126">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05cef-127">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="05cef-127">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="05cef-128">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="05cef-128">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="05cef-129">Lorsque cette propriété est définie sur true ($True), les utilisateurs ne peuvent pas ajouter d’annotations aux diapositives PowerPoint utilisées dans une conférence.</span><span class="sxs-lookup"><span data-stu-id="05cef-129">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference.</span></span> <span data-ttu-id="05cef-130">Toutefois, en fonction de la valeur de la propriété AllowAnnotations, les utilisateurs auront toujours accès à d’autres fonctionnalités de tableau blanc.</span><span class="sxs-lookup"><span data-stu-id="05cef-130">However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features.</span></span> <span data-ttu-id="05cef-131">La valeur par défaut est false, ce qui signifie que les annotations PowerPoint sont autorisées.</span><span class="sxs-lookup"><span data-stu-id="05cef-131">The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05cef-132">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="05cef-132">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="05cef-133">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="05cef-133">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="05cef-134">Lorsque cette propriété est définie sur true (valeur par défaut), tous les blocs-notes OneNote ouverts liés à la Conférence seront automatiquement mis à jour avec des informations telles que des participants à la Conférence et des détails sur le contenu partagé pendant la Conférence.</span><span class="sxs-lookup"><span data-stu-id="05cef-134">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05cef-135">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="05cef-135">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="05cef-136">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="05cef-136">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="05cef-137">Utilisé avec les autres nouveaux paramètres de CsMeetingConfiguration pour personnaliser les invitations aux réunions générées par le complément réunion en ligne pour Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="05cef-137">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05cef-138">LogoURL</span><span class="sxs-lookup"><span data-stu-id="05cef-138">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="05cef-139">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="05cef-139">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="05cef-140">Ajoute le logo de votre organisation à toutes les invitations générées par le complément réunion en ligne pour Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="05cef-140">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="05cef-141">Vous spécifiez l’URL d’une image GIF ou JPG.</span><span class="sxs-lookup"><span data-stu-id="05cef-141">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05cef-142">HelpURL</span><span class="sxs-lookup"><span data-stu-id="05cef-142">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="05cef-143">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="05cef-143">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="05cef-144">Ajoute l’adresse d’aide ou d’assistance de votre organisation à toutes les invitations générées par le complément réunion en ligne pour Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="05cef-144">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05cef-145">LegalURL</span><span class="sxs-lookup"><span data-stu-id="05cef-145">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="05cef-146">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="05cef-146">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="05cef-147">Ajoute du texte légal ou une exclusion de responsabilité à toutes les invitations générées par le complément réunion en ligne pour Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="05cef-147">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="05cef-148">Vous spécifiez l’URL de l’emplacement du texte.</span><span class="sxs-lookup"><span data-stu-id="05cef-148">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05cef-149">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="05cef-149">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="05cef-150">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="05cef-150">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="05cef-151">Ajoute un pied de page personnalisé à toutes les invitations générées par le complément réunion en ligne pour Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="05cef-151">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="05cef-152">Vous spécifiez l’URL de l’emplacement du texte de pied de page personnalisé.</span><span class="sxs-lookup"><span data-stu-id="05cef-152">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="05cef-153">Paramètres de gestion des clients déconseillés</span><span class="sxs-lookup"><span data-stu-id="05cef-153">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05cef-154">Paramètre</span><span class="sxs-lookup"><span data-stu-id="05cef-154">Parameter</span></span></th>
<th><span data-ttu-id="05cef-155">Cmdlet Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="05cef-155">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="05cef-156">Description</span><span class="sxs-lookup"><span data-stu-id="05cef-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05cef-157">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="05cef-157">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="05cef-158">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="05cef-158">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="05cef-159">Ce paramètre a été déconseillé pour une utilisation avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05cef-159">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="05cef-160">Lorsqu’il est utilisé avec EnableEnterpriseCustomizedHelp, ce paramètre a autorisé une organisation à spécifier une URL de telle sorte que lorsque les utilisateurs cliquent sur le menu aide de Lync, l’aide personnalisée s’affiche.</span><span class="sxs-lookup"><span data-stu-id="05cef-160">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05cef-161">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="05cef-161">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="05cef-162">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="05cef-162">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="05cef-163">Ce paramètre a été déconseillé pour une utilisation avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05cef-163">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="05cef-164">Lorsqu’il est utilisé avec CustomizedHelpUrl, ce paramètre a activé les organisations pour afficher une aide personnalisée.</span><span class="sxs-lookup"><span data-stu-id="05cef-164">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05cef-165">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="05cef-165">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="05cef-166">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="05cef-166">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="05cef-167">Le paramètre EnableSQMData de l’applet de passe Set-CSClientPolicy a été supprimé dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05cef-167">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="05cef-168">Au lieu de cela, vous pouvez utiliser le paramètre de stratégie de groupe partagé pour les données de gestion de la qualité des logiciels pour déterminer l’interface utilisateur pour l’option d’amélioration du produit dans la page d’options général du client Lync:</span><span class="sxs-lookup"><span data-stu-id="05cef-168">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="05cef-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="05cef-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="05cef-170">Doubl</span><span class="sxs-lookup"><span data-stu-id="05cef-170">Values:</span></span></p>
<p><span data-ttu-id="05cef-171">1 = afficher et activer la case à cocher (l’utilisateur peut désactiver la case à cocher)</span><span class="sxs-lookup"><span data-stu-id="05cef-171">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="05cef-172">0 = désactiver et désactiver la case à cocher (l’utilisateur ne peut pas remplacer)</span><span class="sxs-lookup"><span data-stu-id="05cef-172">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="05cef-173">NULL = la valeur est déterminée par le programme d’installation d’Office et la case à cocher est affichée pour que les utilisateurs puissent définir tels choix</span><span class="sxs-lookup"><span data-stu-id="05cef-173">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05cef-174">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="05cef-174">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="05cef-175">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="05cef-175">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="05cef-176">Ce paramètre a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="05cef-176">This parameter has been removed.</span></span> <span data-ttu-id="05cef-177">Au lieu de cela, lorsque vous déployez Lync Server 2013 et que vous publiez la topologie, le magasin de contacts unifié est activé par défaut pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="05cef-177">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="05cef-178">Cela signifie que tous les contacts d’un utilisateur sont conservés dans Exchange et sont disponibles dans Lync, Outlook et Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="05cef-178">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="05cef-179">Vous pouvez utiliser l’applet de cmdlet Set-CsUserServicesPolicy pour personnaliser les utilisateurs disposant d’un magasin de contacts unifié disponible.</span><span class="sxs-lookup"><span data-stu-id="05cef-179">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="05cef-180">Vous pouvez activer les utilisateurs globalement, par site, par client ou par individu ou groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="05cef-180">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="05cef-181">Pour plus d’informations, reportez-vous à <a href="lync-server-2013-enable-users-for-unified-contact-store.md">activer les utilisateurs pour le magasin de contacts unifié dans Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="05cef-181">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05cef-182">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="05cef-182">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="05cef-183">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="05cef-183">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="05cef-184">Ce paramètre n’est pas utilisé par Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="05cef-184">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="05cef-185">Dans les versions précédentes, ce paramètre spécifiait le nombre de fois où le client récupérait des données MAPI à partir de dossiers publics Exchange</span><span class="sxs-lookup"><span data-stu-id="05cef-185">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05cef-186">DisableICE</span><span class="sxs-lookup"><span data-stu-id="05cef-186">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="05cef-187">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="05cef-187">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="05cef-188">Ce paramètre a été déconseillé dans Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="05cef-188">This parameter was deprecated in Lync 2013.</span></span></p></td>
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

