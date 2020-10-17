---
title: 'Lync Server 2013 : Test-CsAddressBookWebQuery pour la gestion des carnets d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c4112f34eb35bcf45991e6744327487afe9a2a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519241"
---
# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="cf594-102">Test-CsAddressBookWebQuery pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf594-102">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf594-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cf594-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cf594-104">Personnes autorisées à exécuter cette applet de commande : par défaut, les membres des groupes suivants sont autorisés à exécuter l’applet de commande Test-CsAddressBookWebQuery : RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cf594-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="cf594-105">Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="cf594-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="cf594-106">À l’instar de la transaction synthétique Test-CsAddressBookService, Test-CsAddressBookWebQuery effectue une requête sur la requête Web de carnet d’adresses pour s’assurer qu’elle fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="cf594-106">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly.</span></span> <span data-ttu-id="cf594-107">L’applet de commande se connecte à l’authentification de ticket Web et présente les informations d’identification spécifiées dans – UserCredential.</span><span class="sxs-lookup"><span data-stu-id="cf594-107">The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential.</span></span> <span data-ttu-id="cf594-108">Si elle est authentifiée, l’applet de commande présente ensuite les informations – TargetSipAddress.</span><span class="sxs-lookup"><span data-stu-id="cf594-108">If authenticated, the cmdlet then present the –TargetSipAddress information.</span></span> <span data-ttu-id="cf594-109">La cmdlet doit signaler la réussite si elle a pu récupérer les informations sur le contact.</span><span class="sxs-lookup"><span data-stu-id="cf594-109">The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="cf594-110">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="cf594-110">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="cf594-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cf594-111">See Also</span></span>


[<span data-ttu-id="cf594-112">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="cf594-112">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

