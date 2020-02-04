---
title: 'Lync Server 2013 : téléphones de zone commune'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common area phones
ms:assetid: d63bb3de-154e-4347-9251-9fa94e7d593a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994076(v=OCS.15)
ms:contentKeyID: 51803987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71fa61773a4801d2050d67d4e86458eb5d37759c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="cb8a8-102">Numéros de téléphone communs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb8a8-102">Common area phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb8a8-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="cb8a8-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="cb8a8-104">Les téléphones portables courants sont des téléphones IP qui ne sont pas associés à un utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-104">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="cb8a8-105">Au lieu d’être localisé dans le Bureau d’une personne, les téléphones communs sont généralement situés dans des couloirs de bâtiment, des cafétérias, des salons d’employés, des salles de réunion et d’autres emplacements dans lesquels un grand nombre de personnes est susceptible de se réunir.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-105">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="cb8a8-106">Contrairement aux autres téléphones dans Lync Server, qui sont généralement conservés à l’aide de stratégies vocales et de plans de numérotation qui sont attribués à des utilisateurs individuels, les téléphones ordinaires n’ont pas d’utilisateurs individuels.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-106">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="cb8a8-107">Cela signifie qu’elles doivent être gérées différemment de celles de vos autres téléphones.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-107">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="cb8a8-108">Pour gérer les téléphones portables courants, vous devez créer des objets de contact services de domaine Active Directory (AD FS) pour tous vos numéros de téléphone communs, qui, tels que les comptes d’utilisateurs, peuvent être affectés à des stratégies et des plans vocaux.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-108">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="cb8a8-109">Cette approche permet de garder le contrôle sur des téléphones courants, même si ces téléphones ne sont pas associés à un utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-109">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="cb8a8-110">Les rubriques de cette section vous permettent d’apprendre à créer des objets de contact pour les téléphones communs, à les modifier ou à les supprimer, ainsi qu’à configurer et afficher des informations de configuration sur les téléphones communs dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-110">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cb8a8-111">Trois options s’offrent à vous pour les téléphones de zone commune : le téléphone local Aastra 6721ip, le téléphone IP HP 4110 et le téléphone local IP Polycom CX500.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-111">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="cb8a8-112">Le numéro de téléphone de la Conférence rendez-vous d’Polycom CX3000 est une variante.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-112">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="cb8a8-113">Il est toutefois destiné à une utilisation dans des salles de conférence.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-113">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="cb8a8-114">Pour plus d’informations sur les téléphones portables courants, voir la section téléphones communs pour le <A href="http://technet.microsoft.com/en-us/library/gg398958(v=ocs.14).aspx">choix de nouveaux périphériques</A>.</span><span class="sxs-lookup"><span data-stu-id="cb8a8-114">For details about common area phones, see the Common Area Phones section of <A href="http://technet.microsoft.com/en-us/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cb8a8-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="cb8a8-115">In This Section</span></span>

  - [<span data-ttu-id="cb8a8-116">Afficher des informations sur le téléphone de zone commune dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb8a8-116">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="cb8a8-117">Création ou modification d’un objet de contact pour les téléphones communs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb8a8-117">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="cb8a8-118">Activer ou désactiver la gestion de l’accès à chaud dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb8a8-118">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="cb8a8-119">Supprimer un objet de contact de téléphone pour les zones communes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb8a8-119">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="cb8a8-120">Attribuer des stratégies dans Lync Server 2013 à un téléphone de zone commune</span><span class="sxs-lookup"><span data-stu-id="cb8a8-120">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

