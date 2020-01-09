---
title: Migrer des périphériques analogiques
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype entreprise Server prend en charge les appareils analogiques. Plus précisément, les appareils analogiques pris en charge sont les téléphones analogiques et les Fax analogiques. Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation d’appareils analogiques dans votre environnement Skype entreprise Server. Après la migration vers Skype entreprise Server 2019, vous devez également migrer les objets de contact associés aux périphériques analogiques. Utilisez Skype entreprise Server Management Shell pour récupérer tous les objets de contact associés aux périphériques analogiques hérités, puis déplacez ces objets vers le pool Skype entreprise Server 2019.
ms.openlocfilehash: 7ca36c92270685709c479a1d164f60d0960c526c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990089"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="b5c5a-107">Migrer des périphériques analogiques</span><span class="sxs-lookup"><span data-stu-id="b5c5a-107">Migrate analog devices</span></span>

<span data-ttu-id="b5c5a-108">Skype entreprise Server prend en charge les appareils analogiques.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="b5c5a-109">Plus précisément, les appareils analogiques pris en charge sont les téléphones analogiques et les Fax analogiques.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="b5c5a-110">Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation d’appareils analogiques dans votre environnement Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="b5c5a-111">Après la migration vers Skype entreprise Server 2019, vous devez également migrer les objets de contact associés aux périphériques analogiques.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="b5c5a-112">Utilisez Skype entreprise Server Management Shell pour récupérer tous les objets de contact associés aux périphériques analogiques hérités, puis déplacez ces objets vers le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="b5c5a-113">Pour migrer des périphériques analogiques</span><span class="sxs-lookup"><span data-stu-id="b5c5a-113">To migrate analog devices</span></span>

1. <span data-ttu-id="b5c5a-114">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Microsoft Skype entreprise Server 2019**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b5c5a-115">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="b5c5a-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="b5c5a-116">Vérifiez que tous les objets de contact ont été déplacés vers le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b5c5a-117">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="b5c5a-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="b5c5a-118">Vérifiez que tous les objets de contact sont désormais associés au pool 2019 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b5c5a-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


