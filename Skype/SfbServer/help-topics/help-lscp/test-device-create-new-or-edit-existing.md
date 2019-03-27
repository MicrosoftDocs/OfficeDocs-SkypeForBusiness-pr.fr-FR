---
title: Périphérique de test créer ou modifier une existant
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: La fonctionnalité Périphérique de test fonctionne conjointement à la fonctionnalité Mise à jour du périphérique. Vous pouvez ajouter un périphérique de test à la page Périphérique de test, puis l’utiliser pour vérifier les fonctionnalités des nouvelles mises à jour avant de les déployer sur des périphériques de production. Vous pouvez tester un périphérique globalement (dans tout votre environnement) ou sur un site unique. Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série. Lorsque vous ajoutez un périphérique, il s’affiche dans la liste dans la page périphérique de Test de la Skype pour le panneau de configuration serveur Business.
ms.openlocfilehash: 8f97ed387d8ce585fad64f3f4552ef1fb3eeb50f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877359"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="cd9e3-107">Périphérique de test : création d’un périphérique ou modification d’un périphérique existant</span><span class="sxs-lookup"><span data-stu-id="cd9e3-107">Test Device: Create New or Edit Existing</span></span>

<span data-ttu-id="cd9e3-108">La fonctionnalité Périphérique de test fonctionne conjointement à la fonctionnalité Mise à jour du périphérique.</span><span class="sxs-lookup"><span data-stu-id="cd9e3-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="cd9e3-109">Vous pouvez ajouter un périphérique de test à la page **Périphérique de test**, puis l’utiliser pour vérifier les fonctionnalités des nouvelles mises à jour avant de les déployer sur des périphériques de production.</span><span class="sxs-lookup"><span data-stu-id="cd9e3-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="cd9e3-110">Vous pouvez tester un périphérique globalement (dans tout votre environnement) ou sur un site unique.</span><span class="sxs-lookup"><span data-stu-id="cd9e3-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="cd9e3-111">Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série.</span><span class="sxs-lookup"><span data-stu-id="cd9e3-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="cd9e3-112">Lorsque vous ajoutez un périphérique, il s’affiche dans la liste dans la page **Périphérique de Test** de la Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="cd9e3-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="cd9e3-113">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="cd9e3-113">Tasks you can perform</span></span>

<span data-ttu-id="cd9e3-114">Dans la page **Nouveau périphérique de test** ou **Modifier le périphérique de test**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="cd9e3-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>

- <span data-ttu-id="cd9e3-115">Ajout d’un nouveau périphérique de test</span><span class="sxs-lookup"><span data-stu-id="cd9e3-115">Add a new test device.</span></span>

- <span data-ttu-id="cd9e3-116">Modification des propriétés d’un périphérique de test existant</span><span class="sxs-lookup"><span data-stu-id="cd9e3-116">Modify the properties of an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="cd9e3-117">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="cd9e3-117">UI Reference</span></span>

<span data-ttu-id="cd9e3-118">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="cd9e3-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="cd9e3-119">**Étendue** Identifie l’étendue (globale ou Site) du périphérique de test.</span><span class="sxs-lookup"><span data-stu-id="cd9e3-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>

- <span data-ttu-id="cd9e3-120">**Nom** Vous pouvez ajouter ou modifier le nom du périphérique de test.</span><span class="sxs-lookup"><span data-stu-id="cd9e3-120">**Name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="cd9e3-121">**Nom du périphérique** Vous pouvez ajouter ou modifier le nom du périphérique de test.</span><span class="sxs-lookup"><span data-stu-id="cd9e3-121">**Device name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="cd9e3-122">**Type d’identificateur** Vous pouvez sélectionner la méthode à utiliser pour identifier le périphérique en sélectionnant une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="cd9e3-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>

  - <span data-ttu-id="cd9e3-123">**Adresse MAC**</span><span class="sxs-lookup"><span data-stu-id="cd9e3-123">**MAC address**</span></span>

  - <span data-ttu-id="cd9e3-124">**Numéro de série**</span><span class="sxs-lookup"><span data-stu-id="cd9e3-124">**Serial number**</span></span>

- <span data-ttu-id="cd9e3-125">**Identificateur unique** Vous pouvez taper l’adresse MAC ou le numéro de série du périphérique.</span><span class="sxs-lookup"><span data-stu-id="cd9e3-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>

<span data-ttu-id="cd9e3-126">Pour plus d’informations sur le test des périphériques, reportez-vous à la rubrique [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) de la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="cd9e3-126">For details about testing devices, see [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="cd9e3-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cd9e3-127">See also</span></span>

[<span data-ttu-id="cd9e3-128">Périphérique de test</span><span class="sxs-lookup"><span data-stu-id="cd9e3-128">Test Device</span></span>](test-device.md)

[<span data-ttu-id="cd9e3-129">Nouvelle-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="cd9e3-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="cd9e3-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="cd9e3-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="cd9e3-131">View Software Updates for Devices dans votre organisation</span><span class="sxs-lookup"><span data-stu-id="cd9e3-131">View Software Updates for Devices in Your Organization</span></span>](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
