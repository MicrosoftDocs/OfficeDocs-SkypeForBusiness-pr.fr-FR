---
title: Afficher des informations sur les circuits SIP individuels dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Résumé: Découvrez comment afficher des informations sur les ISL SIP dans Skype entreprise Server.'
ms.openlocfilehash: 3d8ad70428926c26445c6556544a5a363de12f5c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239942"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="d5804-103">Afficher des informations sur les circuits SIP individuels dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d5804-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="d5804-104">**Résumé:** Découvrez comment afficher des informations sur les ISL SIP dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d5804-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="d5804-105">Les circuits SIP sont utilisés pour connecter le réseau téléphonique commuté de Skype entreprise Server à l’aide du réseau téléphonique public commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="d5804-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="d5804-106">Dans la version précédente du produit, les Trunks permettaient le routage des appels sortants d’un serveur de médiation vers une passerelle RTC et chaque passerelle était limitée à un seul Trunk.</span><span class="sxs-lookup"><span data-stu-id="d5804-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="d5804-107">Par conséquent, une passerelle RTC et un Trunk SIP étaient essentiellement identiques.</span><span class="sxs-lookup"><span data-stu-id="d5804-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="d5804-108">Pour les administrateurs, cela signifie qu’ils pouvaient afficher les informations relatives à une ligne SIP individuelle en consultant les informations relatives à la passerelle RTC associée.</span><span class="sxs-lookup"><span data-stu-id="d5804-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="d5804-109">Dans Skype entreprise Server, il est désormais possible d’attribuer plusieurs Trunks à une seule passerelle PSTN. Cela signifie que les passerelles et les liaisons ne sont plus une seule et même.</span><span class="sxs-lookup"><span data-stu-id="d5804-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="d5804-110">Cela signifie que les administrateurs doivent utiliser la nouvelle applet de commande [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) pour afficher des informations sur un Trunk SIP individuel.</span><span class="sxs-lookup"><span data-stu-id="d5804-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="d5804-111">Pour afficher des informations sur toutes vos jonctions SIP</span><span class="sxs-lookup"><span data-stu-id="d5804-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="d5804-112">La commande suivante retourne des informations relatives à toutes les jonctions SIP utilisées dans votre organisation :</span><span class="sxs-lookup"><span data-stu-id="d5804-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="d5804-113">Pour afficher les informations relatives à une jonction SIP spécifique</span><span class="sxs-lookup"><span data-stu-id="d5804-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="d5804-114">La commande suivante retourne uniquement les informations relatives à la jonction SIP ayant l’identité PstnGateway 192.168.0.240 :</span><span class="sxs-lookup"><span data-stu-id="d5804-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="d5804-115">Affichage des informations relatives à toutes les jonctions SIP affectées à un pool</span><span class="sxs-lookup"><span data-stu-id="d5804-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="d5804-116">Dans cet exemple, les informations relatives à toutes les jonctions SIP affectées au pool atl-cs-001.litwareinc.com sont retournées :</span><span class="sxs-lookup"><span data-stu-id="d5804-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
