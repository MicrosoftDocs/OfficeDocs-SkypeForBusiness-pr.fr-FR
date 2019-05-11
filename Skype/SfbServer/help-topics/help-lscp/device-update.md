---
title: Mise à jour du périphérique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft publie régulièrement un nouveau jeu de mises à jour du microprogramme de périphérique pour Skype pour téléphone professionnel, que vous pouvez importer à vos serveurs et distribuer aux utilisateurs. Vous pouvez obtenir le dernier jeu de règles de mise à jour des périphériques en accédant à la page aide et Support sur le site Web Microsoft et recherche forPhone Edition.Download le dernier package de mise à jour et extrayez les fichiers dans un dossier sur l’ordinateur où les mises à jour doivent être téléchargées. Une fois les fichiers extraits, vous pouvez utiliser l’applet de commande Import-CsDeviceUpdate pour importer les règles de mise à jour des périphériques présentes dans le fichier CAB extrait (nommé UCUpdates.cab). Pour plus d’informations, voir Import-CsDeviceUpdate.
ms.openlocfilehash: 9e3d553357131c2e0f9e0b0bcef1329f5d2a4104
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902817"
---
# <a name="device-update"></a><span data-ttu-id="1083a-106">Mise à jour de l'appareil</span><span class="sxs-lookup"><span data-stu-id="1083a-106">Device Update</span></span>

<span data-ttu-id="1083a-107">Microsoft publie régulièrement un nouveau jeu de mises à jour du microprogramme de périphérique pour Skype pour téléphone professionnel, que vous pouvez importer à vos serveurs et distribuer aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1083a-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="1083a-108">Vous pouvez obtenir le dernier jeu de règles de mise à jour des périphériques en accédant à la page Aide et support du site web Microsoft et en recherchant « Phone Edition ».</span><span class="sxs-lookup"><span data-stu-id="1083a-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="1083a-109">Téléchargez le dernier package de mise à jour et extrayez les fichiers vers un dossier sur l’ordinateur destiné à contenir les mises à jours.</span><span class="sxs-lookup"><span data-stu-id="1083a-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="1083a-110">Une fois les fichiers extraits, vous pouvez utiliser l’applet de commande **Import-CsDeviceUpdate** pour importer les règles de mise à jour des périphériques présentes dans le fichier CAB extrait (nommé UCUpdates.cab).</span><span class="sxs-lookup"><span data-stu-id="1083a-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="1083a-111">Pour plus d’informations, voir [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1083a-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="1083a-112">Une fois les règles de mise à jour des périphériques ont été importées, vous pouvez utiliser la page **Mettre à jour des périphériques** pour afficher et gérer ces règles pour les périphériques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1083a-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="1083a-113">Vous pouvez tester les mises à jour de microprogramme, puis, si le test réussit, appliquer les mises à jour disponibles à tous les périphériques appropriés utilisés dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="1083a-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="1083a-114">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="1083a-114">Tasks you can perform</span></span>

<span data-ttu-id="1083a-115">Dans la page **Mise à jour du périphérique**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="1083a-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="1083a-116">Approbation des mises à jour de périphérique répertoriées</span><span class="sxs-lookup"><span data-stu-id="1083a-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="1083a-117">Annulation ou restauration des mises à jour de périphérique en attente</span><span class="sxs-lookup"><span data-stu-id="1083a-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="1083a-118">Suppression des mises à jour de périphérique de la liste</span><span class="sxs-lookup"><span data-stu-id="1083a-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="1083a-119">Référence d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="1083a-119">UI Reference</span></span>

<span data-ttu-id="1083a-120">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="1083a-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="1083a-121">**Modifier** Vous pouvez utiliser cette option pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1083a-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="1083a-122">**Sélectionner tout** Cette option sélectionne toutes les mises à jour des périphériques dans la liste.</span><span class="sxs-lookup"><span data-stu-id="1083a-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="1083a-123">**Supprimer** Cette option supprime toutes les mises à jour de périphérique sélectionné.</span><span class="sxs-lookup"><span data-stu-id="1083a-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="1083a-124">**Action** Vous pouvez sélectionner une ou plusieurs mises à jour dans la liste, effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1083a-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="1083a-125">**Annuler en attente des mises à jour** Cette option empêche la mise à jour sélectionnée de déployés sur les périphériques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1083a-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="1083a-126">**Approuver** Cette option permet la mise à jour sélectionnée à déployer sur les périphériques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1083a-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="1083a-127">**Restaurer** Cette option permet une mise à jour précédemment approuvée être déployées sur des périphériques de votre organisation</span><span class="sxs-lookup"><span data-stu-id="1083a-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="1083a-128">**Actualiser** Vous pouvez actualiser la liste pour vérifier l’état de toutes les mises à jour des périphériques.</span><span class="sxs-lookup"><span data-stu-id="1083a-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="1083a-129">Pour plus d’informations sur le service web de mise à jour des appareils, reportez-vous à la rubrique [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) de la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="1083a-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="1083a-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1083a-130">See also</span></span>

[<span data-ttu-id="1083a-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="1083a-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
