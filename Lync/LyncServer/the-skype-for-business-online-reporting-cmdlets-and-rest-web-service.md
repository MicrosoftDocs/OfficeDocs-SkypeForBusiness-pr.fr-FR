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

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="dab66-102">Cmdlets de création de rapports Skype entreprise Online et service Web REST</span><span class="sxs-lookup"><span data-stu-id="dab66-102">The Skype for Business Online reporting cmdlets and REST web service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dab66-103">_**Dernière modification de la rubrique:** 2014-09-05_</span><span class="sxs-lookup"><span data-stu-id="dab66-103">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="dab66-104">Outre les fonctionnalités de création de rapports, Skype entreprise Online fournit l’accès à cinq cmdlets Windows PowerShell pour générer ces rapports et peut également être utilisé par les administrateurs pour retourner des données de rapport personnalisées.</span><span class="sxs-lookup"><span data-stu-id="dab66-104">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="dab66-105">Skype entreprise Online inclut également le reste (le transfert d’état de la présentation), qui peut être utilisé par les développeurs pour récupérer des informations de rapport personnalisées.</span><span class="sxs-lookup"><span data-stu-id="dab66-105">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="dab66-106">Les applets de création de rapports disponibles aux administrateurs sont les suivantes:</span><span class="sxs-lookup"><span data-stu-id="dab66-106">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="dab66-107">Get-CsActiveUserReport, qui fournit des informations sur le nombre d’utilisateurs actifs (c’est-à-dire les utilisateurs qui se sont connectés à Skype entreprise Online et ayant participé à au moins une conférence ou une session d’égal à égal).</span><span class="sxs-lookup"><span data-stu-id="dab66-107">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="dab66-108">Get-CsAVConferenceTimeReport, qui fournit des informations sur la durée (en minutes) des utilisateurs qui ont passé dans les conférences audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="dab66-108">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="dab66-109">Get-CsConferenceReport, qui fournit des informations sur le nombre et le type de conférences auxquelles les utilisateurs ont participé.</span><span class="sxs-lookup"><span data-stu-id="dab66-109">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="dab66-110">Get-CsP2PAVTimeReport, qui fournit des informations sur le délai (en minutes) passé aux utilisateurs dans des sessions d’égal à égal incluant des contenus audio et/ou vidéo.</span><span class="sxs-lookup"><span data-stu-id="dab66-110">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="dab66-111">Get-CsP2PSessionReport, qui fournit des informations sur le nombre et le type de sessions d’égal à égal auxquelles l’utilisateur a participé.</span><span class="sxs-lookup"><span data-stu-id="dab66-111">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="dab66-112">La plupart des administrateurs utiliseront les rapports disponibles dans le centre d’administration 365 de Microsoft: pas seulement les rapports générés automatiquement, mais ils fournissent également une représentation graphique des données qui est souvent plus facile à interpréter que les valeurs de nombre brut renvoyées par le cmdlets de création de rapports.</span><span class="sxs-lookup"><span data-stu-id="dab66-112">Most administrators will use the reports available in the Microsoft 365 admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="dab66-113">Toutefois, les administrateurs habitués à Windows PowerShell peuvent utiliser les applets de applet de création de rapports pour renvoyer des données qui ne sont pas facilement disponibles dans les rapports Lync Online.</span><span class="sxs-lookup"><span data-stu-id="dab66-113">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="dab66-114">Par exemple, les applets de l’applet de création de rapports renvoient des informations sur la durée de la session (le temps, en minutes, de la date de fin de chaque session).</span><span class="sxs-lookup"><span data-stu-id="dab66-114">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="dab66-115">Les durées de session individuelles ne sont pas disponibles dans les rapports Lync Online.</span><span class="sxs-lookup"><span data-stu-id="dab66-115">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="dab66-116">De même, dans l’affichage quotidien, les rapports Lync Online affichent uniquement les informations relatives aux 14 jours précédents.</span><span class="sxs-lookup"><span data-stu-id="dab66-116">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="dab66-117">Si vous voulez passer en revue le total quotidien d’un autre jour (par exemple, une date de quatre mois auparavant), vous pouvez utiliser les applets de contrôle de création de rapports.</span><span class="sxs-lookup"><span data-stu-id="dab66-117">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="dab66-118">Les administrateurs peuvent également être intéressés par l’article [qui utilise Excel pour récupérer les données de rapport d’office 365](http://msdn.microsoft.com/en-us/library/dn781442.aspx), qui explique comment utiliser la fonctionnalité de requête de données OData dans Microsoft Excel pour créer un rapport Office 365 personnalisé.</span><span class="sxs-lookup"><span data-stu-id="dab66-118">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](http://msdn.microsoft.com/en-us/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="dab66-119">Les rapports personnalisés vous permettent de dicter les données qui sont renvoyées par le service de création de rapports d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="dab66-119">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="dab66-120">Les rapports personnalisés vous permettent également de procéder de la sorte en spécifiant la manière dont les données doivent être triées et regroupées et permettent d’accéder à des informations qui ne sont pas affichées dans le centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="dab66-120">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the admin center.</span></span>

<span data-ttu-id="dab66-121">Les administrateurs possédant un arrière-plan de développement peuvent utiliser le service Web REST pour obtenir des informations qui ne sont pas affichées dans le centre d’administration de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="dab66-121">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="dab66-122">Le service REST est semblable au service SOAP, car chaque technologie fournit un moyen de transférer des données XML entre un client et un serveur.</span><span class="sxs-lookup"><span data-stu-id="dab66-122">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="dab66-123">Toutefois, le service REST a au moins deux avantages par rapport au service SOAP.</span><span class="sxs-lookup"><span data-stu-id="dab66-123">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="dab66-124">Pour un, REST effectue des transferts de données XML à l’aide d’un format normalisé connu sous le nom de syndication ATOM.</span><span class="sxs-lookup"><span data-stu-id="dab66-124">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="dab66-125">En revanche, le protocole SOAP utilise un format non standard lors du transfert de données.</span><span class="sxs-lookup"><span data-stu-id="dab66-125">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="dab66-126">De plus, le REST est en mesure de transférer des données entre des réseaux qui bloquent les verbes HTTP autres que GET et POST.</span><span class="sxs-lookup"><span data-stu-id="dab66-126">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="dab66-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dab66-127">See Also</span></span>


<span data-ttu-id="dab66-128">[Rapports Lync Online](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dab66-128">[Lync Online reporting](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="dab66-129">Service Web de création de rapports Office 365</span><span class="sxs-lookup"><span data-stu-id="dab66-129">The Office 365 Reporting Web Service</span></span>](http://msdn.microsoft.com/en-us/library/office/jj984325.aspx)  
[<span data-ttu-id="dab66-130">Découvrir le service Web de création de rapports d’Office 365</span><span class="sxs-lookup"><span data-stu-id="dab66-130">Learning About the Office 365 Reporting Web Service</span></span>](http://msdn.microsoft.com/en-us/library/office/jj984321.aspx)  
<span data-ttu-id="dab66-131">[Cmdlets de rapport Exchange Online](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="dab66-131">[The Exchange Online Reporting Cmdlets](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="dab66-132">Utiliser Excel pour récupérer les données de rapport d’Office 365</span><span class="sxs-lookup"><span data-stu-id="dab66-132">Using Excel to Retrieve Office 365 Reporting Data</span></span>](http://msdn.microsoft.com/en-us/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

