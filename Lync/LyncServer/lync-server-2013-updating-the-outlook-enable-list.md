---
title: 'Lync Server 2013 : mise à jour de la liste d’activations d’Outlook'
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
ms.openlocfilehash: f44de6e3b7756935829b008c585474e08f6f9969
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a><span data-ttu-id="f4699-102">Mise à jour de la liste d’activations d’Outlook dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4699-102">Updating the Outlook enable list in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4699-103">_**Dernière modification de la rubrique :** 2013-01-07_</span><span class="sxs-lookup"><span data-stu-id="f4699-103">_**Topic Last Modified:** 2013-01-07_</span></span>

<span data-ttu-id="f4699-104">Vous pouvez vous assurer que le complément réunion en ligne pour Microsoft Lync 2013 reste actif pour les utilisateurs en créant une stratégie qui l’inclut dans la liste de gestion des compléments pour Outlook.</span><span class="sxs-lookup"><span data-stu-id="f4699-104">You can ensure that Online Meeting Add-in for Microsoft Lync 2013 always remains enabled for users by creating a policy that includes it in the Add-in Management List for Outlook.</span></span> <span data-ttu-id="f4699-105">La stratégie de liste de gestion des compléments est incluse dans les fichiers de modèles d’administration Office pour la console de gestion des stratégies de groupe.</span><span class="sxs-lookup"><span data-stu-id="f4699-105">The Add-in Management List policy is included in the Office administrative template files for the Group Policy Management Console.</span></span> <span data-ttu-id="f4699-106">Il crée une clé de Registre sous\\stratégies\\\\logiciel HKCU\\Microsoft\\Office\\15,0\\Outlook15 résilience\\AddinList.</span><span class="sxs-lookup"><span data-stu-id="f4699-106">It creates a registry key under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList.</span></span> <span data-ttu-id="f4699-107">Vous pouvez ajouter une valeur à ucaddin. dll à cette clé et configurer la valeur ucaddin. dll de sorte qu’elle soit toujours activée et que les utilisateurs ne puissent pas la désactiver manuellement.</span><span class="sxs-lookup"><span data-stu-id="f4699-107">You can add a value for the ucaddin.dll to this key, and configure the ucaddin.dll value so that it is always enabled and so that users cannot manually disable it</span></span>

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a><span data-ttu-id="f4699-108">Pour ajouter ucaddin. dll à la liste des compléments Outlook</span><span class="sxs-lookup"><span data-stu-id="f4699-108">To Add ucaddin.dll to the Outlook Add-in List</span></span>

  - <span data-ttu-id="f4699-109">Pour la clé de Registre AddinList, située sous\\stratégies\\\\logicielles\\HKCU\\Microsoft\\Office\\15,0 Outlook15\\de résilience AddinList, ajoutez la valeur suivante :</span><span class="sxs-lookup"><span data-stu-id="f4699-109">To the AddinList registry key, located under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList, add the following value:</span></span>
    
      - <span data-ttu-id="f4699-110">Type de Registre =\_St SZ</span><span class="sxs-lookup"><span data-stu-id="f4699-110">Registry Type = REG\_SZ</span></span>
    
      - <span data-ttu-id="f4699-111">Nom = ucaddin. dll</span><span class="sxs-lookup"><span data-stu-id="f4699-111">Name = ucaddin.dll</span></span>
    
      - <span data-ttu-id="f4699-112">Valeur = 1 (indique que le complément est toujours activé et ne peut pas être géré par l’utilisateur final)</span><span class="sxs-lookup"><span data-stu-id="f4699-112">Value = 1 (specifies that the add-in is always enabled and cannot be managed by the end user)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

