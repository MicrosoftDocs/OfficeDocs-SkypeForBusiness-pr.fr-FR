---
title: 'Lync Server 2013: valider les adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57ae7698a50706ed0076650a657a8ec503ffa6aa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a><span data-ttu-id="7de0c-102">Valider des adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7de0c-102">Validate addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7de0c-103">_**Dernière modification de la rubrique:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="7de0c-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="7de0c-104">Avant de publier la base de données de géolocalisation, vous devez valider de nouveaux emplacements par rapport au Guide de l’adresse principale (MSAG), qui est géré par votre réseau SIP ou un réseau téléphonique commuté (RTC) E9-1-1 prestataire de services.</span><span class="sxs-lookup"><span data-stu-id="7de0c-104">Before publishing the location database, you must validate new locations against the Master Street Address Guide (MSAG) that is maintained by your SIP trunk or public switched telephone network (PSTN) E9-1-1 service provider.</span></span>

<span data-ttu-id="7de0c-105">Pour plus d’informations sur les fournisseurs de services SIP Trunk E9-1-1, voir [choix d’un fournisseur de services E9-1-1 pour Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span><span class="sxs-lookup"><span data-stu-id="7de0c-105">For details about SIP trunk E9-1-1 service providers, see [Choosing an E9-1-1 service provider for Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span></span>

<span data-ttu-id="7de0c-106">Pour plus d’informations sur la validation d’adresses, voir la documentation Lync Server Management Shell pour les applets de commande suivantes:</span><span class="sxs-lookup"><span data-stu-id="7de0c-106">For details about validating addresses, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="7de0c-107">**Get-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="7de0c-107">**Get-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="7de0c-108">**Set-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="7de0c-108">**Set-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="7de0c-109">**Remove-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="7de0c-109">**Remove-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="7de0c-110">**Get-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="7de0c-110">**Get-CsLisCivicAddress**</span></span>

  - <span data-ttu-id="7de0c-111">**Test-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="7de0c-111">**Test-CsLisCivicAddress**</span></span>

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="7de0c-112">Pour valider des adresses situées dans la base de données des emplacements</span><span class="sxs-lookup"><span data-stu-id="7de0c-112">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="7de0c-113">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7de0c-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7de0c-114">Exécutez les applets de commande ci-dessous pour configurer la connexion du fournisseur de service d’urgence.</span><span class="sxs-lookup"><span data-stu-id="7de0c-114">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  <span data-ttu-id="7de0c-115">Exécutez l’applet de commande ci-dessous pour valider les adresses de la base de données des emplacements.</span><span class="sxs-lookup"><span data-stu-id="7de0c-115">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    <span data-ttu-id="7de0c-116">Vous pouvez également utiliser l’applet de commande **Test-CsLisCivicAddress** pour valider des adresses individuelles.</span><span class="sxs-lookup"><span data-stu-id="7de0c-116">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

