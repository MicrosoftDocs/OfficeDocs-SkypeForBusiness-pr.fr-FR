---
title: Affichage des informations sur les différentes jonctions SIP (Session Initiation Protocol) dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Résumé : Découvrez comment afficher des informations sur les trunks SIP dans Skype pour Business Server 2015.'
ms.openlocfilehash: c307d4e9b18b7ff5fda8d8d0deaa4eb88ba5b6b0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server-2015"></a><span data-ttu-id="b8264-103">Affichage des informations sur les différentes jonctions SIP (Session Initiation Protocol) dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b8264-103">View information about individual SIP trunks in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b8264-104">**Résumé :** Découvrez comment afficher des informations sur les trunks SIP dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b8264-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b8264-105">PUITS SIP permettent de connecter Skype pour Business Server voix sur un réseau de téléphone IP avec la commutation de téléphone RTPC (réseau Public).</span><span class="sxs-lookup"><span data-stu-id="b8264-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="b8264-106">Dans la version précédente du produit, malles ont été utilisés pour router les appels sortants à partir d’un serveur de médiation à une passerelle PSTN et chaque passerelle a été limitée à une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="b8264-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="b8264-107">Par conséquent, une passerelle PSTN et un SIP trunk étaient essentiellement identiques.</span><span class="sxs-lookup"><span data-stu-id="b8264-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="b8264-108">Pour les administrateurs, cela signifiait qu’ils peuvent afficher des informations sur un SIP trunk individuel simplement par l’affichage d’informations sur la passerelle RTC associée.</span><span class="sxs-lookup"><span data-stu-id="b8264-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="b8264-109">Dans Skype pour Business Server, toutefois, plusieurs troncs peuvent ensuite être attribués à une passerelle PSTN unique ; Cela signifie que les passerelles et les puits y n’est plus les mêmes.</span><span class="sxs-lookup"><span data-stu-id="b8264-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="b8264-110">À son tour, cela signifie que les administrateurs doivent utiliser l’applet de commande [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) nouveau afin d’afficher des informations sur un SIP trunk individuel.</span><span class="sxs-lookup"><span data-stu-id="b8264-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="b8264-111">Pour afficher des informations sur toutes vos jonctions SIP</span><span class="sxs-lookup"><span data-stu-id="b8264-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="b8264-112">La commande suivante retourne des informations relatives à toutes les jonctions SIP utilisées dans votre organisation :</span><span class="sxs-lookup"><span data-stu-id="b8264-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="b8264-113">Pour afficher les informations relatives à une jonction SIP spécifique</span><span class="sxs-lookup"><span data-stu-id="b8264-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="b8264-114">La commande suivante retourne uniquement les informations relatives à la jonction SIP ayant l’identité PstnGateway 192.168.0.240 :</span><span class="sxs-lookup"><span data-stu-id="b8264-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="b8264-115">Affichage des informations relatives à toutes les jonctions SIP affectées à un pool</span><span class="sxs-lookup"><span data-stu-id="b8264-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="b8264-116">Dans cet exemple, les informations relatives à toutes les jonctions SIP affectées au pool atl-cs-001.litwareinc.com sont retournées :</span><span class="sxs-lookup"><span data-stu-id="b8264-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```


