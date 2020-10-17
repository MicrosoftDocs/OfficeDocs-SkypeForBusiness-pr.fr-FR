---
title: 'Lync Server 2013 : mise à jour de la liste d’activation d’Outlook'
description: 'Lync Server 2013 : mise à jour de la liste d’activation d’Outlook.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96edc327fa1b63d5da95eb6ea36a2296659910d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546230"
---
# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a><span data-ttu-id="190ab-103">Mise à jour de la liste d’activation d’Outlook dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="190ab-103">Updating the Outlook enable list in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="190ab-104">_**Dernière modification de la rubrique :** 2013-01-07_</span><span class="sxs-lookup"><span data-stu-id="190ab-104">_**Topic Last Modified:** 2013-01-07_</span></span>

<span data-ttu-id="190ab-105">Vous pouvez vous assurer que le complément de réunion en ligne pour Microsoft Lync 2013 reste toujours activé pour les utilisateurs en créant une stratégie qui l’inclut dans la liste de gestion des compléments pour Outlook.</span><span class="sxs-lookup"><span data-stu-id="190ab-105">You can ensure that Online Meeting Add-in for Microsoft Lync 2013 always remains enabled for users by creating a policy that includes it in the Add-in Management List for Outlook.</span></span> <span data-ttu-id="190ab-106">La stratégie liste de gestion des compléments est incluse dans les fichiers de modèle d’administration Office pour la console de gestion des stratégies de groupe.</span><span class="sxs-lookup"><span data-stu-id="190ab-106">The Add-in Management List policy is included in the Office administrative template files for the Group Policy Management Console.</span></span> <span data-ttu-id="190ab-107">Il crée une clé de Registre sous les \\ stratégies de logiciel HKCU \\ \\ Microsoft \\ Office \\ 15,0 \\ Outlook15 \\ Resilience \\ AddinList.</span><span class="sxs-lookup"><span data-stu-id="190ab-107">It creates a registry key under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList.</span></span> <span data-ttu-id="190ab-108">Vous pouvez ajouter une valeur pour l' ucaddin.dll à cette clé et configurer la valeur de ucaddin.dll de sorte qu’elle soit toujours activée et que les utilisateurs ne puissent pas la désactiver manuellement.</span><span class="sxs-lookup"><span data-stu-id="190ab-108">You can add a value for the ucaddin.dll to this key, and configure the ucaddin.dll value so that it is always enabled and so that users cannot manually disable it</span></span>

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a><span data-ttu-id="190ab-109">Pour ajouter des ucaddin.dll à la liste des compléments Outlook</span><span class="sxs-lookup"><span data-stu-id="190ab-109">To Add ucaddin.dll to the Outlook Add-in List</span></span>

  - <span data-ttu-id="190ab-110">Dans la clé de Registre AddinList, située sous \\ stratégies logicielles HKCU \\ \\ Microsoft \\ Office \\ 15,0 \\ Outlook15 \\ de résilience \\ AddinList, ajoutez la valeur suivante :</span><span class="sxs-lookup"><span data-stu-id="190ab-110">To the AddinList registry key, located under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList, add the following value:</span></span>
    
      - <span data-ttu-id="190ab-111">Type de Registre = REG \_ SZ</span><span class="sxs-lookup"><span data-stu-id="190ab-111">Registry Type = REG\_SZ</span></span>
    
      - <span data-ttu-id="190ab-112">Nom = ucaddin.dll</span><span class="sxs-lookup"><span data-stu-id="190ab-112">Name = ucaddin.dll</span></span>
    
      - <span data-ttu-id="190ab-113">Valeur = 1 (indique que le complément est toujours activé et qu’il ne peut pas être géré par l’utilisateur final)</span><span class="sxs-lookup"><span data-stu-id="190ab-113">Value = 1 (specifies that the add-in is always enabled and cannot be managed by the end user)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

