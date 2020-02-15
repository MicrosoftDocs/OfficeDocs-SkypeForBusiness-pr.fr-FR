---
title: 'Lync Server 2013 : mise à jour de la liste d’activation d’Outlook'
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
ms.openlocfilehash: 376c5788d535cd893b2261dcddcb1fe05d676005
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a><span data-ttu-id="e6aad-102">Mise à jour de la liste d’activation d’Outlook dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6aad-102">Updating the Outlook enable list in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6aad-103">_**Dernière modification de la rubrique :** 2013-01-07_</span><span class="sxs-lookup"><span data-stu-id="e6aad-103">_**Topic Last Modified:** 2013-01-07_</span></span>

<span data-ttu-id="e6aad-104">Vous pouvez vous assurer que le complément de réunion en ligne pour Microsoft Lync 2013 reste toujours activé pour les utilisateurs en créant une stratégie qui l’inclut dans la liste de gestion des compléments pour Outlook.</span><span class="sxs-lookup"><span data-stu-id="e6aad-104">You can ensure that Online Meeting Add-in for Microsoft Lync 2013 always remains enabled for users by creating a policy that includes it in the Add-in Management List for Outlook.</span></span> <span data-ttu-id="e6aad-105">La stratégie liste de gestion des compléments est incluse dans les fichiers de modèle d’administration Office pour la console de gestion des stratégies de groupe.</span><span class="sxs-lookup"><span data-stu-id="e6aad-105">The Add-in Management List policy is included in the Office administrative template files for the Group Policy Management Console.</span></span> <span data-ttu-id="e6aad-106">Il crée une clé de Registre sous\\les\\stratégies\\de\\logiciel\\HKCU\\Microsoft\\Office 15,0\\Outlook15 Resilience AddinList.</span><span class="sxs-lookup"><span data-stu-id="e6aad-106">It creates a registry key under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList.</span></span> <span data-ttu-id="e6aad-107">Vous pouvez ajouter une valeur pour ucaddin. dll à cette clé et configurer la valeur de ucaddin. dll de sorte qu’elle soit toujours activée et que les utilisateurs ne puissent pas la désactiver manuellement.</span><span class="sxs-lookup"><span data-stu-id="e6aad-107">You can add a value for the ucaddin.dll to this key, and configure the ucaddin.dll value so that it is always enabled and so that users cannot manually disable it</span></span>

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a><span data-ttu-id="e6aad-108">Pour ajouter ucaddin. dll à la liste des compléments Outlook</span><span class="sxs-lookup"><span data-stu-id="e6aad-108">To Add ucaddin.dll to the Outlook Add-in List</span></span>

  - <span data-ttu-id="e6aad-109">Dans la clé de Registre AddinList, située sous\\stratégies\\\\logicielles\\HKCU\\Microsoft\\Office\\15,0 Outlook15\\de résilience AddinList, ajoutez la valeur suivante :</span><span class="sxs-lookup"><span data-stu-id="e6aad-109">To the AddinList registry key, located under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList, add the following value:</span></span>
    
      - <span data-ttu-id="e6aad-110">Type de Registre =\_reg SZ</span><span class="sxs-lookup"><span data-stu-id="e6aad-110">Registry Type = REG\_SZ</span></span>
    
      - <span data-ttu-id="e6aad-111">Nom = ucaddin. dll</span><span class="sxs-lookup"><span data-stu-id="e6aad-111">Name = ucaddin.dll</span></span>
    
      - <span data-ttu-id="e6aad-112">Valeur = 1 (indique que le complément est toujours activé et qu’il ne peut pas être géré par l’utilisateur final)</span><span class="sxs-lookup"><span data-stu-id="e6aad-112">Value = 1 (specifies that the add-in is always enabled and cannot be managed by the end user)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

