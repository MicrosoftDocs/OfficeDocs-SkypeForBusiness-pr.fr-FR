---
title: 'Lync Server 2013 : Configurations hybrides prises en charge'
TOCTitle: Configurations hybrides prises en charge
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945633(v=OCS.15)
ms:contentKeyID: 53095431
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurations hybrides Lync Server 2013 prises en charge

 

_**Dernière rubrique modifiée :** 2016-12-08_

Vous pouvez configurer les déploiements Lync Server 2013 en vue d’une intégration à Microsoft Exchange Server 2010, Microsoft Exchange Server 2013 et SharePoint Server, à la fois en local et en ligne. Les fonctionnalités répertoriées dans le tableau suivant sont prises en charge avec tous les clients, sauf indication contraire. Pour plus d’informations sur la prise en charge des clients, reportez-vous à [Tableau de comparaison des clients pour Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) et Tableaux de comparaison des clients Lync Online à l’adresse [Clients for Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902).

## Intégration à Exchange Server

Le tableau ci-dessous répertorie les fonctionnalités prises en charge dans un déploiement hybride intégré à Microsoft Exchange Server.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Exchange en local</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 en local</strong></p></td>
<td><ul>
<li><p>Messagerie instantanée/présence dans Outlook</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-im-and-presence.md">Messagerie instantanée et présence dans Lync Server 2013</a></p></li>
<li><p>Planifier et rejoindre des réunions en ligne à l’aide d’Outlook</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Intégration de Microsoft Lync Server 2013 à Microsoft Exchange Server 2013</a></p></li>
<li><p>Messagerie instantanée/présence dans Outlook Web App</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">Configuration de Microsoft Lync Server 2013 dans un environnement intersites</a></p></li>
<li><p>Planifier et rejoindre des réunions en ligne à l’aide de Outlook Web App</p></li>
<li><p>Messagerie instantanée/présence dans les clients mobiles</p></li>
<li><p>Rejoindre des réunions en ligne dans les clients mobiles</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-deploying-mobility.md">Déploiement de la mobilité dans Lync Server 2013</a></p></li>
<li><p>Publier le statut en fonction des informations de disponibilité du calendrier Outlook</p></li>
<li><p>Liste des contacts (via le magasin de contacts unifié)</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Configuration de Microsoft Lync Server 2013 pour l’utilisation du magasin de contact unifié</a></p>

> [!NOTE]  
> Nécessite Exchange 2013.<br />
Un client de bureau Lync 2013 est requis.

</li>
<li><p>Photo de contact haute résolution dans le client Lync 2013 et Lync Web App.</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Configuration de l’utilisation de photos haute résolution dans Microsoft Lync Server 2013</a></p>

> [!NOTE]  
> Nécessite Exchange 2013.

</li>
<li><p>Délégation de réunion</p>
<p>Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt ou hébergés en local.</p></li>
<li><p>L’historique des conversations manquées et les journaux des appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur</p></li>
<li><p>Archivage de contenu (messagerie instantanée et réunion) dans Exchange</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-deployment-checklist-for-archiving.md">Liste de vérification du déploiement pour l’archivage dans Lync Server 2013</a></p>

> [!NOTE]  
> Nécessite Exchange 2013.

</li>
<li><p>Parcourir le contenu archivé</p>

> [!NOTE]  
> Nécessite Exchange 2013.

</li>
<li><p>Messagerie vocale</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">Déploiement de la messagerie unifiée Exchange locale pour fournir la messagerie vocale Lync Server 2013</a></p></li>
</ul></td>
<td><ul>
<li><p>Messagerie instantanée/présence dans Outlook</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuration de l’intégration de Lync Server 2013 local avec Exchange Online</a></p></li>
<li><p>Planifier et rejoindre une réunion en ligne à l’aide d’Outlook</p></li>
<li><p>Messagerie instantanée/présence dans OWA</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuration de l’intégration de Lync Server 2013 local avec Exchange Online</a></p></li>
<li><p>Planifier et rejoindre une réunion en ligne à partir d’Outlook Web App</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuration de l’intégration de Lync Server 2013 local avec Exchange Online</a></p></li>
<li><p>Messagerie instantanée/présence dans les clients mobiles</p></li>
<li><p>Rejoindre une réunion en ligne dans les clients mobiles</p></li>
<li><p>Publier le statut en fonction des informations de disponibilité du calendrier Outlook</p></li>
<li><p>Liste des contacts (via le magasin de contacts unifié). Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Configuration de Microsoft Lync Server 2013 pour l’utilisation du magasin de contact unifié</a></p>

