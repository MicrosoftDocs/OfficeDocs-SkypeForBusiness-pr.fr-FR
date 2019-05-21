---
title: Migrer des périphériques analogiques
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype entreprise Server prend en charge les appareils analogiques. Plus précisément, les appareils analogiques pris en charge sont les téléphones analogiques et les Fax analogiques. Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation d’appareils analogiques dans votre environnement Skype entreprise Server. Après la migration vers Skype entreprise Server 2019, vous devez également migrer les objets de contact associés aux périphériques analogiques. Utilisez Skype entreprise Server Management Shell pour récupérer tous les objets de contact associés aux périphériques analogiques hérités, puis déplacez ces objets vers le pool Skype entreprise Server 2019.
ms.openlocfilehash: a822f8f73ad839654d266182172ef8e30d5d28e8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280842"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="21f5b-107">Migrer des périphériques analogiques</span><span class="sxs-lookup"><span data-stu-id="21f5b-107">Migrate analog devices</span></span>

<span data-ttu-id="21f5b-108">Skype entreprise Server prend en charge les appareils analogiques.</span><span class="sxs-lookup"><span data-stu-id="21f5b-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="21f5b-109">Plus précisément, les appareils analogiques pris en charge sont les téléphones analogiques et les Fax analogiques.</span><span class="sxs-lookup"><span data-stu-id="21f5b-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="21f5b-110">Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation d’appareils analogiques dans votre environnement Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="21f5b-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="21f5b-111">Après la migration vers Skype entreprise Server 2019, vous devez également migrer les objets de contact associés aux périphériques analogiques.</span><span class="sxs-lookup"><span data-stu-id="21f5b-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="21f5b-112">Utilisez Skype entreprise Server Management Shell pour récupérer tous les objets de contact associés aux périphériques analogiques hérités, puis déplacez ces objets vers le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="21f5b-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="21f5b-113">Pour migrer des périphériques analogiques</span><span class="sxs-lookup"><span data-stu-id="21f5b-113">To migrate analog devices</span></span>

1. <span data-ttu-id="21f5b-114">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Microsoft Skype entreprise Server 2019**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="21f5b-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="21f5b-115">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="21f5b-115">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="21f5b-116">Vérifiez que tous les objets de contact ont été déplacés vers le pool Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="21f5b-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="21f5b-117">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="21f5b-117">At the command line, type:</span></span>

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="21f5b-118">Vérifiez que tous les objets de contact sont désormais associés au pool 2019 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="21f5b-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


