---
title: Migration des périphériques analogiques
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
description: Skype Entreprise Server assure la prise en charge des périphériques analogiques. Les périphériques analogiques pris en charge sont plus précisément des téléphones audio analogiques et des télécopieurs analogiques. Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation de périphériques analogiques dans votre environnement Skype Entreprise Server. Après avoir migré vers Skype Entreprise Server 2019, vous devez également migrer les objets contact associés aux périphériques analogiques. Utilisez Skype Entreprise Server Management Shell pour d’abord récupérer tous les objets contact associés aux périphériques analogiques hérités, puis déplacer ces objets vers le pool Skype Entreprise Server 2019.
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752826"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="8da89-107">Migration des périphériques analogiques</span><span class="sxs-lookup"><span data-stu-id="8da89-107">Migrate analog devices</span></span>

<span data-ttu-id="8da89-108">Skype Entreprise Server assure la prise en charge des périphériques analogiques.</span><span class="sxs-lookup"><span data-stu-id="8da89-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="8da89-109">Les périphériques analogiques pris en charge sont plus précisément des téléphones audio analogiques et des télécopieurs analogiques.</span><span class="sxs-lookup"><span data-stu-id="8da89-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="8da89-110">Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation de périphériques analogiques dans votre environnement Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8da89-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="8da89-111">Après avoir migré vers Skype Entreprise Server 2019, vous devez également migrer les objets contact associés aux périphériques analogiques.</span><span class="sxs-lookup"><span data-stu-id="8da89-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="8da89-112">Utilisez Skype Entreprise Server Management Shell pour d’abord récupérer tous les objets contact associés aux périphériques analogiques hérités, puis déplacer ces objets vers le pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8da89-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="8da89-113">Pour migrer des périphériques analogiques</span><span class="sxs-lookup"><span data-stu-id="8da89-113">To migrate analog devices</span></span>

1. <span data-ttu-id="8da89-114">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Microsoft Skype Entreprise **Server 2019,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="8da89-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="8da89-115">Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="8da89-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="8da89-116">Vérifiez que tous les objets contact ont été déplacés vers le pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8da89-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="8da89-117">Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="8da89-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="8da89-118">Vérifiez que tous les objets contact sont désormais associés au pool Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8da89-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


