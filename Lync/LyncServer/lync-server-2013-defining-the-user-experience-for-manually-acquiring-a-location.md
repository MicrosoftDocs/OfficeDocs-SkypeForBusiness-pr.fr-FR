---
title: Définition de l’interface utilisateur pour l’acquisition manuelle d’un emplacement
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the user experience for manually acquiring a location
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48185435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b5913547ab7d5030ca40070de36b4deb1f6a89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="d72f7-102">Définition de l’interface utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d72f7-102">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d72f7-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d72f7-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d72f7-p101">Si un client se trouve à l’extérieur du réseau ou dans un sous-réseau non défini, l’utilisateur peut entrer manuellement un emplacement. Mais pendant un appel d’urgence, l’appel sera tout d’abord acheminé vers un répartiteur de centre de réponse aux appels d’urgence (Emergency Call Response Center, ou ECRC) E9-1-1 national ou régional avant d’être acheminé vers un centre téléphonique de sécurité publique (Public Safety Answering Point, ou PSAP). L’ECRC demande verbalement un emplacement à l’appelant, puis transfère l’appel au PSAP approprié en fonction des informations renseignées.</span><span class="sxs-lookup"><span data-stu-id="d72f7-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span>

  - <span data-ttu-id="d72f7-107">**Les utilisateurs doivent-ils être invités à entrer un emplacement lorsque le service d’information d’emplacement n’est pas fourni automatiquement ?**</span><span class="sxs-lookup"><span data-stu-id="d72f7-107">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>  
    <span data-ttu-id="d72f7-108">Par exemple, si un client se trouve dans un sous-réseau non défini, au domicile de l’utilisateur, dans un hôtel ou ailleurs à l’extérieur du réseau, l’utilisateur doit-il entrer un emplacement ?</span><span class="sxs-lookup"><span data-stu-id="d72f7-108">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
    <span data-ttu-id="d72f7-p102">Vous pouvez configurer le paramètre **Emplacement requis** dans la stratégie d’emplacement pour définir le comportement du client. Si vous lui attribuez la valeur Non, l’utilisateur ne sera pas invité à entrer un emplacement. Si vous lui attribuez la valeur Oui, l’utilisateur sera invité à entrer un emplacement, mais pourra ignorer le message d’invite. Si vous lui attribuez la valeur Clause d’exclusion de responsabilité, l’utilisateur sera invité à entrer un emplacement, et une notification d’exclusion s’affichera s’il essaie d’ignorer le message d’invite. Dans tous les cas, l’utilisateur peut continuer à utiliser le client comme d’habitude.</span><span class="sxs-lookup"><span data-stu-id="d72f7-p102">You can configure the **Location Required** setting in the location policy to define the client behavior. Setting this value to No means that the user will not be prompted for a location. Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt. Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client as usual.</span></span>

<span data-ttu-id="d72f7-114">Lorsqu’un utilisateur entre manuellement à un emplacement, l’emplacement est mappé à l’adresse MAC de la passerelle par défaut du réseau du client et est stocké dans une table par utilisateur située sur le client.</span><span class="sxs-lookup"><span data-stu-id="d72f7-114">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client’s network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="d72f7-115">Lorsque l’utilisateur revient à un emplacement déjà stocké, le client Lync se positionne automatiquement à cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="d72f7-115">When the user returns to any previously stored location, the Lync client automatically sets itself to that location.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d72f7-116">Vous pouvez uniquement modifier l’emplacement actuel de votre client, mais vous pouvez supprimer les emplacements stockés dans la table des utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="d72f7-116">You can modify only the current location of your client, but you can also delete any location stored in the local user’s table.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

