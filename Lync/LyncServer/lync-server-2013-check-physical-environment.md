---
title: 'Lync Server 2013 : vérifier l’environnement physique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing physical environmental checks
ms:assetid: 153aee5e-3adf-4dbf-bf41-53e4fba51fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720558(v=OCS.15)
ms:contentKeyID: 63969582
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e85f99250161433ba895f287521367d1b76cec1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="eb159-102">Effectuer des vérifications environnementales physiques</span><span class="sxs-lookup"><span data-stu-id="eb159-102">Performing physical environmental checks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb159-103">_**Dernière modification de la rubrique :** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="eb159-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="eb159-104">Avant de vérifier les performances, la disponibilité et les fonctionnalités du déploiement Lync Server 2013, vous devez vérifier l’environnement physique.</span><span class="sxs-lookup"><span data-stu-id="eb159-104">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="eb159-105">Par exemple, il se peut que la température de la salle serveur soit abaissée ou qu’un câble réseau doit être remplacé.</span><span class="sxs-lookup"><span data-stu-id="eb159-105">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="eb159-106">Pour obtenir de meilleurs résultats, effectuez les inspections environnementales physiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="eb159-106">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="eb159-107">**Mesures de sécurité physique les mesures**   de sécurité physique, telles que les verrous, les portes et les salles d’accès restreints, doivent être sécurisées.</span><span class="sxs-lookup"><span data-stu-id="eb159-107">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="eb159-108">Recherchez les entrées non autorisées et forcées et les signes d'endommagement des équipements.</span><span class="sxs-lookup"><span data-stu-id="eb159-108">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="eb159-109">**Température et humidité**   haute température, faible débit d’air et humidité peuvent entraîner une surchauffe des composants matériels.</span><span class="sxs-lookup"><span data-stu-id="eb159-109">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="eb159-110">Vérifiez la température et l’humidité afin de vous assurer que les systèmes environnementaux, tels que le chauffage et l’air conditionné, peuvent conserver des conditions et des fonctions acceptables dans les spécifications du fabricant du matériel.</span><span class="sxs-lookup"><span data-stu-id="eb159-110">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="eb159-111">Lors de l’installation récente d’un nouvel équipement, vérifiez également que le débit d’air à la fois vers et à partir des serveurs n’est pas entravé et conforme aux spécifications du fabricant.</span><span class="sxs-lookup"><span data-stu-id="eb159-111">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="eb159-112">**Périphériques et composants**   l’organisation Lync Server 2013 repose sur un réseau physique opérationnel et sur le matériel associé.</span><span class="sxs-lookup"><span data-stu-id="eb159-112">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="eb159-113">Assurez-vous que les routeurs, commutateurs, concentrateurs, câbles physiques et connecteurs sont opérationnels.</span><span class="sxs-lookup"><span data-stu-id="eb159-113">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="eb159-114">Les spécificités relatives à l’exécution de ces tests dépendront en grande fonction de votre site d’installation et du matériel de serveur choisi.</span><span class="sxs-lookup"><span data-stu-id="eb159-114">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="eb159-115">La première fois que vous effectuez cette vérification, reportez-vous à la documentation du matériel et notez les paramètres souhaités à des fins de référence ultérieure.</span><span class="sxs-lookup"><span data-stu-id="eb159-115">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="eb159-116">Environnement d’espace serveur souhaité</span><span class="sxs-lookup"><span data-stu-id="eb159-116">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb159-117">Paramètre</span><span class="sxs-lookup"><span data-stu-id="eb159-117">Parameter</span></span></th>
<th><span data-ttu-id="eb159-118">Valeur ou plage souhaitée</span><span class="sxs-lookup"><span data-stu-id="eb159-118">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb159-119">Régulation</span><span class="sxs-lookup"><span data-stu-id="eb159-119">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb159-120">Humid</span><span class="sxs-lookup"><span data-stu-id="eb159-120">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb159-121">Face avant des faces de serveur</span><span class="sxs-lookup"><span data-stu-id="eb159-121">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="eb159-122">Allée chaude/allée de froid</span><span class="sxs-lookup"><span data-stu-id="eb159-122">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb159-123">Dégagement d’échappement inentravé</span><span class="sxs-lookup"><span data-stu-id="eb159-123">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

