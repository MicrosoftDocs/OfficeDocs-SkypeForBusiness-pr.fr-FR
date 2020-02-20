---
title: Applets de commande de création de rapports Skype entreprise Online et service Web REST
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0476b90659ced152a4d24fbb3890ac224bdf0d91
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>Applets de commande de création de rapports Skype entreprise Online et service Web REST

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-09-05_

En association avec les fonctionnalités de création de rapports, Skype entreprise Online permet d’accéder à cinq applets de commande Windows PowerShell qui permettent de générer ces rapports et qui peuvent également être utilisés par les administrateurs pour renvoyer des données de création de rapports personnalisées. Skype entreprise Online inclut également le reste (Representational State Transfer), qui peut être utilisé par les développeurs pour récupérer des informations de création de rapports personnalisées.

Les applets de commande de création de rapports disponibles pour les administrateurs sont les suivantes :

  - Get-Csactiveuserreport permet, qui fournit des informations sur le nombre d’utilisateurs actifs (c’est-à-dire, les utilisateurs qui ont ouvert une session sur Skype entreprise Online et qui ont participé à au moins une conférence ou une session de communication P2P).

  - Get-CsAVConferenceTimeReport, qui fournit des informations sur la durée (en minutes) pendant laquelle les utilisateurs ont passé des conférences audio/vidéo.

  - Get-Csconferencereport permet, qui fournit des informations sur le nombre et le type de conférences auxquelles les utilisateurs ont participé.

  - Get-CsP2PAVTimeReport, qui fournit des informations sur la durée (en minutes) pendant laquelle les utilisateurs ont passé des sessions d’égal à égal qui incluaient l’audio et/ou la vidéo.

  - Get-Csp2psessionreport permet, qui fournit des informations sur le nombre et le type de sessions P2P auxquelles les utilisateurs ont participé.

La plupart des administrateurs utilisent les rapports disponibles dans le centre d’administration 365 de Microsoft : non seulement les rapports sont générés automatiquement, mais ils fournissent également une représentation graphique des données souvent plus facile à interpréter que les valeurs numériques brutes renvoyées par le applets de commande de création de rapports. Toutefois, les administrateurs habitués à Windows PowerShell peuvent utiliser les applets de commande de création de rapports pour renvoyer des données qui ne sont pas immédiatement disponibles à partir des rapports Lync Online. Par exemple, les applets de commande de création de rapports renvoient des informations sur la durée de la session (la durée, en minutes, de chaque session). Les durées de session individuelles ne sont pas disponibles à l’aide des rapports Lync Online. De même, dans l’affichage quotidien, les rapports Lync Online affichent des informations uniquement pour les 14 jours précédents. Si vous souhaitez passer en revue les totaux quotidiens pour un autre jour (par exemple, une date comprise entre quatre mois), vous pouvez le faire à l’aide des applets de commande de création de rapports.

Les administrateurs peuvent également être intéressés par l’article [utilisant Excel pour récupérer des données de création de rapports office 365](http://msdn.microsoft.com/library/dn781442.aspx), qui expliquent comment utiliser la fonctionnalité requête de données OData dans Microsoft Excel pour créer des rapports Office 365 personnalisés. Les rapports personnalisés vous permettent de déterminer les données (et la capacité de données) renvoyées par le service de création de rapports Office 365. Les rapports personnalisés vous permettent également d’effectuer des opérations telles que la spécification du mode de tri et de regroupement des données, ainsi que l’accès aux informations qui ne sont pas affichées dans le centre d’administration.

Les administrateurs disposant d’un arrière-plan de développement peuvent utiliser le service Web REST pour obtenir des informations non affichées dans le centre d’administration de Skype entreprise online. Le service REST est similaire au service SOAP, car chaque technologie offre un moyen de transférer des données XML entre un client et un serveur. Toutefois, le service REST présente au moins deux avantages par rapport au service SOAP. Pour un, REST effectue des transferts de données XML à l’aide d’un format standardisé connu sous le nom de syndication ATOM. En revanche, SOAP utilise un format non standard lors du transfert de données. De plus, REST est capable de transférer des données entre des réseaux qui bloquent les verbes HTTP autres que GET et POST.

<div>

## <a name="see-also"></a>Voir aussi


[Création de rapports Lync Online](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))  


[Service Web de création de rapports Office 365](http://msdn.microsoft.com/library/office/jj984325.aspx)  
[En savoir plus sur le service Web de création de rapports Office 365](http://msdn.microsoft.com/library/office/jj984321.aspx)  
[Applets de commande de création de rapports Exchange Online](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)  
[Utilisation d'Excel pour récupérer des données de création de rapports Office 365](http://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

