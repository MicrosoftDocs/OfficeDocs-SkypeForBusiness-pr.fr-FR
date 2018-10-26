---
title: Paramètres nouveaux et modifiés pour Lync 2013
TOCTitle: Paramètres nouveaux et modifiés pour Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205204(v=OCS.15)
ms:contentKeyID: 49298656
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Paramètres nouveaux et modifiés pour Lync 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette rubrique décrit les modifications apportées aux applets de commande Lync Server Management Shell qui sont directement associées à la gestion des clients. Lync Server 2013 introduit plusieurs nouveaux paramètres, et suppriment certains paramètres correspondant à des fonctionnalités qui peuvent être configurées par d’autres moyens.

## Nouveau paramètres de gestion des clients


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nouveau</th>
<th>Applet de commande Lync Server Management Shell</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Lorsque la valeur est True, le suivi de logiciel est activé dans Lync. Si la valeur est False, ce dernier est désactivé. Le suivi de logiciel consiste à conserver un enregistrement détaillé de tout ce que fait le programme (y compris le suivi des appels API). En tant que tel, ce suivi n’est utile que pour les développeurs et le personnel du support aux applications. Ce paramètre équivaut au paramètre « Activer le suivi pour Office Communicator » de la stratégie de groupe Communications Server 2007 R2. Les paramètres sont les suivants :</p>
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
<td><p>Lorsque la valeur est True, toutes les réunions Lync sont considérées comme de « grandes réunions ». Avec une grande réunion, des restrictions sont placées sur le nombre de notifications envoyées aux participants, en plus de la taille de la composition de la réunion qui est transmise par défaut.</p></td>
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
<td><p>Ajoute l’URL d’aide ou d’assistance de votre organisation à toutes les invitations générées par le complément de réunion en ligne pour Lync 2013.</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Ajoute des informations légales ou un texte d’exclusion de responsabilité à toutes les invitations générées par le complément de réunion en ligne pour Lync 2013. Vous spécifiez l’URL de l’emplacement de ce texte.</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Ajoute un pied de page personnalisé à toutes les invitations générées par le complément de réunion en ligne pour Lync 2013. Vous spécifiez l’URL de l’emplacement du texte du pied de page personnalisé.</p></td>
</tr>
<tr class="odd">
<td><p>IsPublicDisclosureAllowed</p></td>
<td><p>CsWebServiceConfiguration</p></td>
<td><p>Active la nouvelle version 2013 de Lync Web App. La nouvelle version de Lync Web App n’est pas activée par défaut et doit être activée par l’administrateur.</p></td>
</tr>
</tbody>
</table>


## Paramètres de gestion des clients supprimés


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètre</th>
<th>Applet de commande Lync Server Management Shell</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Le paramètre EnableSQMData de l’applet de commande Set-CSClientPolicy a été supprimé dans Lync Server 2013. À la place, vous pouvez utiliser le paramètre de stratégie de groupe des données de Gestion de la qualité logicielle (SQM, Software Quality Management) pour déterminer l’interface utilisateur de l’option d’amélioration de l’expérience utilisateur dans la page d’options Général du client Lync :</p>
<p>HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>Valeurs :</p>
<p>1 = Afficher et activer la case à cocher (l’utilisateur peut désactiver cette case à cocher)</p>
<p>0 = Désactiver la case à cocher (l’utilisateur ne peut pas remplacer cette valeur)</p>
<p>Null = La valeur est déterminée par le programme d’installation d’Office, et la case à cocher est affichée pour que les utilisateurs la définissent à leur guise</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Ce paramètre est supprimé. À la place, lorsque vous déployez Lync Server 2013 et publiez la topologie, le magasin de contacts unifié est activé par défaut pour tous les utilisateurs. Cela signifie que tous les contacts d’un utilisateur sont conservés dans Exchange et sont disponibles dans Lync, Outlook et Outlook Web Access. Vous pouvez utiliser l’applet de commande Set-CsUserServicesPolicy pour personnaliser les utilisateurs qui ont un magasin de contacts unifié disponible. Vous pouvez activer les utilisateurs globalement, par site, par locataire, ou par personne ou groupe de personnes. Pour plus d’informations, voir <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Activation des utilisateurs pour le magasin de contacts unifié dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Ce paramètre n’est pas utilisé par Lync 2013. Dans les précédentes versions, il spécifiait la fréquence à laquelle le client récupérait des données MAPI à partir de dossiers publics Exchange.</p></td>
</tr>
</tbody>
</table>

