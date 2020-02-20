---
title: 'Lync Server 2013 : configurations hybrides prises en charge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c757fc19bd82fbf1ae3096bb4a8ac8982f9035b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a>Configurations hybrides Lync Server 2013 prises en charge

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-05-10_

Vous pouvez configurer les déploiements Lync Server 2013 en vue de l’intégration à Microsoft Exchange Server 2010 et Microsoft Exchange Server 2013 et SharePoint Server, en local et en ligne. Sauf indication contraire, les fonctionnalités répertoriées dans le tableau suivant sont prises en charge avec tous les clients. Pour plus d’informations sur la prise en charge des clients, reportez-vous aux [tableaux de comparaison des clients pour Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) et Skype entreprise Online-tableaux de comparaison des [clients pour Skype entreprise Online](https://go.microsoft.com/fwlink/p/?linkid=281902).

<div>

## <a name="integration-with-exchange-server"></a>Intégration à Exchange Server

Le tableau suivant répertorie les fonctionnalités prises en charge dans un déploiement hybride lors de l’intégration à Microsoft Exchange Server.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Exchange local</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 en local</strong></p></td>
<td><ul>
<li><p>Messagerie instantanée/présence dans Outlook</p>
<p>Pour plus d’informations, consultez la rubrique <a href="lync-server-2013-im-and-presence.md">messagerie instantanée et présence dans Lync Server 2013</a></p></li>
<li><p>Planification et participation à des réunions en ligne via Outlook</p>
<p>Pour plus d’informations, reportez-vous à l' <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">intégration de Microsoft Lync server 2013 et de Microsoft Exchange server 2013</a></p></li>
<li><p>Messagerie instantanée/présence dans Outlook Web App</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">la rubrique Configuration de Microsoft Lync Server 2013 dans un environnement</a> intersite</p></li>
<li><p>Planification et participation à des réunions en ligne via Outlook Web App</p></li>
<li><p>Messagerie instantanée/présence dans les clients mobiles</p></li>
<li><p>Participer à des réunions en ligne dans les clients mobiles</p>
<p>Pour plus d’informations, reportez-vous à la rubrique <a href="lync-server-2013-deploying-mobility.md">Deploying Mobility in Lync Server 2013</a></p></li>
<li><p>Publier le statut en fonction des informations de disponibilité du calendrier Outlook</p></li>
<li><p>Liste de contacts (par le biais du magasin de contacts unifié)</p>
<p>Pour plus d’informations, reportez-vous <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">à la rubrique Configuring Microsoft Lync Server 2013 to use the Unified Contact Store</a> .</p>
<div>

> [!NOTE]  
> Nécessite Exchange 2013.<BR>Un client de bureau Lync 2013 est requis.


</div></li>
<li><p>Photo de contact haute résolution dans Lync 2013 client et Lync Web App.</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">la rubrique Configuration de l’utilisation de photos haute résolution dans Microsoft Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Nécessite Exchange 2013.


</div></li>
<li><p>Délégation de réunion</p>
<p>Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt, ou tous les deux sont hébergés en local.</p></li>
<li><p>L’historique des conversations manquées et les journaux d’appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur</p></li>
<li><p>Archivage de contenu (messagerie instantanée et réunion) dans Exchange</p>
<p>Pour plus d’informations, consultez la rubrique <a href="lync-server-2013-deployment-checklist-for-archiving.md">relative à la liste de vérification du déploiement pour l’archivage dans Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Nécessite Exchange 2013.


</div></li>
<li><p>Recherche de contenu archivé</p>
<div>

> [!NOTE]  
> Nécessite Exchange 2013.


</div></li>
<li><p>Messagerie vocale</p>
<p>Pour plus d’informations, reportez-vous à la rubrique <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">déploiement de la messagerie unifiée Exchange locale pour fournir la messagerie vocale Lync Server 2013</a></p></li>
</ul></td>
<td><ul>
<li><p>Messagerie instantanée/présence dans Outlook</p>
<p>Pour plus d’informations, reportez-vous à la rubrique <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 Integration with Exchange Online</a> .</p></li>
<li><p>Planifier et participer à une réunion en ligne via Outlook</p></li>
<li><p>Messagerie instantanée/présence dans OWA</p>
<p>Pour plus d’informations, reportez-vous à la rubrique <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 Integration with Exchange Online</a> .</p></li>
<li><p>Planifier et participer à une réunion en ligne à partir d’Outlook Web App</p>
<p>Pour plus d’informations, reportez-vous à la rubrique <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises Lync Server 2013 Integration with Exchange Online</a> .</p></li>
<li><p>Messagerie instantanée/présence dans les clients mobiles</p></li>
<li><p>Participer à une réunion en ligne dans les clients mobiles</p></li>
<li><p>Publier le statut en fonction des informations de disponibilité du calendrier Outlook</p></li>
<li><p>Liste de contacts (par le biais du magasin de contacts unifié). Pour plus d’informations, reportez-vous <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">à la rubrique Configuring Microsoft Lync Server 2013 to use the Unified Contact Store</a> .</p>
<div>

> [!NOTE]  
> Lync Server 2013 uniquement. Un client de bureau Lync 2013 est requis.


</div></li>
<li><p>Photo de contact haute résolution dans Lync 2013 client et Lync Web App.</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">la rubrique Configuration de l’utilisation de photos haute résolution dans Microsoft Lync Server 2013</a>.</p></li>
<li><p>Délégation de réunion</p>
<p>Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt, ou tous les deux sont hébergés en local.</p></li>
<li><p>L’historique des conversations manquées et les journaux d’appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur</p></li>
<li><p>Archivage de contenu (messagerie instantanée et réunion) dans Exchange.</p>
<p>Pour plus d’informations, consultez la rubrique <a href="lync-server-2013-deployment-checklist-for-archiving.md">relative à la liste de vérification du déploiement pour l’archivage dans Lync Server 2013</a></p></li>
<li><p>Rechercher du contenu archivé. Pour plus d’informations, reportez-vous à la rubrique <a href="https://go.microsoft.com/fwlink/p/?linkid=285448">configurer Exchange pour le centre EDiscovery SharePoint</a></p></li>
<li><p>Messagerie vocale. Pour plus d’informations, consultez la rubrique Présentation <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">de la messagerie vocale des utilisateurs Lync Server 2013 sur une messagerie unifiée Exchange hébergée</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Messagerie instantanée et présence dans Outlook</p></li>
<li><p>Planification et participation à des réunions en ligne via Outlook</p></li>
<li><p>Messagerie instantanée/présence dans les clients mobiles</p></li>
<li><p>L’historique des conversations manquées et les journaux d’appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur</p></li>
<li><p>Photo de contact haute résolution dans le client Lync 2013.</p>
<div>

> [!NOTE]  
> Nécessite Microsoft Exchange Server 2013. Cette fonction n’est pas prise en charge dans Lync Web App lorsque les utilisateurs sont hébergés sur Skype entreprise online.


</div></li>
<li><p>Participer à une réunion en ligne dans les clients mobiles</p></li>
<li><p>Publier le statut en fonction des informations de disponibilité du calendrier Outlook</p></li>
<li><p>Délégation de réunion</p>
<p>Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt, ou tous les deux sont hébergés en local.</p></li>
</ul></td>
<td><ul>
<li><p>Messagerie instantanée/présence dans Outlook</p></li>
<li><p>Planification et participation à des réunions en ligne via Outlook</p></li>
<li><p>Messagerie instantanée/présence dans Outlook Web App</p></li>
<li><p>Planifier et participer à une réunion en ligne à partir d’Outlook Web App</p></li>
<li><p>Messagerie instantanée/présence dans les clients mobiles</p></li>
<li><p>Participer à une réunion en ligne dans les clients mobiles</p></li>
<li><p>Publier le statut en fonction des informations de disponibilité du calendrier Outlook</p></li>
<li><p>L’historique des conversations manquées et les journaux d’appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur</p></li>
<li><p>Liste de contacts (par le biais du magasin de contacts unifié)</p>
<div>

> [!NOTE]  
> Client Lync Server 2013 requis


</div></li>
<li><p>Photo de contact haute résolution dans Lync 2013 client et Lync Web App</p></li>
<li><p>Délégation de réunion</p>
<p>Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt, ou tous les deux sont hébergés en local.</p></li>
<li><p>Archivage de contenu (messagerie instantanée et réunion) dans Exchange</p></li>
<li><p>Recherche de contenu archivé</p></li>
<li><p>Messagerie vocale</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>Intégration à SharePoint

Le tableau suivant répertorie les fonctionnalités prises en charge dans un déploiement hybride Lync Server 2013 lors de l’intégration à SharePoint.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>SharePoint local</th>
<th>SharePoint Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 en local</strong></p></td>
<td><ul>
<li><p>Recherche de compétences</p></li>
<li><p>Présence dans SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>Présence dans SharePoint</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Présence dans SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>Présence dans SharePoint</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

