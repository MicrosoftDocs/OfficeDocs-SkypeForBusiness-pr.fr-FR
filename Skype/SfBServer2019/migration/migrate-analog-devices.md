---
title: Migrer des périphériques analogiques
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype pour Business Server prend en charge pour les périphériques analogiques. Plus précisément, les périphériques analogiques pris en charge sont des téléphones audio analogiques et télécopieurs analogiques. Vous pouvez configurer les passerelles complets pour prendre en charge l’utilisation de périphériques analogiques dans votre Skype pour un environnement de serveur d’entreprise. Après avoir migré vers Skype pour Business Server 2019, vous devez également migrer les objets contact associés avec les périphériques analogiques. Utiliser Skype pour Business Server Management Shell pour premier récupérer tous les contacts associés les périphériques analogiques hérités, puis déplacer ces objets vers le Skype pour Business Server 2019 pool.
ms.openlocfilehash: ea100f4e26cc38d5eb30f881de61bf415110ca36
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374849"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="2a861-107">Migrer des périphériques analogiques</span><span class="sxs-lookup"><span data-stu-id="2a861-107">Migrate analog devices</span></span>

<span data-ttu-id="2a861-108">Skype pour Business Server prend en charge pour les périphériques analogiques.</span><span class="sxs-lookup"><span data-stu-id="2a861-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="2a861-109">Plus précisément, les périphériques analogiques pris en charge sont des téléphones audio analogiques et télécopieurs analogiques.</span><span class="sxs-lookup"><span data-stu-id="2a861-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="2a861-110">Vous pouvez configurer les passerelles complets pour prendre en charge l’utilisation de périphériques analogiques dans votre Skype pour un environnement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="2a861-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="2a861-111">Après avoir migré vers Skype pour Business Server 2019, vous devez également migrer les objets contact associés avec les périphériques analogiques.</span><span class="sxs-lookup"><span data-stu-id="2a861-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="2a861-112">Utiliser Skype pour Business Server Management Shell pour premier récupérer tous les contacts associés les périphériques analogiques hérités, puis déplacer ces objets vers le Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="2a861-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="2a861-113">Pour migrer des périphériques analogiques</span><span class="sxs-lookup"><span data-stu-id="2a861-113">To migrate analog devices</span></span>

1. <span data-ttu-id="2a861-114">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Microsoft Skype pour Business Server 2019**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2a861-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="2a861-115">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="2a861-115">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="2a861-116">Vérifiez que tous les objets contact ont été déplacés vers le Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="2a861-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="2a861-117">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="2a861-117">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="2a861-118">Vérifiez que tous les objets contact sont désormais associé à la Skype pour Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="2a861-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