> [!NOTE]  
> Lync Server 2013 uniquement. Un client de bureau Lync 2013 est requis.

</li>
<li><p>Photo de contact haute résolution dans le client Lync 2013 et Lync Web App.</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Configuration de l’utilisation de photos haute résolution dans Microsoft Lync Server 2013</a>.</p></li>
<li><p>Délégation de réunion</p>
<p>Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt ou hébergés en local.</p></li>
<li><p>L’historique des conversations manquées et les journaux des appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur</p></li>
<li><p>Archivage de contenu (messagerie instantanée et réunion) dans Exchange.</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-deployment-checklist-for-archiving.md">Liste de vérification du déploiement pour l’archivage dans Lync Server 2013</a></p></li>
<li><p>Parcourir le contenu archivé. Pour plus d’informations, reportez-vous à <a href="http://go.microsoft.com/fwlink/p/?linkid=285448">Configurer Exchange pour le centre de découverte électronique SharePoint</a></p></li>
<li><p>Messagerie vocale. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">Mise à disposition de la messagerie vocale Lync Server 2013 aux utilisateurs sur la messagerie unifiée Exchange hébergée</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Messagerie instantanée et présence dans Outlook</p></li>
<li><p>Planifier et rejoindre des réunions en ligne à l’aide d’Outlook</p></li>
<li><p>Messagerie instantanée/présence dans les clients mobiles</p></li>
<li><p>L’historique des conversations manquées et les journaux des appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur</p></li>
<li><p>Photo de contact haute résolution dans le client Lync 2013.</p>

> [!NOTE]  
> Nécessite Microsoft Exchange Server 2013. Non pris en charge dans Lync Web App lorsque les utilisateurs sont hébergés sur Skype Entreprise Online.

</li>
<li><p>Rejoindre une réunion en ligne dans les clients mobiles</p></li>
<li><p>Publier le statut en fonction des informations de disponibilité du calendrier Outlook</p></li>
<li><p>Délégation de réunion</p>
<p>Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt ou hébergés en local.</p></li>
</ul></td>
<td><ul>
<li><p>Messagerie instantanée/présence dans Outlook</p></li>
<li><p>Planifier et rejoindre des réunions en ligne à l’aide d’Outlook</p></li>
<li><p>Messagerie instantanée/présence dans Outlook Web App</p></li>
<li><p>Planifier et rejoindre une réunion en ligne à partir d’Outlook Web App</p></li>
<li><p>Messagerie instantanée/présence dans les clients mobiles</p></li>
<li><p>Rejoindre une réunion en ligne dans les clients mobiles</p></li>
<li><p>Publier le statut en fonction des informations de disponibilité du calendrier Outlook</p></li>
<li><p>L’historique des conversations manquées et les journaux des appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur</p></li>
<li><p>Liste des contacts (via le magasin de contacts unifié)</p>

> [!NOTE]  
> Client Lync Server 2013 requis

</li>
<li><p>Photo de contact haute résolution dans le client Lync 2013 et Lync Web App.</p></li>
<li><p>Délégation de réunion</p>
<p>Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt ou hébergés en local.</p></li>
<li><p>Archivage de contenu (messagerie instantanée et réunion) dans Exchange</p></li>
<li><p>Parcourir le contenu archivé</p></li>
<li><p>Messagerie vocale</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Intégration à SharePoint

Le tableau ci-dessous répertorie les fonctionnalités prises en charge dans un déploiement hybride de Lync Server 2013 intégré à SharePoint.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>SharePoint en local</th>
<th>SharePoint en ligne</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 en local</strong></p></td>
<td><ul>
<li><p>Recherche de compétences</p></li>
<li><p>Présence dans SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>Présence dans SharePoint</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Présence dans SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>Présence dans SharePoint</p></li>
</ul></td>
</tr>
</tbody>
</table>

