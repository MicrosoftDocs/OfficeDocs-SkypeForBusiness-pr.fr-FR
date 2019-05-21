---
title: Tester les paramètres de configuration du Trunk SIP dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Résumé: Découvrez comment tester les paramètres de configuration du Trunk SIP à l’aide de Skype entreprise Server Management Shell.'
ms.openlocfilehash: aec88300341f42d5f228c3c13f1a0925b71ce855
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300959"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="d0fe6-103">Tester les paramètres de configuration du Trunk SIP dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d0fe6-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="d0fe6-104">**Résumé:** Découvrez comment tester les paramètres de configuration du Trunk SIP à l’aide de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d0fe6-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="d0fe6-p101">Les paramètres de configuration de jonction SIP (Session Initiation Protocol) définissent la relation et les possibilités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (RTC), un autocommutateur privé IP (PBX) ou le contrôleur SBC (Session Border Controller) du côté fournisseur de services. Ces paramètres spécifient, par exemple :</span><span class="sxs-lookup"><span data-stu-id="d0fe6-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="d0fe6-107">si la déviation du trafic multimédia doit être activée sur les jonctions ;</span><span class="sxs-lookup"><span data-stu-id="d0fe6-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="d0fe6-108">les conditions dans lesquelles les paquets RTCP sont envoyés ;</span><span class="sxs-lookup"><span data-stu-id="d0fe6-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="d0fe6-109">si le chiffrement SRTP (Secure Real-Time Protocol ) est requis ou non sur chaque jonction.</span><span class="sxs-lookup"><span data-stu-id="d0fe6-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="d0fe6-110">Lorsque vous installez Skype entreprise Server, une collection globale de paramètres de configuration SIP Trunk est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="d0fe6-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="d0fe6-111">En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).</span><span class="sxs-lookup"><span data-stu-id="d0fe6-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="d0fe6-112">Les administrateurs peuvent également utiliser l’applet de commande Test-CsTrunkConfiguration pour vérifier qu’une jonction peut convertir un numéro composé par un utilisateur en numéro pouvant être traité par la passerelle.</span><span class="sxs-lookup"><span data-stu-id="d0fe6-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="d0fe6-113">Les paramètres de configuration de jonction peuvent uniquement être testés à l’aide de Windows PowerShell et de l’applet de commande [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d0fe6-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="d0fe6-114">Ce cmdlet peut être exécuté à partir de Skype entreprise Server Management Shell ou d’une session à distance de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d0fe6-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="d0fe6-115">Pour tester les paramètres de configuration des jonctions SIP</span><span class="sxs-lookup"><span data-stu-id="d0fe6-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="d0fe6-116">Cette commande vérifie que les paramètres de configuration de jonction pour le site Redmond peuvent convertir correctement le numéro composé 4255551212.</span><span class="sxs-lookup"><span data-stu-id="d0fe6-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


