---
title: 'Lync Server 2013 : test-CsAddressBookWebQuery pour la gestion du carnet d’adresses'
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
ms.openlocfilehash: c50497979e8439a60799864376d1f93d36646cec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="d5f2d-102">Test-CsAddressBookWebQuery pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5f2d-102">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5f2d-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d5f2d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d5f2d-104">Qui peut exécuter cette applet de commande : par défaut, les membres des groupes suivants sont autorisés à exécuter l’applet de commande test-CsAddressBookWebQuery : RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d5f2d-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="d5f2d-105">Pour renvoyer la liste de tous les rôles de contrôle d’accès basés sur des rôles (RBAC) affectés à cette applet de commande (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="d5f2d-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="d5f2d-106">Comme pour la transaction synthétique test-CsAddressBookService, test-CsAddressBookWebQuery effectue une requête sur la requête Web du carnet d’adresses pour vérifier qu’elle fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="d5f2d-106">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly.</span></span> <span data-ttu-id="d5f2d-107">L’applet de connexion se connecte à l’authentification par ticket Web et présente les informations d’identification spécifiées dans-UserCredential.</span><span class="sxs-lookup"><span data-stu-id="d5f2d-107">The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential.</span></span> <span data-ttu-id="d5f2d-108">S’il est authentifié, l’applet de la cmdlet présente les informations – TargetSipAddress.</span><span class="sxs-lookup"><span data-stu-id="d5f2d-108">If authenticated, the cmdlet then present the –TargetSipAddress information.</span></span> <span data-ttu-id="d5f2d-109">L’applet de la cmdlet doit signaler la réussite s’il a pu récupérer les informations sur le contact.</span><span class="sxs-lookup"><span data-stu-id="d5f2d-109">The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="d5f2d-110">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d5f2d-110">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="d5f2d-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d5f2d-111">See Also</span></span>


[<span data-ttu-id="d5f2d-112">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="d5f2d-112">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

