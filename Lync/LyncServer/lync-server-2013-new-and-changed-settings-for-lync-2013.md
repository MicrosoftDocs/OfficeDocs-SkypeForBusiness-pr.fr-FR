---
title: 'Lync Server 2013 : paramètres nouveaux et modifiés pour Lync 2013'
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
ms.openlocfilehash: 5aa98f8935a692f06b78db523e4e109e8cba9ddf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505431"
---
# <a name="new-and-changed-settings-for-lync-2013"></a>Paramètres nouveaux et modifiés pour Lync 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-12-05_

Cette rubrique traite des modifications apportées aux applets de commande Lync Server Management Shell qui sont directement liées à la gestion des clients. Lync Server 2013 introduit plusieurs nouveaux paramètres et déprécie les paramètres des fonctionnalités qui peuvent être configurées par d’autres moyens.

<div>

## <a name="new-client-management-parameters"></a>Nouveau paramètres de gestion des clients


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nouveau</th>
<th>Cmdlet Lync Server Management Shell</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Lorsque ce paramètre est défini sur true, le suivi de logiciel est activé dans Lync ; Lorsque la valeur est false, le suivi de logiciel est désactivé. Le suivi des logiciels implique de conserver un enregistrement détaillé de tous les éléments qu’un programme effectue (y compris les appels d’API de suivi). Le suivi est principalement utile aux développeurs et au personnel de support des applications. Ce paramètre équivaut au paramètre de stratégie de groupe Communications Server 2007 R2 &quot; activer le suivi pour Communicator. &quot; Les paramètres sont les suivants :</p>
<ul>
<li><p>Off = Le suivi est désactivé et l’utilisateur ne peut pas modifier le paramètre.</p></li>
<li><p>Light = Un suivi minimal est assuré et l’utilisateur ne peut pas modifier ce paramètre.</p></li>
<li><p>On = Un suivi documenté est assuré et l’utilisateur ne peut pas modifier ce paramètre.</p></li>
</ul>
<p>Par défaut, TracingLevel a la valeur null. Cela signifie qu’un suivi minimal est assuré, mais que l’utilisateur peut activer ou désactiver ce suivi minimal.</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Lorsque la valeur est True ($True), les flux audio et vidéo peuvent être isolés du reste du trafic réseau. Les périphériques clients peuvent alors les coder et les décoder localement. La redirection de médias se traduit généralement par une moindre utilisation de la bande passante, une plus grande extensibilité du serveur et une expérience utilisateur optimisée par rapport aux techniques similaires telles que l’accès à distance des périphériques ou la compression codec.</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>Lorsque la valeur est true, toutes les réunions Lync sont traitées comme des &quot; grandes réunions. &quot; Avec une grande réunion, des restrictions sont placées sur le nombre de notifications envoyées aux participants, en plus de la taille de la liste de réunions qui est transmise par défaut.</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>Quand la valeur est True ($True), les utilisateurs ne sont pas en mesure d’ajouter des annotations à des diapositives PowerPoint utilisées dans une conférence. Cependant, (en fonction de la valeur de la propriété AllowAnnotations), les utilisateurs ont toujours accès aux autres fonctionnalités de tableau blanc. La valeur par défaut est False, ce qui signifie que les annotations PowerPoint sont autorisées.</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>Quand la valeur est True (valeur par défaut), tout bloc-notes OneNote ouvert lié à la conférence est automatiquement mis à jour avec des informations telles que les participants à la conférence et les détails sur le contenu partagé pendant la conférence.</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Utilisé avec les autres nouveaux paramètres CsMeetingConfiguration pour personnaliser les invitations aux réunions générées par le complément de réunion en ligne pour Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Ajoute le logo de votre organisation à toutes les invitations générées par le complément de réunion en ligne pour Lync 2013. Vous spécifiez l’URL d’une image GIF ou JPG.</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Ajoute l’URL d’aide ou de support de votre organisation à toutes les invitations générées par le complément de réunion en ligne pour Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Ajoute du texte légal ou du texte de la clause d’exclusion de responsabilité à toutes les invitations générées par le complément de réunion en ligne pour Lync 2013. Vous spécifiez l’URL de l’emplacement de ce texte.</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Ajoute un pied de page personnalisé à toutes les invitations générées par le complément de réunion en ligne pour Lync 2013. Vous spécifiez l’URL de l’emplacement du texte du pied de page personnalisé.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a>Paramètres de gestion des clients supprimés


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètre</th>
<th>Cmdlet Lync Server Management Shell</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustomizedHelpUrl</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Ce paramètre est déconseillé pour une utilisation avec Lync Server 2013. Lorsqu’il est utilisé avec EnableEnterpriseCustomizedHelp, ce paramètre a permis à une organisation de spécifier une URL de manière à ce que, lorsque les utilisateurs cliquent sur le menu aide dans Lync, l’aide personnalisée s’affiche.</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Ce paramètre est déconseillé pour une utilisation avec Lync Server 2013. Lorsqu’il est utilisé avec CustomizedHelpUrl, ce paramètre permet aux organisations d’afficher l’aide personnalisée.</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Le paramètre EnableSQMData de la cmdlet Set-CSClientPolicy a été supprimé dans Lync Server 2013. À la place, vous pouvez utiliser le paramètre de stratégie de groupe des données de Gestion de la qualité logicielle (SQM, Software Quality Management) pour déterminer l’interface utilisateur de l’option d’amélioration de l’expérience utilisateur dans la page d’options Général du client Lync :</p>
<p>HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>Value</p>
<p>1 = Afficher et activer la case à cocher (l’utilisateur peut désactiver cette case à cocher)</p>
<p>0 = Désactiver la case à cocher (l’utilisateur ne peut pas remplacer cette valeur)</p>
<p>Null = La valeur est déterminée par le programme d’installation d’Office, et la case à cocher est affichée pour que les utilisateurs la définissent à leur guise</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Ce paramètre est supprimé. Au lieu de cela, lorsque vous déployez Lync Server 2013 et que vous publiez la topologie, le magasin de contacts unifié est activé par défaut pour tous les utilisateurs. Cela signifie que tous les contacts d’un utilisateur sont conservés dans Exchange et sont disponibles dans Lync, Outlook et Outlook Web Access. Vous pouvez utiliser l’applet de commande Set-CsUserServicesPolicy pour personnaliser les utilisateurs qui ont un magasin de contacts unifié disponible. Vous pouvez activer les utilisateurs globalement, par site, par locataire, ou par personne ou groupe de personnes. Pour plus d’informations, consultez la rubrique <a href="lync-server-2013-enable-users-for-unified-contact-store.md">activation des utilisateurs pour le magasin de contacts unifié dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Ce paramètre n’est pas utilisé par Lync 2013. Dans les précédentes versions, il spécifiait la fréquence à laquelle le client récupérait des données MAPI à partir de dossiers publics Exchange.</p></td>
</tr>
<tr class="even">
<td><p>DisableICE</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Ce paramètre a été déconseillé dans Lync 2013.</p></td>
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

