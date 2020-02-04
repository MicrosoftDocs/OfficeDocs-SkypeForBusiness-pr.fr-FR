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
ms.openlocfilehash: 0dea28ecfcd5e6a881c1d3d1ee63f16cd4821410
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a>Configurations hybrides Lync Server 2013 prises en charge

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-05-10_

Vous pouvez configurer les déploiements de Lync Server 2013 pour l’intégration avec Microsoft Exchange Server 2010 et Microsoft Exchange Server 2013 et SharePoint Server, en local et en ligne. Sauf indication contraire, les fonctionnalités affichées dans le tableau ci-dessous sont prises en charge avec tous les clients. Pour plus d’informations sur la prise en charge des clients, voir [tableaux de comparaison des clients pour Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) et les tableaux de comparaison des clients Skype entreprise Online pour [les clients de Skype entreprise Online](http://go.microsoft.com/fwlink/p/?linkid=281902).

<div>

## <a name="integration-with-exchange-server"></a>Intégration à Exchange Server

Le tableau suivant répertorie les fonctionnalités prises en charge dans un déploiement hybride lorsque Microsoft Exchange Server est intégré.


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
<td><p><strong>Lync Server 2013 en local</strong></p></td>
<td><ul>
<li><p>Messagerie instantanée/présence dans Outlook</p>
<p>Pour plus d’informations, reportez-vous à la section <a href="lync-server-2013-im-and-presence.md">messagerie instantanée et présence dans Lync Server 2013</a></p></li>
<li><p>Planification de réunions en ligne et participation à l’aide d’Outlook</p>
<p>Pour plus d’informations, reportez-vous <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</a>.</p></li>
<li><p>Messagerie instantanée et présence dans Outlook Web App</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">configuration de Microsoft Lync Server 2013 dans un environnement local</a></p></li>
<li><p>Planification de réunions en ligne et participation via Outlook Web App</p></li>
<li><p>Messagerie instantanée/présence dans les clients mobiles</p></li>
<li><p>Participation à des réunions en ligne dans les clients mobiles</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-deploying-mobility.md">déploiement de mobilité dans Lync Server 2013</a></p></li>
<li><p>Publication du statut en fonction des informations de disponibilité du calendrier Outlook</p></li>
<li><p>Liste de contacts (par le biais du magasin de contacts unifié)</p>
<p>Pour plus d’informations, reportez-vous <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">à configuration de Microsoft Lync Server 2013 pour utiliser le magasin de contacts unifié</a></p>
<div>

> [!NOTE]  
> Nécessite Exchange 2013.<BR>Un client de bureau Lync 2013 est requis.


</div></li>
<li><p>Photo de contact haute résolution dans le client Lync 2013 et Lync Web App.</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">la rubrique Configuration de l’utilisation de photos haute résolution dans Microsoft Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Nécessite Exchange 2013.


</div></li>
<li><p>Délégation de réunion</p>
<p>Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt ou hébergés en local.</p></li>
<li><p>L’historique des conversations manquées et les journaux des appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur</p></li>
<li><p>Archivage de contenu (messagerie instantanée et réunion) dans Exchange</p>
<p>Pour plus d’informations, voir <a href="lync-server-2013-deployment-checklist-for-archiving.md">liste de vérification de déploiement pour l’archivage dans Lync Server 2013</a></p>
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
<p>Pour plus d’informations, reportez-vous <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">à déploiement d’une messagerie unifiée Exchange locale pour fournir la messagerie vocale de Lync Server 2013</a></p></li>
</ul></td>
<td><ul>
<li><p>Messagerie instantanée/présence dans Outlook</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">configuration de l’intégration de Lync Server 2013 en local avec Exchange Online</a> .</p></li>
<li><p>Planification d’une réunion en ligne et participation à l’aide d’Outlook</p></li>
<li><p>Messagerie instantanée/présence dans OWA</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">configuration de l’intégration de Lync Server 2013 en local avec Exchange Online</a> .</p></li>
<li><p>Planifier et rejoindre une réunion en ligne à partir d’Outlook Web App</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">configuration de l’intégration de Lync Server 2013 en local avec Exchange Online</a> .</p></li>
<li><p>Messagerie instantanée/présence dans les clients mobiles</p></li>
<li><p>Participation à une réunion en ligne dans les clients mobiles</p></li>
<li><p>Publication du statut en fonction des informations de disponibilité du calendrier Outlook</p></li>
<li><p>Liste de contacts (par le biais du magasin de contacts unifié). Pour plus d’informations, reportez-vous <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">à configuration de Microsoft Lync Server 2013 pour utiliser le magasin de contacts unifié</a></p>
<div>

> [!NOTE]  
> Lync Server 2013 uniquement. Un client de bureau Lync 2013 est requis.


</div></li>
<li><p>Photo de contact haute résolution dans le client Lync 2013 et Lync Web App.</p>
<p>Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">la rubrique Configuration de l’utilisation de photos haute résolution dans Microsoft Lync Server 2013</a>.</p></li>
<li><p>Délégation de réunion</p>
<p>Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt ou hébergés en local.</p></li>
<li><p>L’historique des conversations manquées et les journaux des appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur</p></li>
<li><p>Archivage de contenu (messagerie instantanée et réunion) dans Exchange.</p>
<p>Pour plus d’informations, voir <a href="lync-server-2013-deployment-checklist-for-archiving.md">liste de vérification de déploiement pour l’archivage dans Lync Server 2013</a></p></li>
<li><p>Recherche de contenu archivé. Pour plus d’informations, reportez-vous à la section <a href="http://go.microsoft.com/fwlink/p/?linkid=285448">configurer Exchange pour le centre de découverte électronique SharePoint</a></p></li>
<li><p>Messagerie vocale. Pour plus d’informations, reportez-vous à la section <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">fourniture de messages vocaux aux utilisateurs Lync Server 2013 sur la messagerie unifiée Exchange</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Messagerie instantanée et présence dans Outlook</p></li>
<li><p>Planification de réunions en ligne et participation à l’aide d’Outlook</p></li>
<li><p>Messagerie instantanée/présence dans les clients mobiles</p></li>
<li><p>L’historique des conversations manquées et les journaux des appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur.</p></li>
<li><p>Photo de contact haute résolution dans le client Lync 2013.</p>
<div>

> [!NOTE]  
> Nécessite Microsoft Exchange Server 2013. Ceci n’est pas pris en charge dans Lync Web App lorsque les utilisateurs sont familiaux dans Skype entreprise online.


</div></li>
<li><p>Participation à une réunion en ligne dans les clients mobiles</p></li>
<li><p>Publication du statut en fonction des informations de disponibilité du calendrier Outlook</p></li>
<li><p>Délégation de réunion</p>
<p>Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt ou hébergés en local.</p></li>
</ul></td>
<td><ul>
<li><p>Messagerie instantanée/présence dans Outlook</p></li>
<li><p>Planification de réunions en ligne et participation à l’aide d’Outlook</p></li>
<li><p>Messagerie instantanée et présence dans Outlook Web App</p></li>
<li><p>Planifier et rejoindre une réunion en ligne à partir d’Outlook Web App</p></li>
<li><p>Messagerie instantanée/présence dans les clients mobiles</p></li>
<li><p>Participation à une réunion en ligne dans les clients mobiles</p></li>
<li><p>Publication du statut en fonction des informations de disponibilité du calendrier Outlook</p></li>
<li><p>L’historique des conversations manquées et les journaux des appels sont écrits dans la boîte aux lettres Exchange de l’utilisateur.</p></li>
<li><p>Liste de contacts (par le biais du magasin de contacts unifié)</p>
<div>

> [!NOTE]  
> Client de Lync Server 2013 requis


</div></li>
<li><p>Photo de contact haute résolution dans le client Lync 2013 et Lync Web App</p></li>
<li><p>Délégation de réunion</p>
<p>Pris en charge uniquement lorsque les deux utilisateurs sont hébergés en ligne dans la même forêt ou hébergés en local.</p></li>
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

Le tableau suivant répertorie les fonctionnalités prises en charge dans un déploiement hybride Lync Server 2013 lorsqu’il est intégré à SharePoint.


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


</div>

</div>

<span> </span>

</div>

</div>

</div>

