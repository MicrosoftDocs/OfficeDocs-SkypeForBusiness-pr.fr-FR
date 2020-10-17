---
title: 'Lync Server 2013 : téléphones de partie commune'
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
ms.openlocfilehash: fb5039fe3e47668a17196a81316250d7c517e6e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526141"
---
# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="1c86b-102">Téléphones de partie commune dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c86b-102">Common area phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c86b-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="1c86b-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="1c86b-104">Les téléphones de partie commune sont des téléphones IP qui ne sont pas associés à un utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="1c86b-104">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="1c86b-105">Au lieu d’être situés dans le Bureau d’une personne, les téléphones de partie commune sont généralement situés dans des halls de construction, des cafétérias, des salons d’employés, des salles de réunion et dans d’autres emplacements susceptibles d’être rassemblés par un grand nombre de personnes.</span><span class="sxs-lookup"><span data-stu-id="1c86b-105">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="1c86b-106">Contrairement à d’autres téléphones dans Lync Server, qui sont généralement gérés à l’aide de stratégies de voix et de plans de numérotation attribués à des utilisateurs individuels, les téléphones de zone commune ne sont pas affectés à des utilisateurs individuels.</span><span class="sxs-lookup"><span data-stu-id="1c86b-106">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="1c86b-107">Cela signifie qu’ils doivent être gérés différemment de vos autres téléphones.</span><span class="sxs-lookup"><span data-stu-id="1c86b-107">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="1c86b-108">Pour gérer les téléphones de partie commune, vous créez des objets contact des services de domaine Active Directory pour tous vos téléphones de partie commune qui, comme les comptes d’utilisateur, peuvent se voir attribuer des stratégies et des plans vocaux.</span><span class="sxs-lookup"><span data-stu-id="1c86b-108">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="1c86b-109">Cette approche vous permet de maintenir le contrôle sur les téléphones de partie commune, même si ces téléphones ne sont pas associés à un utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="1c86b-109">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="1c86b-110">Utilisez les rubriques de cette section pour apprendre à créer des objets contact pour les téléphones de partie commune, pour les modifier et les supprimer, et pour configurer et afficher les informations de configuration concernant les téléphones de partie commune dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="1c86b-110">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c86b-111">Vous disposez de trois options pour les téléphones de partie commune : le téléphone de partie commune Aastra 6721ip, le téléphone IP HP 4110 et le téléphone de partie commune IP Polycom CX500.</span><span class="sxs-lookup"><span data-stu-id="1c86b-111">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="1c86b-112">Le téléphone de conférence IP Polycom CX3000 est un autre composant de partie commune.</span><span class="sxs-lookup"><span data-stu-id="1c86b-112">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="1c86b-113">Toutefois, il est destiné à être utilisé dans les salles de conférence.</span><span class="sxs-lookup"><span data-stu-id="1c86b-113">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="1c86b-114">Pour plus d’informations sur les téléphones de partie commune, consultez la section relative aux téléphones de partie commune sur la <A href="https://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">sélection de nouveaux appareils</A>.</span><span class="sxs-lookup"><span data-stu-id="1c86b-114">For details about common area phones, see the Common Area Phones section of <A href="https://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1c86b-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="1c86b-115">In This Section</span></span>

  - [<span data-ttu-id="1c86b-116">Afficher les informations de téléphone de partie commune dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c86b-116">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="1c86b-117">Création ou modification d’un objet contact de téléphone de partie commune dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c86b-117">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="1c86b-118">Activation ou désactivation de la connexion à chaud dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c86b-118">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="1c86b-119">Supprimer un objet contact de téléphone de partie commune dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c86b-119">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="1c86b-120">Affecter des stratégies dans Lync Server 2013 à un téléphone de partie commune</span><span class="sxs-lookup"><span data-stu-id="1c86b-120">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

