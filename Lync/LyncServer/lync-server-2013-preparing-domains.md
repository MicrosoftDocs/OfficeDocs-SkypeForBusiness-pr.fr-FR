---
title: 'Lync Server 2013 : Préparation des domaines'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c1f5693a14084627d20ae66fa6ec85f6b6c6c6f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a><span data-ttu-id="bac6e-102">Préparation des domaines pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bac6e-102">Preparing domains for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bac6e-103">_**Dernière modification de la rubrique:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="bac6e-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="bac6e-104">La préparation du domaine est l’étape finale de la préparation des services de domaine Active Directory pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bac6e-104">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span> <span data-ttu-id="bac6e-105">L’étape de préparation du domaine ajoute les entrées de contrôle d’accès (ACE) nécessaires aux groupes universels qui permettent d’héberger et de gérer les utilisateurs au sein du domaine.</span><span class="sxs-lookup"><span data-stu-id="bac6e-105">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="bac6e-106">La préparation de domaine crée des ACE à la racine du domaine et dans trois conteneurs intégrés : Utilisateur, Ordinateurs et Contrôleurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="bac6e-106">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="bac6e-107">Vous pouvez exécuter une préparation de domaine sur n’importe quel ordinateur du domaine sur lequel vous déployez Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bac6e-107">You can run domain preparation on any computer in the domain where you are deploying Lync Server.</span></span> <span data-ttu-id="bac6e-108">Vous devez préparer chacun des domaines qui hébergeront Lync Server ou des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bac6e-108">You must prepare every domain that will host Lync Server or users.</span></span>

<span data-ttu-id="bac6e-109">Si l’héritage des autorisations est désactivé ou que les autorisations des utilisateurs authentifiées sont désactivées au sein de votre organisation, vous devez effectuer des étapes supplémentaires lors de la préparation du domaine.</span><span class="sxs-lookup"><span data-stu-id="bac6e-109">If permissions inheritance is disabled or authenticated user permissions are disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="bac6e-110">Pour plus d’informations, reportez-vous à [la rubrique préparation d’un service de domaine Active Directory verrouillé dans Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="bac6e-110">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

<span data-ttu-id="bac6e-111">Si votre organisation utilise des unités d’organisation au lieu des trois conteneurs intégrés (c’est-à-dire, utilisateurs, ordinateurs et contrôleurs de domaine), vous devez accorder l’accès en lecture aux UO pour le groupe utilisateurs authentifiés.</span><span class="sxs-lookup"><span data-stu-id="bac6e-111">If your organization uses organizational units (OU) instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the OUs for the Authenticated Users group.</span></span> <span data-ttu-id="bac6e-112">L’accès en lecture aux conteneurs est requis pour la préparation du domaine.</span><span class="sxs-lookup"><span data-stu-id="bac6e-112">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="bac6e-113">Si le groupe utilisateurs authentifiés ne dispose pas d’un accès en lecture à l’unité d’organisation, exécutez l’applet de commande **Grant-CsOuPermission** comme illustré dans les exemples de code suivants pour accorder des autorisations de lecture pour chaque unité d’organisation.</span><span class="sxs-lookup"><span data-stu-id="bac6e-113">If the Authenticated Users group does not have read access to the OU, run the **Grant-CsOuPermission** cmdlet as illustrated in the following code examples to grant read permissions for each OU.</span></span>

   ```
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

<span data-ttu-id="bac6e-114">Pour plus d’informations sur l’applet **de connexion Grant-CsOuPermission** , voir la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="bac6e-114">For details about the **Grant-CsOuPermission** cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div class="">


> [!TIP]  
> <span data-ttu-id="bac6e-115">Pour plus d’informations sur les entrées ACE créées sur la racine du domaine et dans les conteneurs utilisateurs, ordinateurs et contrôleurs de domaine, voir <A href="lync-server-2013-changes-made-by-domain-preparation.md">modifications apportées par la préparation du domaine dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bac6e-115">For details about the ACEs created on the domain root and in the Users, Computers, and Domain Controllers containers, see <A href="lync-server-2013-changes-made-by-domain-preparation.md">Changes made by domain preparation in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bac6e-116">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="bac6e-116">In This Section</span></span>

  - [<span data-ttu-id="bac6e-117">Exécution de la préparation du domaine pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bac6e-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)

  - [<span data-ttu-id="bac6e-118">Utilisation d’applets de commande pour inverser la préparation d’un domaine pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bac6e-118">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

