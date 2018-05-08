---
title: Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planification pour des utilisateurs itinérants dans un déploiement E9-1-1 à l’aide de fournisseurs d’acheminement SIP dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 3e5c8776768212c6be179700a33261382949deee
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server-2015"></a><span data-ttu-id="08b82-103">Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="08b82-103">Define the user experience for manually acquiring a location in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="08b82-104">Planification pour des utilisateurs itinérants dans un déploiement E9-1-1 à l’aide de fournisseurs d’acheminement SIP dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="08b82-104">Planning for roaming users in an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="08b82-p101">Si un client se trouve à l’extérieur du réseau ou dans un sous-réseau non défini, l’utilisateur peut entrer manuellement un emplacement. Mais pendant un appel d’urgence, l’appel sera tout d’abord acheminé vers un répartiteur de centre de réponse aux appels d’urgence (Emergency Call Response Center, ou ECRC) E9-1-1 national ou régional avant d’être acheminé vers un centre téléphonique de sécurité publique (Public Safety Answering Point, ou PSAP). L’ECRC demande verbalement un emplacement à l’appelant, puis transfère l’appel au PSAP approprié en fonction des informations renseignées.</span><span class="sxs-lookup"><span data-stu-id="08b82-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span> 
  
<span data-ttu-id="08b82-108">**Les utilisateurs doivent être invités à entrer un emplacement lorsqu’elle n’est pas automatiquement fournie par le service informations d’emplacement ?**</span><span class="sxs-lookup"><span data-stu-id="08b82-108">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>
  
<span data-ttu-id="08b82-109">Par exemple, si un client se trouve dans un sous-réseau non défini, au domicile de l’utilisateur, dans un hôtel ou ailleurs à l’extérieur du réseau, l’utilisateur doit-il entrer un emplacement ?</span><span class="sxs-lookup"><span data-stu-id="08b82-109">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
<span data-ttu-id="08b82-p102">Vous pouvez configurer le paramètre **Emplacement requis** dans la stratégie d’emplacement pour définir le comportement du client. Si vous lui attribuez la valeur Non, l’utilisateur ne sera pas invité à entrer un emplacement. Si vous lui attribuez la valeur Oui, l’utilisateur sera invité à entrer un emplacement, mais pourra ignorer le message d’invite. Si vous lui attribuez la valeur Clause d’exclusion de responsabilité, l’utilisateur sera invité à entrer un emplacement, et une notification d’exclusion s’affichera s’il essaie d’ignorer le message d’invite. Dans tous les cas, l’utilisateur peut continuer à utiliser le client comme d’habitude.</span><span class="sxs-lookup"><span data-stu-id="08b82-p102">You can configure the **Location Required** setting in the location policy to define the client behavior. Setting this value to No means that the user will not be prompted for a location. Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt. Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client as usual.</span></span>
    
<span data-ttu-id="08b82-115">Lorsqu’un utilisateur entre manuellement un emplacement, l’emplacement est mappé à l’adresse MAC de la passerelle par défaut du réseau du client et est stocké dans une table par utilisateur située sur le client.</span><span class="sxs-lookup"><span data-stu-id="08b82-115">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client's network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="08b82-116">Lorsque l’utilisateur revient à n’importe quel emplacement stocké précédemment, la Skype pour client Business lui-même définit automatiquement à cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="08b82-116">When the user returns to any previously stored location, the Skype for Business client automatically sets itself to that location.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="08b82-117">Vous pouvez modifier uniquement l’emplacement actuel de votre client, mais vous pouvez également supprimer les emplacements stockés dans la table de l’utilisateur local.</span><span class="sxs-lookup"><span data-stu-id="08b82-117">You can modify only the current location of your client, but you can also delete any location stored in the local user's table.</span></span> 
  

