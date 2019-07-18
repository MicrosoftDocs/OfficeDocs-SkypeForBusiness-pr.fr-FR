---
title: Cmdlets de création de rapports Skype entreprise Online et service Web REST
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2b1e11b4c9d68dbc5e177d684cd3053a83df8ea
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>Cmdlets de création de rapports Skype entreprise Online et service Web REST

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-09-05_

Outre les fonctionnalités de création de rapports, Skype entreprise Online fournit l’accès à cinq cmdlets Windows PowerShell pour générer ces rapports et peut également être utilisé par les administrateurs pour retourner des données de rapport personnalisées. Skype entreprise Online inclut également le reste (le transfert d’état de la présentation), qui peut être utilisé par les développeurs pour récupérer des informations de rapport personnalisées.

Les applets de création de rapports disponibles aux administrateurs sont les suivantes:

  - Get-CsActiveUserReport, qui fournit des informations sur le nombre d’utilisateurs actifs (c’est-à-dire les utilisateurs qui se sont connectés à Skype entreprise Online et ayant participé à au moins une conférence ou une session d’égal à égal).

  - Get-CsAVConferenceTimeReport, qui fournit des informations sur la durée (en minutes) des utilisateurs qui ont passé dans les conférences audio/vidéo.

  - Get-CsConferenceReport, qui fournit des informations sur le nombre et le type de conférences auxquelles les utilisateurs ont participé.

  - Get-CsP2PAVTimeReport, qui fournit des informations sur le délai (en minutes) passé aux utilisateurs dans des sessions d’égal à égal incluant des contenus audio et/ou vidéo.

  - Get-CsP2PSessionReport, qui fournit des informations sur le nombre et le type de sessions d’égal à égal auxquelles l’utilisateur a participé.

La plupart des administrateurs utiliseront les rapports disponibles dans le centre d’administration 365 de Microsoft: pas seulement les rapports générés automatiquement, mais ils fournissent également une représentation graphique des données qui est souvent plus facile à interpréter que les valeurs de nombre brut renvoyées par le cmdlets de création de rapports. Toutefois, les administrateurs habitués à Windows PowerShell peuvent utiliser les applets de applet de création de rapports pour renvoyer des données qui ne sont pas facilement disponibles dans les rapports Lync Online. Par exemple, les applets de l’applet de création de rapports renvoient des informations sur la durée de la session (le temps, en minutes, de la date de fin de chaque session). Les durées de session individuelles ne sont pas disponibles dans les rapports Lync Online. De même, dans l’affichage quotidien, les rapports Lync Online affichent uniquement les informations relatives aux 14 jours précédents. Si vous voulez passer en revue le total quotidien d’un autre jour (par exemple, une date de quatre mois auparavant), vous pouvez utiliser les applets de contrôle de création de rapports.

Les administrateurs peuvent également être intéressés par l’article [qui utilise Excel pour récupérer les données de rapport d’office 365](http://msdn.microsoft.com/en-us/library/dn781442.aspx), qui explique comment utiliser la fonctionnalité de requête de données OData dans Microsoft Excel pour créer un rapport Office 365 personnalisé. Les rapports personnalisés vous permettent de dicter les données qui sont renvoyées par le service de création de rapports d’Office 365. Les rapports personnalisés vous permettent également de procéder de la sorte en spécifiant la manière dont les données doivent être triées et regroupées et permettent d’accéder à des informations qui ne sont pas affichées dans le centre d’administration.

Les administrateurs possédant un arrière-plan de développement peuvent utiliser le service Web REST pour obtenir des informations qui ne sont pas affichées dans le centre d’administration de Skype entreprise online. Le service REST est semblable au service SOAP, car chaque technologie fournit un moyen de transférer des données XML entre un client et un serveur. Toutefois, le service REST a au moins deux avantages par rapport au service SOAP. Pour un, REST effectue des transferts de données XML à l’aide d’un format normalisé connu sous le nom de syndication ATOM. En revanche, le protocole SOAP utilise un format non standard lors du transfert de données. De plus, le REST est en mesure de transférer des données entre des réseaux qui bloquent les verbes HTTP autres que GET et POST.

<div>

## <a name="see-also"></a>Voir aussi


[Rapports Lync Online](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))  


[Service Web de création de rapports Office 365](http://msdn.microsoft.com/en-us/library/office/jj984325.aspx)  
[Découvrir le service Web de création de rapports d’Office 365](http://msdn.microsoft.com/en-us/library/office/jj984321.aspx)  
[Cmdlets de rapport Exchange Online](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)  
[Utiliser Excel pour récupérer les données de rapport d’Office 365](http://msdn.microsoft.com/en-us/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

