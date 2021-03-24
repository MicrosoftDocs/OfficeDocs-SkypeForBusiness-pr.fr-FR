---
title: 'Périphérique de test : création d’un périphérique ou modification d’un périphérique existant'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: La fonctionnalité Périphérique de test fonctionne en conjonction avec la fonctionnalité Mise à jour du périphérique. Vous pouvez ajouter un périphérique de test à la page Périphérique de test, puis l’utiliser pour vérifier les fonctionnalités des nouvelles mises à jour avant de les déployer sur des périphériques de production. Vous pouvez tester un appareil globalement (dans l’ensemble de votre environnement) ou au sein d’un site unique. Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série. Lorsque vous ajoutez un appareil, celui-ci apparaît dans la liste de la page Périphérique de test du Panneau de contrôle Skype Entreprise Server.
ms.openlocfilehash: 6a472923040dbf1101044a28667cb1358399f808
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099370"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="f585c-107">Test d’appareil : création d’un nouveau ou modification d’un test existant</span><span class="sxs-lookup"><span data-stu-id="f585c-107">Test Device: Create New or Edit Existing</span></span>

<span data-ttu-id="f585c-108">La fonctionnalité Périphérique de test fonctionne en conjonction avec la fonctionnalité Mise à jour du périphérique.</span><span class="sxs-lookup"><span data-stu-id="f585c-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="f585c-109">Vous pouvez ajouter un périphérique de test à la page **Périphérique de test**, puis l’utiliser pour vérifier les fonctionnalités des nouvelles mises à jour avant de les déployer sur des périphériques de production.</span><span class="sxs-lookup"><span data-stu-id="f585c-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="f585c-110">Vous pouvez tester un appareil globalement (dans l’ensemble de votre environnement) ou au sein d’un site unique.</span><span class="sxs-lookup"><span data-stu-id="f585c-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="f585c-111">Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série.</span><span class="sxs-lookup"><span data-stu-id="f585c-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="f585c-112">Lorsque vous ajoutez un appareil, celui-ci apparaît dans la liste de la page Périphérique de **test** du Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f585c-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="f585c-113">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="f585c-113">Tasks you can perform</span></span>

<span data-ttu-id="f585c-114">Vous pouvez effectuer les tâches suivantes dans la page **Nouveau périphérique de test** ou **Modifier le périphérique de test** :</span><span class="sxs-lookup"><span data-stu-id="f585c-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>

- <span data-ttu-id="f585c-115">Ajouter un nouveau périphérique de test</span><span class="sxs-lookup"><span data-stu-id="f585c-115">Add a new test device.</span></span>

- <span data-ttu-id="f585c-116">Modifier les propriétés d’un périphérique de test existant</span><span class="sxs-lookup"><span data-stu-id="f585c-116">Modify the properties of an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="f585c-117">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="f585c-117">UI Reference</span></span>

<span data-ttu-id="f585c-118">Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="f585c-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="f585c-119">**Étendue** Identifie l’étendue (globale ou site) du périphérique de test.</span><span class="sxs-lookup"><span data-stu-id="f585c-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>

- <span data-ttu-id="f585c-120">**Nom** Vous pouvez ajouter ou modifier le nom du périphérique de test.</span><span class="sxs-lookup"><span data-stu-id="f585c-120">**Name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="f585c-121">**Nom de l’appareil** Vous pouvez ajouter ou modifier le nom du périphérique de test.</span><span class="sxs-lookup"><span data-stu-id="f585c-121">**Device name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="f585c-122">**Type d’identificateur** Vous pouvez sélectionner la méthode à utiliser pour identifier l’appareil en sélectionnant l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f585c-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>

  - <span data-ttu-id="f585c-123">**Adresse MAC**</span><span class="sxs-lookup"><span data-stu-id="f585c-123">**MAC address**</span></span>

  - <span data-ttu-id="f585c-124">**Numéro de série**</span><span class="sxs-lookup"><span data-stu-id="f585c-124">**Serial number**</span></span>

- <span data-ttu-id="f585c-125">**Identificateur unique** Vous pouvez taper l’adresse MAC ou le numéro de série de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="f585c-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>

<span data-ttu-id="f585c-126">Pour plus d’informations sur le test des périphériques, voir [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="f585c-126">For details about testing devices, see [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="f585c-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f585c-127">See also</span></span>

[<span data-ttu-id="f585c-128">Périphérique de test</span><span class="sxs-lookup"><span data-stu-id="f585c-128">Test Device</span></span>](test-device.md)

[<span data-ttu-id="f585c-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="f585c-129">New-CsTestDevice</span></span>](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="f585c-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="f585c-130">Set-CsTestDevice</span></span>](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="f585c-131">Afficher des mises à jour logicielles pour les périphériques dans votre entreprise</span><span class="sxs-lookup"><span data-stu-id="f585c-131">View Software Updates for Devices in Your Organization</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)