---
title: 'Lync Server 2013 : règles de mise à jour d’appareils'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update rules
ms:assetid: a2f7e293-3342-4566-9605-410cb95f3b3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994062(v=OCS.15)
ms:contentKeyID: 51803973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4912497f1c8481d44b02a0213e01a0e8908ebfa2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="92db8-102">Règles de mise à jour des appareils dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92db8-102">Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92db8-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="92db8-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="92db8-104">Périodiquement, Microsoft publie un nouvel ensemble de mises à jour de microprogramme de périphérique pour Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="92db8-104">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="92db8-105">Les *règles de mise à jour* de l’appareil associent les mises à jour du microprogramme aux périphériques matériels (téléphones et autres appareils exécutant Lync Phone Edition).</span><span class="sxs-lookup"><span data-stu-id="92db8-105">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="92db8-106">Pour obtenir le dernier ensemble de règles de mise à jour de l’appareil, accédez à la page aide et support sur le site Web de Microsoft et recherchez « Phone Edition ».</span><span class="sxs-lookup"><span data-stu-id="92db8-106">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="92db8-107">Téléchargez le package de mise à jour et extrayez les fichiers vers un dossier sur l’ordinateur sur lequel les mises à jour doivent être téléchargées.</span><span class="sxs-lookup"><span data-stu-id="92db8-107">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="92db8-108">Une fois les fichiers extraits, importez les règles de mise à jour de l’appareil trouvées dans le fichier extrait. Le fichier CAB (qui porte le nom UCUpdates. cab).</span><span class="sxs-lookup"><span data-stu-id="92db8-108">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="92db8-109">Utilisez ensuite le panneau de configuration de Lync Server ou les applets de commande Windows PowerShell pour afficher et gérer ces règles pour les appareils de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="92db8-109">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="92db8-110">Les rubriques suivantes vous expliquent comment importer, afficher et gérer des règles de mise à jour d’appareil.</span><span class="sxs-lookup"><span data-stu-id="92db8-110">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="92db8-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="92db8-111">In This Section</span></span>

  - [<span data-ttu-id="92db8-112">Afficher des informations sur les règles de mise à jour des appareils dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92db8-112">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="92db8-113">Importer des règles de mise à jour de périphériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92db8-113">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="92db8-114">Approuver une règle de mise à jour d’appareil dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92db8-114">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="92db8-115">Supprimer une règle de mise à jour d’appareil dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92db8-115">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="92db8-116">Réinitialiser une règle de mise à jour d’appareil dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92db8-116">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="92db8-117">Restaurer une règle de mise à jour d’appareil dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92db8-117">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

