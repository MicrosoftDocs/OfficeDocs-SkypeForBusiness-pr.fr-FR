---
title: 'Lync Server 2013 : validation des adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4054af0ec8adbe219b2cc8dd33aac4fe52cf5ead
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42121607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a><span data-ttu-id="f2fac-102">Valider des adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2fac-102">Validate addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2fac-103">_**Dernière modification de la rubrique :** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="f2fac-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="f2fac-104">Avant de publier la base de données des emplacements, vous devez valider les nouveaux emplacements par rapport à la base de données MSAG (Master Street Address Guide) gérée par votre fournisseur de service de jonction SIP ou E9-1-1 PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="f2fac-104">Before publishing the location database, you must validate new locations against the Master Street Address Guide (MSAG) that is maintained by your SIP trunk or public switched telephone network (PSTN) E9-1-1 service provider.</span></span>

<span data-ttu-id="f2fac-105">Pour plus d’informations sur les fournisseurs de services de jonction SIP E9-1-1, voir [choix d’un fournisseur de services E9-1-1 pour Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span><span class="sxs-lookup"><span data-stu-id="f2fac-105">For details about SIP trunk E9-1-1 service providers, see [Choosing an E9-1-1 service provider for Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).</span></span>

<span data-ttu-id="f2fac-106">Pour plus d’informations sur la validation des adresses, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="f2fac-106">For details about validating addresses, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="f2fac-107">**Get-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="f2fac-107">**Get-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="f2fac-108">**Set-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="f2fac-108">**Set-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="f2fac-109">**Remove-CsLisServiceProvider**</span><span class="sxs-lookup"><span data-stu-id="f2fac-109">**Remove-CsLisServiceProvider**</span></span>

  - <span data-ttu-id="f2fac-110">**Get-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="f2fac-110">**Get-CsLisCivicAddress**</span></span>

  - <span data-ttu-id="f2fac-111">**Test-CsLisCivicAddress**</span><span class="sxs-lookup"><span data-stu-id="f2fac-111">**Test-CsLisCivicAddress**</span></span>

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="f2fac-112">Pour valider des adresses situées dans la base de données des emplacements</span><span class="sxs-lookup"><span data-stu-id="f2fac-112">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="f2fac-113">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f2fac-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f2fac-114">Exécutez les applets de commande suivantes pour configurer la connexion du fournisseur de service d’urgence.</span><span class="sxs-lookup"><span data-stu-id="f2fac-114">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  <span data-ttu-id="f2fac-115">Exécutez l’applet de commande suivante pour valider les adresses de la base de données des emplacements.</span><span class="sxs-lookup"><span data-stu-id="f2fac-115">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    <span data-ttu-id="f2fac-116">Vous pouvez également utiliser l’applet de commande **Test-CsLisCivicAddress** pour valider des adresses individuelles.</span><span class="sxs-lookup"><span data-stu-id="f2fac-116">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

