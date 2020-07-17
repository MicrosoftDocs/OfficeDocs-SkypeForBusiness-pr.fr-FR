---
title: Applets de commande de création de rapports Skype entreprise Online et service Web REST
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f40d394ba69cf017c11d4eb6cd57246a9d425c0f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="659d5-102">Applets de commande de création de rapports Skype entreprise Online et service Web REST</span><span class="sxs-lookup"><span data-stu-id="659d5-102">The Skype for Business Online reporting cmdlets and REST web service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="659d5-103">_**Dernière modification de la rubrique :** 2014-09-05_</span><span class="sxs-lookup"><span data-stu-id="659d5-103">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="659d5-104">En association avec les fonctionnalités de création de rapports, Skype entreprise Online permet d’accéder à cinq applets de commande Windows PowerShell qui permettent de générer ces rapports et qui peuvent également être utilisés par les administrateurs pour renvoyer des données de création de rapports personnalisées.</span><span class="sxs-lookup"><span data-stu-id="659d5-104">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="659d5-105">Skype entreprise Online inclut également le reste (Representational State Transfer), qui peut être utilisé par les développeurs pour récupérer des informations de création de rapports personnalisées.</span><span class="sxs-lookup"><span data-stu-id="659d5-105">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="659d5-106">Les applets de commande de création de rapports disponibles pour les administrateurs sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="659d5-106">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="659d5-107">Get-Csactiveuserreport permet, qui fournit des informations sur le nombre d’utilisateurs actifs (c’est-à-dire, les utilisateurs qui ont ouvert une session sur Skype entreprise Online et qui ont participé à au moins une conférence ou une session de communication P2P).</span><span class="sxs-lookup"><span data-stu-id="659d5-107">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="659d5-108">Get-CsAVConferenceTimeReport, qui fournit des informations sur la durée (en minutes) pendant laquelle les utilisateurs ont passé des conférences audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="659d5-108">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="659d5-109">Get-Csconferencereport permet, qui fournit des informations sur le nombre et le type de conférences auxquelles les utilisateurs ont participé.</span><span class="sxs-lookup"><span data-stu-id="659d5-109">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="659d5-110">Get-CsP2PAVTimeReport, qui fournit des informations sur la durée (en minutes) pendant laquelle les utilisateurs ont passé des sessions d’égal à égal qui incluaient l’audio et/ou la vidéo.</span><span class="sxs-lookup"><span data-stu-id="659d5-110">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="659d5-111">Get-Csp2psessionreport permet, qui fournit des informations sur le nombre et le type de sessions P2P auxquelles les utilisateurs ont participé.</span><span class="sxs-lookup"><span data-stu-id="659d5-111">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="659d5-112">La plupart des administrateurs utilisent les rapports disponibles dans le centre d’administration 365 de Microsoft : non seulement les rapports sont générés automatiquement, mais ils fournissent également une représentation graphique des données souvent plus facile à interpréter que les valeurs numériques brutes renvoyées par les applets de commande de création de rapports.</span><span class="sxs-lookup"><span data-stu-id="659d5-112">Most administrators will use the reports available in the Microsoft 365 admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="659d5-113">Toutefois, les administrateurs habitués à Windows PowerShell peuvent utiliser les applets de commande de création de rapports pour renvoyer des données qui ne sont pas immédiatement disponibles à partir des rapports Lync Online.</span><span class="sxs-lookup"><span data-stu-id="659d5-113">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="659d5-114">Par exemple, les applets de commande de création de rapports renvoient des informations sur la durée de la session (la durée, en minutes, de chaque session).</span><span class="sxs-lookup"><span data-stu-id="659d5-114">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="659d5-115">Les durées de session individuelles ne sont pas disponibles à l’aide des rapports Lync Online.</span><span class="sxs-lookup"><span data-stu-id="659d5-115">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="659d5-116">De même, dans l’affichage quotidien, les rapports Lync Online affichent des informations uniquement pour les 14 jours précédents.</span><span class="sxs-lookup"><span data-stu-id="659d5-116">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="659d5-117">Si vous souhaitez passer en revue les totaux quotidiens pour un autre jour (par exemple, une date comprise entre quatre mois), vous pouvez le faire à l’aide des applets de commande de création de rapports.</span><span class="sxs-lookup"><span data-stu-id="659d5-117">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="659d5-118">Les administrateurs peuvent également être intéressés par l’article [utilisant Excel pour récupérer des données de création de rapports office 365](https://msdn.microsoft.com/library/dn781442.aspx), qui expliquent comment utiliser la fonctionnalité requête de données OData dans Microsoft Excel pour créer des rapports Office 365 personnalisés.</span><span class="sxs-lookup"><span data-stu-id="659d5-118">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](https://msdn.microsoft.com/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="659d5-119">Les rapports personnalisés vous permettent de déterminer les données (et la capacité de données) renvoyées par le service de création de rapports Office 365.</span><span class="sxs-lookup"><span data-stu-id="659d5-119">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="659d5-120">Les rapports personnalisés vous permettent également d’effectuer des opérations telles que la spécification du mode de tri et de regroupement des données, ainsi que l’accès aux informations qui ne sont pas affichées dans le centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="659d5-120">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the admin center.</span></span>

<span data-ttu-id="659d5-121">Les administrateurs disposant d’un arrière-plan de développement peuvent utiliser le service Web REST pour obtenir des informations non affichées dans le centre d’administration de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="659d5-121">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="659d5-122">Le service REST est similaire au service SOAP, car chaque technologie offre un moyen de transférer des données XML entre un client et un serveur.</span><span class="sxs-lookup"><span data-stu-id="659d5-122">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="659d5-123">Toutefois, le service REST présente au moins deux avantages par rapport au service SOAP.</span><span class="sxs-lookup"><span data-stu-id="659d5-123">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="659d5-124">Pour un, REST effectue des transferts de données XML à l’aide d’un format standardisé connu sous le nom de syndication ATOM.</span><span class="sxs-lookup"><span data-stu-id="659d5-124">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="659d5-125">En revanche, SOAP utilise un format non standard lors du transfert de données.</span><span class="sxs-lookup"><span data-stu-id="659d5-125">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="659d5-126">De plus, REST est capable de transférer des données entre des réseaux qui bloquent les verbes HTTP autres que GET et POST.</span><span class="sxs-lookup"><span data-stu-id="659d5-126">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="659d5-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="659d5-127">See Also</span></span>


<span data-ttu-id="659d5-128">[Création de rapports Lync Online](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="659d5-128">[Lync Online reporting](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="659d5-129">Service Web de création de rapports Office 365</span><span class="sxs-lookup"><span data-stu-id="659d5-129">The Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984325.aspx)  
[<span data-ttu-id="659d5-130">En savoir plus sur le service Web de création de rapports Office 365</span><span class="sxs-lookup"><span data-stu-id="659d5-130">Learning About the Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984321.aspx)  
<span data-ttu-id="659d5-131">[Applets de commande de création de rapports Exchange Online](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="659d5-131">[The Exchange Online Reporting Cmdlets](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="659d5-132">Utilisation d'Excel pour récupérer des données de création de rapports Office 365</span><span class="sxs-lookup"><span data-stu-id="659d5-132">Using Excel to Retrieve Office 365 Reporting Data</span></span>](https://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

