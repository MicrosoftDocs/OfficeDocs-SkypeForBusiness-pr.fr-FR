---
title: Tester les paramètres de configuration du Trunk SIP dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Les paramètres de configuration du Trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté (PSTN), un échange de succursale public (PBX) ou un contrôleur de bordure de session (SBC) au fournisseur de services. '
ms.openlocfilehash: bfb09511c8d074555c0b84d2da141a029f63a01a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992561"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="e900e-103">Tester les paramètres de configuration du Trunk SIP dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e900e-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="e900e-104">Les paramètres de configuration du Trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté (PSTN), un échange de succursale public (PBX) ou un contrôleur de bordure de session (SBC) au fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="e900e-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="e900e-105">Ces paramètres spécifient, par exemple :</span><span class="sxs-lookup"><span data-stu-id="e900e-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="e900e-106">si la déviation du trafic multimédia doit être activée sur les jonctions ;</span><span class="sxs-lookup"><span data-stu-id="e900e-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="e900e-107">Les conditions dans lesquelles les paquets de contrôle de transport en temps réel (RTCP) sont envoyés.</span><span class="sxs-lookup"><span data-stu-id="e900e-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="e900e-108">Le chiffrement SRTP (Secure Real-Time Protocol) est requis sur chaque Trunk.</span><span class="sxs-lookup"><span data-stu-id="e900e-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="e900e-109">Lorsque vous installez Skype entreprise Server, une collection globale de paramètres de configuration SIP Trunk est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="e900e-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="e900e-110">En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).</span><span class="sxs-lookup"><span data-stu-id="e900e-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="e900e-111">Les administrateurs peuvent également utiliser l’applet de [contrôle test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) pour vérifier qu’un Trunk peut convertir un nombre comme composé par un utilisateur sur un numéro qui peut être géré par la passerelle.</span><span class="sxs-lookup"><span data-stu-id="e900e-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="e900e-112">Les paramètres de configuration de jonction peuvent uniquement être testés à l’aide de Windows PowerShell et de l’applet de commande Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="e900e-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="e900e-113">Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e900e-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="e900e-114">**Pour tester les paramètres de configuration des jonctions SIP**</span><span class="sxs-lookup"><span data-stu-id="e900e-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="e900e-115">Cette commande vérifie que les paramètres de configuration de jonction pour le site Redmond peuvent convertir correctement le numéro composé 4255551212.</span><span class="sxs-lookup"><span data-stu-id="e900e-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
