---
title: Afficher des informations sur des trunks SIP individuelles dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Résumé : Découvrez comment afficher des informations sur les trunks SIP dans Skype Entreprise Server.'
ms.openlocfilehash: 29a5a025589f4df7d99b8bf708bf8bd67d0f138f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830524"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="1b97e-103">Afficher des informations sur des trunks SIP individuelles dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1b97e-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="1b97e-104">**Résumé :** Découvrez comment afficher des informations sur les trunks SIP dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1b97e-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="1b97e-105">Les connexions SIP (Public Switched Telephone Network) sont utilisées pour connecter Skype Entreprise Server Voice via un réseau téléphonique IP au réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="1b97e-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="1b97e-106">Dans la version précédente du produit, les trunks étaient utilisées pour router les appels sortants d’un serveur de médiation vers une passerelle PSTN et chaque passerelle était limitée à une seule.</span><span class="sxs-lookup"><span data-stu-id="1b97e-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="1b97e-107">Par conséquent, une passerelle PSTN et une trunk SIP étaient essentiellement identiques.</span><span class="sxs-lookup"><span data-stu-id="1b97e-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="1b97e-108">Pour les administrateurs, cela signifie qu’ils peuvent afficher des informations sur une trunk SIP individuelle simplement en visualisant les informations sur la passerelle PSTN associée.</span><span class="sxs-lookup"><span data-stu-id="1b97e-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="1b97e-109">Dans Skype Entreprise Server, toutefois, plusieurs branches peuvent désormais être affectées à une seule passerelle PSTN . Cela signifie que les passerelles et les trunks ne sont plus identiques.</span><span class="sxs-lookup"><span data-stu-id="1b97e-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="1b97e-110">Cela signifie que les administrateurs doivent utiliser la nouvelle cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) pour afficher des informations sur une trunk SIP individuelle.</span><span class="sxs-lookup"><span data-stu-id="1b97e-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="1b97e-111">Pour afficher des informations pour toutes vos trunks SIP</span><span class="sxs-lookup"><span data-stu-id="1b97e-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="1b97e-112">La commande suivante retourne des informations sur toutes les trunks SIP en cours d’utilisation dans votre organisation :</span><span class="sxs-lookup"><span data-stu-id="1b97e-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="1b97e-113">Pour afficher les informations d’une trunk SIP spécifique</span><span class="sxs-lookup"><span data-stu-id="1b97e-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="1b97e-114">Cette commande retourne des informations uniquement pour la trunk SIP dont l’identité est PstnGateway:192.168.0.240 :</span><span class="sxs-lookup"><span data-stu-id="1b97e-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="1b97e-115">Afficher les informations de toutes les trunks SIP affectées à un pool</span><span class="sxs-lookup"><span data-stu-id="1b97e-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="1b97e-116">Dans cet exemple, les informations sont retournées pour toutes les trunks SIP affectées au pool atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="1b97e-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
