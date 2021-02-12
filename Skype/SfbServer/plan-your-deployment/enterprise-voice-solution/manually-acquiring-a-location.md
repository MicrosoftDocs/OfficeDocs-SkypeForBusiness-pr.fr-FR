---
title: Définir l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planification des utilisateurs itinérants dans un déploiement E9-1-1 à l’aide de fournisseurs de trunking SIP dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: dd43d78b4c139b4fb30a0b4ba379d96150314332
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825424"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a><span data-ttu-id="eeda8-103">Définir l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="eeda8-103">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>
 
<span data-ttu-id="eeda8-104">Planification des utilisateurs itinérants dans un déploiement E9-1-1 à l’aide de fournisseurs de trunking SIP dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="eeda8-104">Planning for roaming users in an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="eeda8-105">Si un client se trouve en dehors du réseau ou dans un sous-réseau non définie, l’utilisateur peut entrer manuellement un emplacement.</span><span class="sxs-lookup"><span data-stu-id="eeda8-105">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location.</span></span> <span data-ttu-id="eeda8-106">Toutefois, au cours d’un appel d’urgence, l’appel est d’abord acheminé vers un répartiteur de centre d’appels d’urgence (ECRC) E9-1-1 national/régional avant d’être acheminé vers un centre d’appels de sécurité publique (PSAP).</span><span class="sxs-lookup"><span data-stu-id="eeda8-106">But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="eeda8-107">La CERC interrogera verbalement l’appelant pour obtenir un emplacement, puis le fera suivre au PSAP approprié, en fonction des informations fournies.</span><span class="sxs-lookup"><span data-stu-id="eeda8-107">The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span> 
  
<span data-ttu-id="eeda8-108">**Les utilisateurs doivent-ils être invités à entrer un emplacement lorsqu’un emplacement n’est pas automatiquement fourni par le service Informations d’emplacement ?**</span><span class="sxs-lookup"><span data-stu-id="eeda8-108">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>
  
<span data-ttu-id="eeda8-109">Par exemple, si un client se trouve dans un sous-réseau non définie, à la maison, à l’hôtel ou n’importe où en dehors du réseau, l’utilisateur doit-il entrer un emplacement ?</span><span class="sxs-lookup"><span data-stu-id="eeda8-109">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
<span data-ttu-id="eeda8-110">Vous pouvez configurer le paramètre **Emplacement requis** dans la stratégie d’emplacement pour définir le comportement du client.</span><span class="sxs-lookup"><span data-stu-id="eeda8-110">You can configure the **Location Required** setting in the location policy to define the client behavior.</span></span> <span data-ttu-id="eeda8-111">La définition de cette valeur sur Non signifie que l’utilisateur ne sera pas invité à se rendre sur un emplacement.</span><span class="sxs-lookup"><span data-stu-id="eeda8-111">Setting this value to No means that the user will not be prompted for a location.</span></span> <span data-ttu-id="eeda8-112">La définition de cette valeur sur Oui signifie que l’utilisateur est invité à se rendre sur un emplacement, mais peut ignorer l’invite.</span><span class="sxs-lookup"><span data-stu-id="eeda8-112">Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="eeda8-113">La définition de cette valeur sur Disclaimer signifie que l’utilisateur est invité à se rendre sur un emplacement et qu’une clause d’exclusion de responsabilité s’affiche s’il tente d’ignorer l’invite.</span><span class="sxs-lookup"><span data-stu-id="eeda8-113">Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="eeda8-114">Dans tous les cas, l’utilisateur peut continuer à utiliser le client comme d’habitude.</span><span class="sxs-lookup"><span data-stu-id="eeda8-114">In all cases, the user can continue to use the client as usual.</span></span>
    
<span data-ttu-id="eeda8-115">Lorsqu’un utilisateur entre manuellement un emplacement, il est mappé à l’adresse MAC de la passerelle par défaut du réseau du client et stocké dans une table par utilisateur située sur le client.</span><span class="sxs-lookup"><span data-stu-id="eeda8-115">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client's network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="eeda8-116">Lorsque l’utilisateur retourne à un emplacement stocké précédemment, le client Skype Entreprise se définit automatiquement à cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="eeda8-116">When the user returns to any previously stored location, the Skype for Business client automatically sets itself to that location.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="eeda8-117">Vous pouvez modifier uniquement l’emplacement actuel de votre client, mais vous pouvez également supprimer n’importe quel emplacement stocké dans la table de l’utilisateur local.</span><span class="sxs-lookup"><span data-stu-id="eeda8-117">You can modify only the current location of your client, but you can also delete any location stored in the local user's table.</span></span> 
  

