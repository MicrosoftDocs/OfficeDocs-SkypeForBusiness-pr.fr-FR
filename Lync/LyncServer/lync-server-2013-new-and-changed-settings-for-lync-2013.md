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
ms.openlocfilehash: fb5366f7e3d4c2aba81b5b8b25873ea22d54c3a6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a>Paramètres nouveaux et modifiés pour Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-12-05_

Cette rubrique traite des modifications apportées aux applets de applet Lync Server Management Shell qui sont associées directement à la gestion des clients. Lync Server 2013 introduit plusieurs nouveaux paramètres et déprécie les paramètres des fonctionnalités qui peuvent être configurées par le biais d’autres moyens.

<div>

## <a name="new-client-management-parameters"></a>Nouveaux paramètres de gestion des clients


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
<td><p>Lorsque cette propriété est définie sur true, le suivi logiciel est activé dans Lync ; Lorsque la valeur est définie sur false, le suivi logiciel est désactivé. Le suivi logiciel implique de maintenir un enregistrement détaillé de tout ce qu’un programme effectue (y compris les appels d’API de suivi). Le suivi est particulièrement utile pour les développeurs et pour le personnel de support de l’application. Ce paramètre est équivalent au paramètre &quot;de stratégie de groupe Communications Server 2007 R2 activez le suivi pour Communicator. &quot; Les paramètres sont les suivants :</p>
<ul>
<li><p>Désactivé = le suivi est désactivé et l’utilisateur ne peut pas modifier ce paramètre.</p></li>
<li><p>Clair = le suivi minimal est effectué et l’utilisateur ne peut pas modifier ce paramètre.</p></li>
<li><p>On = suivi détaillé est effectué et l’utilisateur ne peut pas modifier ce paramètre.</p></li>
</ul>
<p>Par défaut, TracingLevel est défini sur une valeur null. Cela signifie qu’un suivi minimal est effectué, mais que l’utilisateur peut activer ou désactiver ce suivi minimal.</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Lorsque ce paramètre est défini sur true ($True) autorise la séparation des flux audio et vidéo à partir du trafic réseau, cela permet aux appareils clients de procéder au codage et au décodage de l’audio et de la vidéo localement. La redirection de média entraîne généralement une utilisation plus lente de la bande passante, une extensibilité du serveur plus élevée et une meilleure interface utilisateur par rapport aux techniques similaires, telles que l’accès à l’appareil distant ou la compression du codec.</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>Lorsque cette propriété est définie sur true, toutes les réunions &quot;Lync sont considérées comme des réunions de grande taille. &quot; Dans une grande réunion, des restrictions sont placées sur le nombre de notifications envoyées aux participants, en plus de la taille de la liste de la réunion qui est transmise par défaut.</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>Lorsque cette propriété est définie sur true ($True), les utilisateurs ne peuvent pas ajouter d’annotations aux diapositives PowerPoint utilisées dans une conférence. Toutefois, en fonction de la valeur de la propriété AllowAnnotations, les utilisateurs auront toujours accès à d’autres fonctionnalités de tableau blanc. La valeur par défaut est false, ce qui signifie que les annotations PowerPoint sont autorisées.</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>Lorsque cette propriété est définie sur true (valeur par défaut), tous les blocs-notes OneNote ouverts liés à la Conférence seront automatiquement mis à jour avec des informations telles que des participants à la Conférence et des détails sur le contenu partagé pendant la Conférence.</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Utilisé avec les autres nouveaux paramètres de CsMeetingConfiguration pour personnaliser les invitations aux réunions générées par le complément réunion en ligne pour Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Ajoute le logo de votre organisation à toutes les invitations générées par le complément réunion en ligne pour Lync 2013. Vous spécifiez l’URL d’une image GIF ou JPG.</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Ajoute l’adresse d’aide ou d’assistance de votre organisation à toutes les invitations générées par le complément réunion en ligne pour Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Ajoute du texte légal ou une exclusion de responsabilité à toutes les invitations générées par le complément réunion en ligne pour Lync 2013. Vous spécifiez l’URL de l’emplacement du texte.</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Ajoute un pied de page personnalisé à toutes les invitations générées par le complément réunion en ligne pour Lync 2013. Vous spécifiez l’URL de l’emplacement du texte de pied de page personnalisé.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a>Paramètres de gestion des clients déconseillés


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
<td><p>Ce paramètre a été déconseillé pour une utilisation avec Lync Server 2013. Lorsqu’il est utilisé avec EnableEnterpriseCustomizedHelp, ce paramètre a autorisé une organisation à spécifier une URL de telle sorte que lorsque les utilisateurs cliquent sur le menu aide de Lync, l’aide personnalisée s’affiche.</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Ce paramètre a été déconseillé pour une utilisation avec Lync Server 2013. Lorsqu’il est utilisé avec CustomizedHelpUrl, ce paramètre a activé les organisations pour afficher une aide personnalisée.</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Le paramètre EnableSQMData de l’applet de passe Set-CSClientPolicy a été supprimé dans Lync Server 2013. Au lieu de cela, vous pouvez utiliser le paramètre de stratégie de groupe partagé pour les données de gestion de la qualité des logiciels pour déterminer l’interface utilisateur pour l’option d’amélioration du produit dans la page d’options général du client Lync :</p>
<p>HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>Doubl</p>
<p>1 = afficher et activer la case à cocher (l’utilisateur peut désactiver la case à cocher)</p>
<p>0 = désactiver et désactiver la case à cocher (l’utilisateur ne peut pas remplacer)</p>
<p>NULL = la valeur est déterminée par le programme d’installation d’Office et la case à cocher est affichée pour que les utilisateurs puissent définir tels choix</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Ce paramètre a été supprimé. Au lieu de cela, lorsque vous déployez Lync Server 2013 et que vous publiez la topologie, le magasin de contacts unifié est activé par défaut pour tous les utilisateurs. Cela signifie que tous les contacts d’un utilisateur sont conservés dans Exchange et sont disponibles dans Lync, Outlook et Outlook Web Access. Vous pouvez utiliser l’applet de cmdlet Set-CsUserServicesPolicy pour personnaliser les utilisateurs disposant d’un magasin de contacts unifié disponible. Vous pouvez activer les utilisateurs globalement, par site, par client ou par individu ou groupe d’utilisateurs. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-enable-users-for-unified-contact-store.md">activer les utilisateurs pour le magasin de contacts unifié dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Ce paramètre n’est pas utilisé par Lync 2013. Dans les versions précédentes, ce paramètre spécifiait le nombre de fois où le client récupérait des données MAPI à partir de dossiers publics Exchange</p></td>
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

