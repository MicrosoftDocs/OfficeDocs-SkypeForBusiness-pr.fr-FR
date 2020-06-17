---
title: Migrer des périphériques analogiques
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype entreprise Server prend en charge les appareils analogiques. Les périphériques analogiques pris en charge sont plus précisément des téléphones audio analogiques et des télécopieurs analogiques. Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation d’appareils analogiques dans votre environnement Skype entreprise Server. Après avoir effectué la migration vers Skype entreprise Server 2019, vous devez également migrer les objets contact associés aux appareils analogiques. Utilisez Skype entreprise Server Management Shell pour récupérer tous les objets contact associés aux appareils analogiques hérités, puis déplacez ces objets vers le pool Skype entreprise Server 2019.
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752826"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="1448f-107">Migrer des périphériques analogiques</span><span class="sxs-lookup"><span data-stu-id="1448f-107">Migrate analog devices</span></span>

<span data-ttu-id="1448f-108">Skype entreprise Server prend en charge les appareils analogiques.</span><span class="sxs-lookup"><span data-stu-id="1448f-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="1448f-109">Les périphériques analogiques pris en charge sont plus précisément des téléphones audio analogiques et des télécopieurs analogiques.</span><span class="sxs-lookup"><span data-stu-id="1448f-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="1448f-110">Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation d’appareils analogiques dans votre environnement Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1448f-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="1448f-111">Après avoir effectué la migration vers Skype entreprise Server 2019, vous devez également migrer les objets contact associés aux appareils analogiques.</span><span class="sxs-lookup"><span data-stu-id="1448f-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="1448f-112">Utilisez Skype entreprise Server Management Shell pour récupérer tous les objets contact associés aux appareils analogiques hérités, puis déplacez ces objets vers le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1448f-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="1448f-113">Pour migrer des périphériques analogiques</span><span class="sxs-lookup"><span data-stu-id="1448f-113">To migrate analog devices</span></span>

1. <span data-ttu-id="1448f-114">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Skype entreprise Server 2019**, puis sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1448f-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="1448f-115">Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="1448f-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="1448f-116">Vérifiez que tous les objets contact ont été déplacés vers le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1448f-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="1448f-117">Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="1448f-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="1448f-118">Vérifiez que tous les objets contact sont désormais associés au pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1448f-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


