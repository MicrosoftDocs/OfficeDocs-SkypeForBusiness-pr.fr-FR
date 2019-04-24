---
title: Tester les paramètres de configuration de jonction SIP dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Paramètres de configuration de jonction SIP définissent les relations et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté, un autocommutateur public-IP (PBX) ou un contrôleur de bordure de Session (SBC) au niveau du fournisseur de service. '
ms.openlocfilehash: 3f251ea720ab220ccda0cfe9882d4a8396085aa0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214623"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="f0510-103">Tester les paramètres de configuration de jonction SIP dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="f0510-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="f0510-104">Paramètres de configuration de jonction SIP définissent les relations et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté, un autocommutateur public-IP (PBX) ou un contrôleur de bordure de Session (SBC) au niveau du fournisseur de service.</span><span class="sxs-lookup"><span data-stu-id="f0510-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="f0510-105">Ces paramètres spécifient, par exemple :</span><span class="sxs-lookup"><span data-stu-id="f0510-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="f0510-106">si la déviation du trafic multimédia doit être activée sur les jonctions ;</span><span class="sxs-lookup"><span data-stu-id="f0510-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="f0510-107">Les conditions dans lesquelles les paquets Real-Time transport control protocol (RTCP) sont envoyés.</span><span class="sxs-lookup"><span data-stu-id="f0510-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="f0510-108">Ou non sécurisé en temps réel (chiffrement SRTP protocol) est requis sur chaque jonction.</span><span class="sxs-lookup"><span data-stu-id="f0510-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="f0510-109">Lorsque vous installez Skype pour Business Server, une collection de paramètres de configuration de jonction SIP globale est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="f0510-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="f0510-110">En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).</span><span class="sxs-lookup"><span data-stu-id="f0510-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="f0510-111">Les administrateurs peuvent également utiliser l’applet de commande [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) pour vérifier qu’une jonction permettre convertir un numéro composé par un utilisateur vers un numéro qui peut être géré par la passerelle.</span><span class="sxs-lookup"><span data-stu-id="f0510-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="f0510-112">Les paramètres de configuration de jonction peuvent uniquement être testés à l’aide de Windows PowerShell et de l’applet de commande Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f0510-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="f0510-113">Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0510-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="f0510-114">**Pour tester les paramètres de configuration des jonctions SIP**</span><span class="sxs-lookup"><span data-stu-id="f0510-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="f0510-115">Cette commande vérifie que les paramètres de configuration de jonction pour le site Redmond peuvent convertir correctement le numéro composé 4255551212.</span><span class="sxs-lookup"><span data-stu-id="f0510-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
